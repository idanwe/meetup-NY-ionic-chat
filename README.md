#### Step 0 - start

1. Run `ionic start chat blank`

#### Step 1 - chat view

1. Run `ionic setup sass`
2. Run `npm install`
3. Add chat template and CtrlController

#### Step 2 - Connect to meteor server

1. Run `meteor create server`
2. Replace `server.js` code with `Messages = new Meteor.Collection('messages');`
3. Run `bower install meteor-client-side angular-meteor`
4. Add to `index.html` 
```
    <script src="lib/meteor-client-side/meteor-runtime-config.js"></script>
    <script src="lib/meteor-client-side/dist/meteor-client-side.bundle.min.js"></script>
    <script src="lib/angular-meteor/dist/angular-meteor.bundle.min.js"></script>
```
5. Add `Messages = new Meteor.Collection('messages');` to the client
6. Assign angular meteor collection to $scope `$scope.messages = $scope.$meteorCollection(Messages);`
7. Run the app: `ionic serve` && `cd server && meteor`

#### Step 3 - Users

In the server:
1. Run `meteor add accounts-password`

In the client:
1. Run `bower install accounts-password-client-side`
2. Add to `index.html`
```
    <script src="lib/accounts-base-client-side/dist/accounts-base-client-side.bundle.min.js"></script>
    <script src="lib/accounts-password-client-side/dist/accounts-password-client-side.bundle.min.js"></script>
    <script src="lib/angular-meteor.bundle.min.js"></script>
```
3. Add login, register and logout
4. Add to message wrapper div (`.message-list`) `ng-if="$root.currentUser`
5. Add `currentUser._id` to message
