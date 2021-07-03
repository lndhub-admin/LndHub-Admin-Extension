# LndHub-Admin-Extension

Extension to manage accounts and settings for LndHub

- Needs work to be able easy install components for API and also UI if needed

This is a example extension router with a example UI that has one component Fees Settings installed.

Idea is to be able extend LndHub Admin Router with API calls and can have some decorateded with a UI.

The Example Router has access to all of BlueWallet Lightning LndHub API + Redis DB + Lightning + all NPMs in package.json

One can build diffrent API calls and use any framework for UI, the shipped one here use 
HTML5
CSS3
Vanilla.js
addons can be made as components.

***INSTALL***
Drop folder into /LndHub/index.js line after
```
app.use(require('./controllers/api'));
//add
app.use(require('./extensions/admin/adminRouter'));
```
