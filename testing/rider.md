## General

### General_001
*  **Test case name:**  _Mapbox access token._
*  Description: May embed the Mapbox access token in the app.
*  **Expected result:** _The map is available and adequately presented to the user._

### General_002
*  **Test case name:**  _Creating Trackable ID._
*  Description: User can create trackable ID.
*  **Expected result:** _Trackable ID is created._

### General_003
*  **Test case name:**  _Trackable ID with empty name._
*  Description: The user shouldn't be able to create a trackable without any name.
*  **Expected result:** _Trackable ID will be not created._

### General_004
*  **Test case name:**  _Trackable ID with the given destination._
*  Description: The user should be able to create a trackable with a specified destination.
*  **Expected result:** _Trackable ID is created, and the destination matches the given one._

### General_005
*  **Test case name:**  _Trackable ID without  destination._
*  Description: The user should be able to create trackable without a specified destination.
*  **Expected result:** _Trackable ID is created, and there is no destination point._

### General_006
*  **Test case name:**  _App working in the background._
*  Description: The application is working correctly while operating from the background.
*  **Expected result:** _Location is updated correctly._

### General_007
*  **Test case name:**  _App working while the device is locked._
*  Description: The application is working correctly while the device is locked.
*  **Expected result:** _Location is updated correctly._

### [TBD] Cross-platform test cases

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
_1. In case when permissions are revoked -> user is asked again after going to map view for them._
_2. In case when permissions are given -> user will not be asked about any permissions, and the map|GPS pointer is working correctly._

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

## GPS

### GPS_001
*  **Test case name:**  _App working in the background._
* Description: While moved to the background, the app is working correctly..
* **Expected result:** _Location is updated correctly._

### GPS_002
*  **Test case name:**  _App working while the device is locked._
* Description: _The application is working correctly while the device is locked._
* **Expected result:** _Location is updated correctly._

### GPS_003
*  **Test case name:**  _GPS accuracy while using other navigation apps._
*  Description: The GPS location is processed corretcly when the user uses another navigation app simultaneously.
*  **Expected result:** _Location is updated correctly._

### GPS_004
*  **Test case name:**  _GPS functionality when location signal is interrupted._
* Description: _The GPS location is processed correctly when the device loses and recovers the signal._
* **Expected result:** _Location is resumed._

### GPS_005
*  **Test case name:**  _Publish rate frequency when **no one** is subscribing to the channel._
*  Description: _Check is the frequency of publish rate changes accordingly to battery level and proximity to the destination._

| Battery level: | Proximity to destination: | **Expected result:** |
| --------- 		 | ----------  							 | ----------						|
| Low  		 		   | Close	    							 | Lower freq					  |
| High 				 	 | Far away    							 | Lower freq						|
| Low  		 		   | Far away 						     | Lower freq						|
| High 				 	 | Close	    							 | High freq						|

### GPS_006
*  **Test case name:**  _Publish rate frequency when **somebody** subscribes to the channel._
*  Description: _Check is the frequency of publish rate changes accordingly to battery level and proximity to the destination._

| Battery level: | Proximity to destination: | **Expected result:** |
| --------- 		 | ----------  							 | ----------						|
| Low  		 		   | Close	    							 | Lower freq					  |
| High 				 	 | Far away    							 | Lower freq						|
| Low  		 		   | Far away 						     | Lower freq						|
| High 				 	 | Close	    							 | High freq						|

> ### Test Case [GPS_005] and [GPS_006] results comparission
>
> Expected results should be compared against each other: 
> frequency for the same test conditions (eg, low battery level and close destination) should be higher in the case when someone is subscribing to the channel[GPS_006] than when the channel is unsubscribbed[GPS_005]

### GPS_007
*  **Test case name:**  _Changing publish rate frequency when channel gets subscribbed._
* Description: _Check publish rate frequency change while the app is running[unsubscribbed-> subscribbed -> unsubbscribed]._
* **Expected result:** _Publish rate is changed immidately._

### GPS_008
*  **Test case name:**  _Changing publish rate frequency when the battery level is dropping and rising._
* Description: _Check publish rate frequency change while the app is running[low battery level -> high battery level -> low battery level]._
* **Expected result:** _Publish rate is changed immidately._

### GPS_009
*  **Test case name:**  _Changing publish rate frequency when the rider gets close and far away from the destination._
* Description: _Check the publish rate frequency change while the app is running[close to the destination -> far from the destination -> close to the destination]._
* **Expected result:** _Publish rate is changed immediately._

### GPS_010
*  **Test case name:**  _App behavior when the device is charged._
* Description: _Confirm that the publish rate changes according to subscription or proximity to the destination when the device is being charged._
* **Expected result:** _Publish rate is changed according to rules._

### GPS_011
*  **Test case name:**  [LONG RUN | APP IN BACKGROUND] _Publish rate frequency isn't changed._
* Description: _Check app behavior when battery level is high, and localization isn't altered for a longer time [~10h]._
* **Expected result:** _Publish rate freq isn't changed._

### GPS_012
*  **Test case name:**  [LONG RUN | APP OPENED] _Publish rate frequency isn't changed._
* Description: _Check app behavior when battery level is high, and localization isn't altered for a longer time [~10h]._
* **Expected result:** _Publish rate freq isn't changed._

### GPS_013 [ANDROID]
*  **Test case name:**  _App behavor when the device is in battery save mode._
* Description: _Check if the app operates correctly in different battery-safe modes._
* **Expected result:** _GPS location is resumed when leaving battery safe mode._
