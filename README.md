This is a **example extension router** with a **example UI** that has one **component Fee Setting** installed.

Idea is to be able extend LndHub Admin Router with API calls and can have some or all of them decorateded with a UI.

The Example Router has access to all of :

- - BlueWallet Lightning API
- - LndHub
- - Redis DB
- - LND gRPC
- - - Node.js
- - - NPMs in package.json

One can build diffrent API calls and can use any framework for UI,

the shipped example UI here use :

- HTML5
- CSS3
- Vanilla.js
- Mustache.js

addons can be made as components.

        └── extensions
            ├── admin
            │   ├── adminConfig.js
            │   ├── adminRouter.js
            │   └── public
            │       ├── admin.css
            │       ├── comp_feeSetting.html
            │       ├── comp_feeSetting.js
            │       ├── comp_meny.html
            │       ├── css
            │       │   └── adminStyle.css
            │       ├── indexTemplate.html
            │       └── js
            │           └── adminJS.js
            └── components
                ├── AuthAdmin
                │   └── README.md
                ├── FeeSettings
                │   └── README.md
                ├── GrantAccount
                │   └── README.md
                ├── HelpDesk
                │   └── README.md
                ├── InfoStator
                │   └── README.md
                ├── InvoiceDecoder
                │   └── README.md
                ├── NamedAccounts
                │   └── README.md
                ├── QRCodec
                │   └── README.md
                └── WebWallet
                    └── README.md

Under refactoring of the component design, right now only feeSetting component installed

**_INSTALL_**

(need PR https://github.com/BlueWallet/LndHub/pull/238)

Drop folder into /LndHub and in /index.js line

```javascript
// after
app.use(require("./controllers/api"));
// add
app.use(require("./extensions/admin/adminRouter"));
```

(or dload https://github.com/lndhub-admin/LndHub/tree/Admin-Extension-router)

in adminConfig.js

```javascript
{
  adminUIPath: '/ngu', // path to admin UI
  adminUserName: 'Headbanana', // not used other then for display
  adminPin: 'auth-pin-here', // Auth PIN
}
```

set path wanted to reach admin UI from <LndHub-URL>/adminUIPath
and set the adminPin to something You would remember.
