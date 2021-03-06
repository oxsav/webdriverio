WebdriverIO Appium Service
==========================

Handling the Appium server is out of scope of the actual WebdriverIO project. This service helps you to run the Appium server seamlessly when running tests with the [WDIO testrunner](https://webdriver.io/guide/testrunner/gettingstarted.html). It starts the [Appium Server](http://appium.io/docs/en/about-appium/getting-started/index.html#starting-appium) in in a child process.

## Installation

The easiest way is to keep `@wdio/appium-service` as a devDependency in your `package.json`.

```json
{
  "devDependencies": {
    "@wdio/appium-service": "^5.0.0"
  }
}
```

You can simple do it by:

```bash
npm install @wdio/appium-service --save-dev
```

Instructions on how to install `WebdriverIO` can be found [here.](https://webdriver.io/docs/gettingstarted.html)

## Configuration

In order to use the service you need to add `appium` to your service array:

```js
// wdio.conf.js
export.config = {
  // ...
  services: ['appium'],
  // ...
};
```

## Options

The following options can be added to the wdio.conf.js file.

### logPath
Path where all logs from the Appium server should be stored.

Type: `String`

Default: `{}`

Example:
```js
export.config = {
    appium: {
        logPath : "./",
    }
}
```

### command
The name of the command which should be started.

Type: `String`

Default: `{}`

Example:
```js
export.config = {
    appium: {
        command: "myAppium",
    }
}
```

### args
Map of arguments for the Appium server, passed directly to `appium`.

See [the documentation](http://appium.io/docs/en/writing-running-appium/server-args/index.html) for possible arguments.
The arguments should be supplied in lower camel case, so `--pre-launch true` becomes `preLaunch: true`.

Type: `Object`

Default: `{}`

Example:
```js
export.config = {
  appium: {
    args: {
      // ...
      debugLogSpacing: true,
      platformName: 'iOS',
      // ...
    }
  }
},
```

----

For more information on WebdriverIO see the [homepage](https://webdriver.io).
