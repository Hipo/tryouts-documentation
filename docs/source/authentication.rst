Authentication
**************

We use app_id and app_secret to authenticate your account. You can get your app_id and app_secret from your tryouts profile. Authentication is made by HTTP 'Authorization' header.

Example Requests:

::

    curl <api_endpoint> \
    -H "Authorization: app_id:app_secret"
