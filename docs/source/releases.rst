Releases
********

Create Release
==============
Method: **POST**
Endpoint: **/v1/applications/<application_short_hash>/releases/**

======== ========== ===================================================================================================================================================================================================================== 
Field    Required   Description                                                                                                                                                                                                          
======== ========== ===================================================================================================================================================================================================================== 
status   false      2 to make your release public. Release will be distributed to available testers. 1 to make your release private. Release won't be distributed to testers. This also prevents release from showing up for SDK update  
notify   false      Notify testers? 1 for yes, 0 for no                                                                                                                                                                                  
notes    false      Release notes     
======== ========== ===================================================================================================================================================================================================================== 

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
