Releases
********

Create Release
==============
Method: **POST**
Endpoint: **/v1/applications/<application_short_hash>/releases/**

Example Requests:

::

    curl https://api.tryouts.io/v1/applications/zFBQ1NoV/releases/ \
    -F "build=@<-build-file-path>" \
    -F "notes=release-notes-here" \
    -F "notify=1" \
    -F "status=2" \
    -H "Authorization: api_key:api_secret"

Response:

::

    {
        "application_name": "my new fancy app",
        "minimum_os_version": "Android 4.0.3, 4.0.4",
        "download_url": "https://tryouts.io/releases/xTcFsjBGK/",
        "size": "7.59 MB"
    }
