Sharding is the term we use to define _regionally/geographically isolated instances_ of Cliniko. When new accounts sign up, they'll be able to choose the region in which their account data is hosted. Cliniko will then decide which shard within that region their account will live on.

## Why is Cliniko sharded?

1. Some jurisdictions require medical data to remain within the country/region
2. Lower end-user latency
3. Better performance and scalability

## How does this impact you?

Cliniko users access their account via their account's unique Cliniko subdomain, e.g. `good-healthy-times.cliniko.com`.
With sharding, Cliniko will exist as a collection of regional instances, and a Cliniko account will reside in one of those instances. Cliniko account subdomains will begin to move to the form `subdomain.shard.cliniko.com`. This means you would need to know and use the shard ID in your account's unique Cliniko URL to access your Cliniko account. Trying to access that subdomain in another shard will not work. For an account in the first Australian shard, `au1`, that subdomain will become `good-healthy-times.au1.cliniko.com` (if the account's subdomain was `good-healthy-times`). Currently, all accounts are in `au1` and resolve as either `your-domain.au1.cliniko.com` or `your-domain.cliniko.com`.

As mentioned above, new users will be able to choose their region upon signing up to Cliniko. We will also make it possible to move a Cliniko account from one region to another on request. There is one group of accounts for whom we are supporting an early move to their own shard: UK accounts that **opt in** to using a shard in the UK. This first non-Australian shard will be `uk1`.

It's important to note that we are not moving all UK accounts to `uk1`. For existing UK accounts, this is optional and by request only. If an account in the UK wishes to move to a UK-based shard, we will conduct transfer of their data across to that shard from `au1`. The following things then need to happen:

- the account will have a few hours of down time while the account's data is migrated
- that account will need to start using the shard ID in their unique Cliniko subdomain, i.e. `physio-on-thames.uk1.cliniko.com`
- any integrations with that account via the API will need to use the shard ID in the API URL, i.e. `api.uk1.cliniko.com`

_Remember:_ new accounts will also be able to choose to start on the `uk1` shard, so it is important that your integration is able to handle this right from the get go, and without a customer advising you of their choice in shard.

## That's where you come in!

You can see that this has a downstream effect on integrators - it will be mandatory for any accounts _not in the default `au1` shard_ to use the shard ID in the URL of _all_ Cliniko API request. In addition, API keys have also changed slightly (more below), the goal being to make it possible for you to know which shard you need to be pointing to from the API key alone.

# API keys and API URLs

If you go and generate a new API key right now, you'll notice that it's got a little something extra appended to it - the account's shard ID. e.g. `MS0xLWl4SzYYYYdtR3V2HNOTAREALKEYwvNHI2d2xHHHHjLXuytrF0ZV9sdeW0pd-au1`. The last few characters tell you which shard this API key may be used against.

## Using shard-aware API keys

When a Cliniko user supplies their API key, you will need to use the shard ID when making API requests on behalf of users of that account.
Some examples:

- An API key ending `-uk1` must have all API requests routed to `https://api.uk1.cliniko.com`
- An API key ending `-us1` must have all API requests routed to `https://api.us1.cliniko.com`
- An API key ending `-au1` _may_ have API requests routed to `https://api.au1.cliniko.com` or `https://api.cliniko.com`

_Existing API keys stored in your integration can be written as `{THE_API_KEY_VALUE}-au1` - that is, all already-issued API keys may be used against the `au1` shard._

> For existing API keys, you should begin using the default shard `au1` now. It's good practice to get in to and eventually the current Cliniko API URL will start redirecting with a `301`, only responding to requests on the sharded routes.

The API key is passed in the Basic authorization header, just as you do now: `b64($API_KEY + ':')` and you may **include or exclude** the hyphenated shard ID. That is, if you make an API request using either `MS0xLWl4SzYY-uk1` or `MS0xLWl4SzYY`, the request will succeed. You just need to ensure you're sending the request to the correct shard (in this case, `uk1`).

# Recap

- users will be able to choose their Cliniko region at sign-up; a new user may choose _any_ region to have their account data hosted. It is possible for an Australian customer to choose the UK as their region, so even if you don't have customers in the UK, consider that it is possible you'll need to handle sharded requests once the UK shard is live.
- if your integration does not currently deal with any UK Cliniko customers, please start using the shard ID supplied to you in new API keys anyway (as all new API keys now include the shard ID).
- if your integration deals with UK customers, you will need to ensure that you are able to handle the new format API key, and that your integration is able to route requests to the correct shard, based on the shard ID in the API key.
- if you'd like to start using the sharded API URL across the board, the default shard ID is `au1`. Requests to `https://api.cliniko.com` and `https://api.au1.cliniko.com` are the same.

## Code examples

While these examples are not designed to work, they should give you a good idea of how your API key usage should change.

### Saving an API key

```js
function saveApiKey(apiKeyInput, accountId) {
  var apiKeyParts = apiKeyInput.split('-');
  var apiKey = null;
  var shardId = null;

  if (apiKeyParts.length === 1) {
    // If no shard ID supplied, default it in.
    apiKey = apiKeyParts[0];
    shardId = 'au1';
  } else if (apiKeyParts.length === 2 && /^\w{2}\d{1,2}$/.test(apiKeyParts[1])) {
    // Otherwise, use the shard ID supplied to you, ensuring it matches known attributes
    // e.g. two alpha chars followed by 1-2 digits
    apiKey = apiKeyParts[0];
    // Maybe also validate it against the list of current shard regions?
    shardId = apiKeyParts[1];
  } else {
    throw new Error('Invalid API key');
  }

  var clinikoIntegration = new ClinikoIntegration({
    accountId: accountId,
    apiKey: apiKey,
    shardId: shardId
  });
  clinikoIntegration.save();
}
```

### Using an API key

```js
function requestClinikoPatient(patientId, accountId) {
  var clinikoIntegration = ClinikoIntegration.findOne({ accountId: accountId });

  // If you don't have a shard ID saved, use the default au1.
  var shardId = clinikoIntegration.shardId || 'au1';
  var requestOpts = {
    url: 'https://api.' + shardId + '.cliniko.com/v1/patients/' + patientId,
    method: 'GET',
    headers: {
      authorization: 'Basic ' + base64(clinikoIntegration.apiKey + ':'),
      'user-agent': 'Your name (integrations@example.com)',
      accept: 'application/json',
      'content-type': 'application/json'
    }
  };
  var patient = request(requestOpts);
  // Do helpful things...
}
```
