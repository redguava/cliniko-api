Custom patient buttons
======================

Cliniko offers an additional integration option for applications that handle
patient data. This allows users to open these applications directly from Cliniko
and potentially synchronize information on a given patient as needed.

How it works for Cliniko users
-------------------------

Users can add these applications in a settings page under
Settings > Our clinic > Integrations:

![Configuration
panel](../assets/custom-patient-buttons-config.png?raw=true)

This adds a new button to the Patient Actions bar for each patient:

![Patient actions with open
dropdown](../assets/patient-actions-open.png?raw=true)

Clicking on one of those buttons causes the user's browser to send a GET request
to the corresponding URL, with a query string of `patient_id=<Cliniko ID of
displayed patient>`. If the user is logged into the other application, they
should be taken directly to that application's information screen about the
patient with that Cliniko ID. If they're not logged in, they should be
redirected to a login screen before they can see the patient information.

How it works for integrators
-------------------------

If you want your application to integrate with Cliniko in this way, it should
have an endpoint prepared to receive GET requests from browsers with the query
string above. Requests made by unauthenticated users should be redirected to a
login screen. Once the user is authenticated, your application should display
the information it has about the patient whose Cliniko ID was included in the
request. If you also integrate with Cliniko via its API, you can have your
application update its information on that patient via the API at this point.

Once your patient integration endpoint is ready, please get in contact with us
so we can add its URL to our list of approved applications! Once that's done you
should be able to publish this URL to your users so they can add it to the
config panel shown above and use the integration.
