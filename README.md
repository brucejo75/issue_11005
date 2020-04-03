# https://github.com/meteor/meteor/issues/11005

To repro the issue
```
cd repro
meteor build ../build --directory --debug --server https://foo.com
```

**Note:** `--directory` & `--debug` flags make the build go faster.

**Result:**
```
%% Failed to install 'cordova-plugin-background-fetch': Error: Cannot find module 'cordova-common'
... (stack trace)
```

Expected it to build.

**Note:** if you remove the reference to `App.appendToConfig` in `mobile-config.js` the app will build.
