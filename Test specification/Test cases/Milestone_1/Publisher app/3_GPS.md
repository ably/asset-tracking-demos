### [GPS_001]
---
*  **Test case name:**  _App working in the background._
* Description: While moved to the background, the app is working correctly..
* **Expected result:** _Location is updated correctly._

### [GPS_002]
---
*  **Test case name:**  _App working while the device is locked._
* Description: _The application is working correctly while the device is locked._
* **Expected result:** _Location is updated correctly._

### [GPS_003]
--
*  **Test case name:**  _GPS accuracy while using other navigation apps._
*  Description: The GPS location is processed corretcly when the user uses another navigation app simultaneously.
*  **Expected result:** _Location is updated correctly._

### [GPS_004]
---
*  **Test case name:**  _GPS functionality when location signal is interrupted._
* Description: _The GPS location is processed correctly when the device loses and recovers the signal._
* **Expected result:** _Location is resumed._

### [GPS_005]
---
*  **Test case name:**  _Publish rate frequency when **no one** is subscribing to the channel._
*  Description: _Check is the frequency of publish rate changes accordingly to battery level and proximity to the destination._

| Battery level: | Proximity to destination: | **Expected result:** |
| --------- 		 | ----------  							 | ----------						|
| Low  		 		   | Close	    							 | Lower freq					  |
| High 				 	 | Far away    							 | Lower freq						|
| Low  		 		   | Far away 						     | Lower freq						|
| High 				 	 | Close	    							 | High freq						|

### [GPS_006]
---
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

### [GPS_007]
---
*  **Test case name:**  _Changing publish rate frequency when channel gets subscribbed._
* Description: _Check publish rate frequency change while the app is running[unsubscribbed-> subscribbed -> unsubbscribed]._
* **Expected result:** _Publish rate is changed immidately._

### [GPS_008]
---
*  **Test case name:**  _Changing publish rate frequency when the battery level is dropping and rising._
* Description: _Check publish rate frequency change while the app is running[low battery level -> high battery level -> low battery level]._
* **Expected result:** _Publish rate is changed immidately._

### [GPS_009]
---
*  **Test case name:**  _Changing publish rate frequency when the rider gets close and far away from the destination._
* Description: _Check the publish rate frequency change while the app is running[close to the destination -> far from the destination -> close to the destination]._
* **Expected result:** _Publish rate is changed immediately._

### [GPS_010]
---
*  **Test case name:**  _App behavior when the device is charged._
* Description: _Confirm that the publish rate changes according to subscription or proximity to the destination when the device is being charged._
* **Expected result:** _Publish rate is changed according to rules._

### [GPS_011]
---
*  **Test case name:**  [LONG RUN | APP IN BACKGROUND] _Publish rate frequency isn't changed._
* Description: _Check app behavior when battery level is high, and localization isn't altered for a longer time [~10h]._
* **Expected result:** _Publish rate freq isn't changed._

### [GPS_012]
---
*  **Test case name:**  [LONG RUN | APP OPENED] _Publish rate frequency isn't changed._
* Description: _Check app behavior when battery level is high, and localization isn't altered for a longer time [~10h]._
* **Expected result:** _Publish rate freq isn't changed._

### [GPS_013] [ANDROID]
---
*  **Test case name:**  _App behavor when the device is in battery save mode._
* Description: _Check if the app operates correctly in different battery-safe modes._
* **Expected result:** _GPS location is resumed when leaving battery safe mode._
