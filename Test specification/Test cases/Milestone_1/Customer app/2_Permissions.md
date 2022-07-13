### [Permissions_001]
---
*  **Test case name:**  _GPS permissions question._
*  Description: _Is the user asked about GPS permissions?
*  **Expected result:**
_User can decide if Rider and Customer app get the permissions to use GPS location. Apps behave accordingly to the user's input:_
_1. Check when permissions are granted._
_2. Confirm that the app asks about permissions when they are missing._

### [Permissions_002]
---
*  **Test case name:**  _Changing GPS permissions in **OS settings**._
*  Description: Can the user effectively change GPS permissions?
*  **Expected result:** 
_1. When permissions are revoked -> user is asked again after going to map view for them._
_2. When permissions are given -> user will not be asked about any permissions, and the map|GPS pointer is working correctly._

### [Permissions_003]
---
*  **Test case name:**  _"Only once" GPS permissions._
*  Description: Check app behavior when "only once" GPS permissions were granted.
*  **Expected result:** _Apps are working correctly._

### [Permissions_004] [ANDROID]
---
*  **Test case name:**  _Revoking GPS permissions by Android._
*  Description: Check if the user can give permissions when they are removed by Android's "Auto revoke permissions" option. [TIP] this mechanism is triggered when the app isn't used for a long time.
*  **Expected result:** _Permissions question is presented to the user when the app is used next time._

### [Permissions_005]
---
*  **Test case name:**  _App killed while GPS permission dialog is presented._
*  Description: Check the app behavior when the user kills the app when permissions are determined.
*  **Expected result:** _Permissions question is presented to the user when the app is opened next time._

### [Permissions_006]
---
*  **Test case name:**  _GPS permissions refused at app launch._
*  Description: Check the app behavior when the user rejects GPS permissions.
*  **Expected result:** _The user is asked again after the next app launch._