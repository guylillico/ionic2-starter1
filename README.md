# Backand Ionic 2 Starter
Create mobile application with [ionic](http://www.ionicframework.com) and [backand](http://www.backand.com).
**NOTE: Compatible with Ionic ^2.2.1**


## Running the app

- Create an Ionic app:
```bash
$ ionic start myApp https://github.com/backand/ionic2-starter1 --v2    
$ cd myApp
```

- Install dependencies:
```bash
$ npm install @backand/angular2-sdk socket.io-client @types/node @types/socket.io-client
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

- Want to customize data model or change authorization?
create a free personal application at [backand.com](https://www.backand.com/apps/#/sign_up)

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

- CRUD:
To fetch, create, and filter rows, from an object, say `stuff`, modify
the object used in these functions in `src/pages/crud/crud.ts`:
```javascript
getItems
filterItems
postItem
```
replacing `todo` with the name of your object, `stuff`


- SOCKET:
To subscribe to event `items_updated` from server side via sockets, in your component do, as in `src/app/pages/crud/crud.ts`:
```javascript
this.backand.on("items_updated",
  (data: any) => {
      // do something with data
  });
```

- LOGIN:
The app opens a dialog supplied by the social network.
