# Fuse Firebase Notifications
Simple Fuse app. Receives notifications from Firebase.
For Android is pretty straight forward but the issue comes in iOS. The user registers to APNS (Apple Push Notification System) but in order to work with Firebase we need to convert that ID to FCM (Firebase Cloud Messaging) and we do that with the following script:

https://gist.github.com/LuisRodriguezLD/0257300f08eae90e97d81682148c8b22

(Shout out to @jesusmartinoza for the code)




### Requirements
* Firebase project
* For iOS, Bundle ID ready to receive push notifications. More info: https://www.fusetools.com/docs/fuse/pushnotifications/push#certifying-your-app-for-acs
* For iOS, push certificates (.P12) More info: https://firebase.google.com/docs/cloud-messaging/ios/certs


### Sender ID and API Key
For the next step you are going to need the Sender ID and the API key, both can be found in the project settings.
![Alt text](https://luisrodriguez.ws/github/2.png "Project Settings")
![Alt text](https://luisrodriguez.ws/github/3.png "Your Keys")


### Making the example work
* Add both Android and iOS app to the Firebase project.
![Alt text](https://luisrodriguez.ws/github/1.png "Add apps to Project")
* Add the push certificates to the project https://firebase.google.com/docs/notifications/ios/console-audience#upload_your_apns_certificate 
* In the `.unoproj` chande the bundle identifier and use your own.
* In the `.unoproj` chande the Sender ID.
* In Notifications.js change `line 32` with your package name
* In Notifications.js change `line 44` with your api key 
 
 
### Important iOS
* You need to build using `-adebug` and manually make sure Push Notifications is on
![Alt text](https://luisrodriguez.ws/github/4.png "Turn on push notifications")
* This is for testing purposes only, if you were to sumbit to the App Store the notifications <b>will not work</b>. Change `line 33` to `false`


### Testing
From the Firebase console send a notification, you can either choose everyone who has the app or a specific user.
![Alt text](https://luisrodriguez.ws/github/5.png "Send Notification")
  
### Obligatory Pics
iOS Working             |  iOS Payload | Android Working
:-------------------------:|:-------------------------:|:-------------------------:
| 
![Alt text](https://luisrodriguez.ws/github/r1.jpg "Notifications Working")  | ![Alt text](https://luisrodriguez.ws/github/r2.jpg "Payload")  | ![Alt text](https://luisrodriguez.ws/github/r3.jpg "android")  |

