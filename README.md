# Backand Ionic 2 Starter
Create a mobile application with [ionic](http://www.ionicframework.com) and [backand](http://www.backand.com).
**NOTE: Compatible with Ionic 2.2.1**


## Running the app

- Create an Ionic app:
```bash
$ ionic start myApp https://github.com/backand/ionic2-starter1 --v2    
$ cd myApp
```

- Install dependencies:
```bash
$ npm i -S @backand/angular2-sdk socket.io-client @types/node @types/socket.io-client
```

- Install Cordova Plugins
```bash
$ ionic plugin add cordova-plugin-inappbrowser
```

- Run the app
```bash
$ ionic serve
```

- In order to run the app on another platform (Android/iOS):
```bash
$ cordova platform add <platform>
$ ionic run <platform>
```


## Setting up your own Backand application
If you want to customize the data model, or change how authentication takes place, follow these steps:

- Create a free personal application at [backand.com](https://www.backand.com/apps/#/sign_up)

- Change the app's parameters (/src/app/app.component.ts) in the init function with your new app parameters:
```javascript
backand.init({
  appName: 'your app name',
  signUpToken: 'your signup token',
  anonymousToken: 'your anonymousToken token',
  runSocket: true,
  mobilePlatform: 'ionic'
});
```

- Delete the starter content, and begin writing your app!

Review our Angular 2 SDK to get started - [angular2-sdk](https://github.com/backand/angular2-sdk).
