Authentication
**************

We use api_key and api_secret to authenticate your account. You can get your api_key and api_secret from your tryouts profile. Authentication is made by HTTP 'Authorization' header.

Example Requests:

::

    curl <api_endpoint> \
    -H "Authorization: api_key:api_secret"
