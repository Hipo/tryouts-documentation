Invitations
***********

Create Invitation
=================
Method: **POST**
Endpoint: **/v1/applications/<application_short_hash>/invitations/**

Example Requests:

::

    curl 'https://api.tryouts.io/v1/applications/zFBQ1NoV/invitations/' \
    -X POST \
    -H "Authorization: api_key:api_secret" \
    -H "Content-Type: application/json" \
    -d '{
        "invitations":[
            {
                "receiver": "fancy+tester@tryouts.io",
                "is_admin": true
            },
            {
                "receiver": "fancy+tester2@tryouts.io"
            }
        ]
    }'


.. note:: the field `is_admin` is optional and `false` as default.

Response:

::

    {
        "results": [
            {
                "id": 63,
                "sender": 2,
                "receiver": "fancy+tester@tryouts.io",
                "invite_code": "2e5b7ef3-19fa-495b-980f-4b60a7f54fb3",
                "application": 43,
                "is_used": false,
                "is_admin": true,
                "date_created": "2015-11-18T12:17:53.812Z"
            },
            {
                "id": 64,
                "sender": 2,
                "receiver": "fancy+tester2@tryouts.io",
                "invite_code": "0ef3eaba-145c-45d6-aaaa-6674d7df9ec7",
                "application": 43,
                "is_used": false,
                "is_admin": false,
                "date_created": "2015-11-18T12:17:56.335Z"
            }
        ]
    }

