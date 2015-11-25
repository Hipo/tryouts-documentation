Applications
************

Create Application
==================
Method: **POST**
Endpoint: **/v1/applications/**

=========== ==
Device Type Id
=========== ==
iOS 		1
Android		3
=========== ==

Example Requests:

::

    curl 'https://api.tryouts.io/v1/applications/' \
    -X POST \
    -H "Authorization: api_key:api_secret" \
    -H "Content-Type: application/json" \
    -d '{
        "name": "My new fancy app",
        "device_type": 1,
        "icon_file": "base64 image as a string"
    }'

.. note:: 
    **a base64 image**
    ``data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7``

    **icon_file accepts only the part after "base64,"**
    ``R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7``
.. note:: the field ``icon_file`` is optional.


Response:

::

    {
        "id": 43,
        "name": "my new fancy app",
        "os_name": "Android",
        "device_type": "3",
        "short_hash": "8YonowI8",
        "icon_original": "https://tryouts.s3.amazonaws.com/static/img/appicon@2x.jpg",
        "icon_thumbnail": "https://tryouts.s3.amazonaws.com/static/img/appicon.jpg",
    }

List Applications
=================
Method: **GET**
Endpoint: **/v1/applications/**

Example Requests:

::

    curl 'https://api.tryouts.io/v1/applications/' \
    -H "Authorization: api_key:api_secret" \

Response:

::

    {
        "count": 25,
        "next": "https://api.tryouts.io/v1/applications/?page=3",
        "previous": "https://api.tryouts.io/v1/applications/?page=1",
        "results": [
            {
                "id": 9,
                "name": "my new fancy app",
                "os_name": "iOS",
                "device_type": "1",
                "short_hash": "ITd1aWzR",
                "latest_release": {
                    "id": 106,
                    "release_number": "0.3.0b1",
                    "release_notes": "",
                    "release_date": "2015-11-11T10:31:12.025Z",
                    "minimum_os_version": "7.0",
                    "size": "0.19 MB",
                    "short_hash": "N44G3jcd",
                    "download_link": "https://tryouts.io/releases/N44G3jcd/",
                    "public_install_link": "https://tryouts.io/releases/N44G3jcd/install/",
                    "cf_bundle_short_version_string": "0.3.0",
                    "cf_bundle_version": "0.3.0b1",
                    "is_ios_enterprise_build": false,
                    "identifier": "W9875NV3WF.com.hipo.HappyBird"
                },
                "icon_original": "https://tryouts.s3.amazonaws.com/static/img/appicon@2x.jpg",
                "icon_thumbnail": "https://tryouts.s3.amazonaws.com/static/img/appicon.jpg"
            },
            {
                "id": 3,
                "name": "my new fancy app",
                "os_name": "Android",
                "device_type": "3",
                "short_hash": "zFBQ1NoV",
                "latest_release": {
                    "id": 133,
                    "release_number": "1.0",
                    "release_notes": "",
                    "release_date": "2015-11-17T14:56:10.821Z",
                    "minimum_os_version": "Android 4.0.3, 4.0.4",
                    "size": "7.59 MB",
                    "short_hash": "oNZ4QpAG"
                },
                "icon_original": "https://tryouts.s3.amazonaws.com/static/img/appicon@2x.jpg",
                "icon_thumbnail": "https://tryouts.s3.amazonaws.com/static/img/appicon.jpg"
            },
            ...
        ]
    }

Application Detail
==================
Method: **GET**
Endpoint: **/v1/applications/<short_hash>/**

Example Requests:

::

    curl 'https://api.tryouts.io/v1/applications/zFBQ1NoV/' \
    -H "Authorization: api_key:api_secret" \

Response:

::

    {
        "id": 3,
        "name": "my new fancy app",
        "os_name": "Android",
        "device_type": "3",
        "short_hash": "zFBQ1NoV",
        "latest_release": {
            "id": 133,
            "release_number": "1.0",
            "release_notes": "",
            "release_date": "2015-11-17T14:56:10.821Z",
            "minimum_os_version": "Android 4.0.3, 4.0.4",
            "size": "7.59 MB",
            "short_hash": "oNZ4QpAG",
            "download_link": "https://tryouts.io/releases/zFBQ1NoV/",
            "public_install_link": "https://tryouts.io/releases/zFBQ1NoV/install/"
        },
        "icon_original": "https://tryouts.s3.amazonaws.com/static/img/appicon@2x.jpg",
        "icon_thumbnail": "https://tryouts.s3.amazonaws.com/static/img/appicon.jpg"
    }

Application Testers
===================
Method: **GET**
Endpoint: **/v1/applications/<short_hash>/testers/**

Example Requests:

::

    curl 'https://api.tryouts.io/v1/applications/zFBQ1NoV/testers/' \
    -H "Authorization: api_key:api_secret" \

Response:

::

    {
        "count": 4,
        "next": null,
        "previous": null,
        "results": [
            {
                "id": 1,
                "first_name": "fancy",
                "last_name": "tester",
                "devices": [
                    {
                        "id": 3,
                        "owner": 2,
                        "udid": "7c8aff46e2e9517bbe8dec7dc0a73ad500000000",
                        "os": "1",
                        "os_version": "iOS 8.1",
                        "model": "iPhone 6",
                        "hex_id": "a098ceef-3836-4cae-932d-b7f7dbcc9e81"
                    },
                    {
                        "id": 9,
                        "owner": 2,
                        "udid": "9337d45be4824226bfaa53ede1f082ce",
                        "os": "3",
                        "os_version": "Android 5.1.1",
                        "model": "Nexus 6",
                        "hex_id": "d7d5b3f8-1ebc-4935-983a-84a0acf31754"
                    }
                ],
                "name": "fancy tester",
                "email": "fancytester@tryouts.io",
                "date_joined": "2015-10-22T13:44:59Z",
                "avatar_original": "https://www.gravatar.com/avatar/0488cdedcdbed4d47779329d46bc4c3a?s=240&d=https%3A%2F%2Ftryouts.io%2Fstatic%2Fimg%2Fdefault-avatar.png",
                "avatar_thumbnail": "https://www.gravatar.com/avatar/0488cdedcdbed4d47779329d46bc4c3a?s=90&d=https%3A%2F%2Ftryouts.io%2Fstatic%2Fimg%2Fdefault-avatar.png"
            },
            ....
        ]
    }


Remove Tester
=============
Method: **DELETE**
Endpoint: **/v1/applications/<short_hash>/testers/<tester_id>**

Example Requests:

::

    curl 'https://api.tryouts.io/v1/applications/zFBQ1NoV/testers/1' \
    -X DELETE \
    -H "Authorization: api_key:api_secret" \

Response:

::

    Status 204 NO CONTENT
