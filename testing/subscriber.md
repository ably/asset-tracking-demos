## General 

### General_001
*  **Test case name:**  _Start tracking Trackable ID._
*  Description: The user can add a trackable ID.
*  **Expected result:** The app starts to listen to a specified channel._

### General_002
*  **Test case name:**  _Special characters in Trackable ID name._
*  Description: The app allows using special characters in trackable ID name.
*  **Expected result:** _Trackable ID is created._

### General_003
*  **Test case name:**  _iOS maps._
*  Description: The iOS Customer app should use Apple Maps.
*  **Expected result:** _Map view is presented using Apple Maps._

### General_004
*  **Test case name:**  _Android  maps._
*  Description: The Android Customer app should use Google Maps.
*  **Expected result:** _Map view is presented using Google Maps._

### General_005
*  **Test case name:**  _Map marker direction._
*  Description: The map marker shows the Rider's direction.
*  **Expected result:** _Prezented direction matches the real one._

### General_005
*  **Test case name:**  _App working in the background._
* Description: While called from the background, the app is working correctly..
* **Expected result:** _Location is updated correctly._

### General_007
*  **Test case name:**  _App working while the device is locked._
* Description: _The application is working correctly while the device is unlocked._
* **Expected result:** _Location is updated correctly._

### General_008
*  **Test case name:**  _Marker accuracy while using other navigation apps._
*  Description: The marker is presented correctly when the user uses another navigation app simultaneously.
*  **Expected result:** _Location is updated correctly._

### General_009
*  **Test case name:**  _App behavior when the network signal is interrupted(**4G**)._
* Description: _When the network connection is resumed, the marker shows the correct location._
* **Expected result:** _Location is resumed._

### General_010
*  **Test case name:**  _App behavior when the network signal is interrupted(**WiFi**)._
* Description: _When the network connection is resumed, the marker is showing a correct location._
* **Expected result:** _Location is resumed._

### General_011
*  **Test case name:**  _App behavior when switching between networks WiFi/4G._
* Description: _The marker is presented corretcly ._
* **Expected result:** _Location is updated correctly._

## Permissions 

### Permissions_001
*  **Test case name:**  _GPS permissions question._
*  Description: _Is the user asked about GPS permissions?
*  **Expected result:**
_User can decide if Rider and Customer app get the permissions to use GPS location. Apps behave accordingly to the user's input:_
_1. Check when permissions are granted._
_2. Confirm that the app asks about permissions when they are missing._

### Permissions_002
*  **Test case name:**  _Changing GPS permissions in **OS settings**._
*  Description: Can the user effectively change GPS permissions?
*  **Expected result:** 
_1. When permissions are revoked -> user is asked again after going to map view for them._
_2. When permissions are given -> user will not be asked about any permissions, and the map|GPS pointer is working correctly._

### Permissions_003
*  **Test case name:**  _"Only once" GPS permissions._
*  Description: Check app behavior when "only once" GPS permissions were granted.
*  **Expected result:** _Apps are working correctly._

### Permissions_004 [ANDROID]
*  **Test case name:**  _Revoking GPS permissions by Android._
*  Description: Check if the user can give permissions when they are removed by Android's "Auto revoke permissions" option. [TIP] this mechanism is triggered when the app isn't used for a long time.
*  **Expected result:** _Permissions question is presented to the user when the app is used next time._

### Permissions_005
*  **Test case name:**  _App killed while GPS permission dialog is presented._
*  Description: Check the app behavior when the user kills the app when permissions are determined.
*  **Expected result:** _Permissions question is presented to the user when the app is opened next time._

### Permissions_006
*  **Test case name:**  _GPS permissions refused at app launch._
*  Description: Check the app behavior when the user rejects GPS permissions.
*  **Expected result:** _The user is asked again after the next app launch._