<p align="center">
  <a href="https://sentry.io" target="_blank" align="center">
    <img src="https://sentry-brand.storage.googleapis.com/sentry-logo-black.png" width="280">
  </a>
  <br />
</p>

_Bad software is everywhere, and we're tired of it. Sentry is on a mission to help developers write better software faster, so we can get back to enjoying technology. If you want to join us [<kbd>**Check out our open positions**</kbd>](https://sentry.io/careers/)_

Sentry (lite) SDK for Unity
===========

> This is the stable Sentry SDK for Unity. It's running in production in many games and sends millions of events every month to [sentry.io](sentry.io).
If you are used to other Sentry SDKs, you might find that the API here is smaller. This is by design, and this SDK is lightweight and compile with your game.
It supports any platform that you can target with Unity.

**Sentry is working on a complete SDK for Unity with features such as Release Health, Native Crash Reporting and Performance Monitoring.
If you'd like to learn more check out [sentry-unity](https://github.com/getsentry/sentry-unity) or join us on Discord, #unity: [![Discord Chat](https://img.shields.io/discord/621778831602221064?logo=discord&logoColor=ffffff&color=7389D8)](https://discord.gg/PXa5Apfe7K)**

# We are currently not accepting PRs for new features on this repository.

Bug fixes are most welcomed and we'll continue to support the code base for security and bug fixes. But any new development, [refer to Sentry Unity](https://github.com/getsentry/sentry-unity).

### Installation

#### Through the package manager

![Install git package screenshot](./Documentation~/install-git-package.png)

Open the package manager, click the + icon, and add git url.

```
https://github.com/getsentry/sentry-unity-lite.git#1.0.3
```

### Usage

In order to make Sentry work, you need to add `SentrySdk` component to any
`GameObject` that is in the first loaded scene of the game.

You can also add it programatically. There can only be one `SentrySdk`
in your whole project. To add it programatically do:

```C#
var sentry = gameObject.AddComponent<SentrySdk>();
sentry.Dsn = "__YOUR_DSN__"; // get it on sentry.io when you create a project, or on project settings.
```

The SDK needs to know which project within Sentry your errors should go to. That's defined via the DSN.
DSN is the only obligatory parameter on `SentrySdk` object.

This is enough to capture automatic traceback events from the game. They will
be sent to your DSN and you can find them at [sentry.io](sentry.io)

`SentrySdk` is the main component that you have to use in your own project.

### Example

The package includes a Demo scene. `SentryTest` is a component that handles
button presses to crash or fail assert.

### API

The basic API is automatic collection of test failures, so it should mostly
run headless. There are two important APIs that are worth considering.

* collecting breadcrumbs

  ```C#
  SentrySdk.AddBreadcrumb(string)
  ```

  will collect a breadcrumb.

* sending messages

  ```C#
  SentrySdk.CaptureMessage(string)
  ```

  would send a message to Sentry.

### Unity version

The lowest required version is Unity 5.6.
Previous versions might work but were not tested and will not be supported.


### Native Crash Support

Sentry is [working on a Unity SDK](https://github.com/getsentry/sentry-unity) based on the .NET SDK which includes offline caching and native crashes.
Previews of that package are available. If you'd like to get involved in the SDK development, you can [join Sentry's Discord server and say hi on the `#unity` channel](https://discord.gg/UmjjsgRAFa).

## Resources

* [![Documentation](https://img.shields.io/badge/documentation-sentry.io-green.svg)](https://docs.sentry.io/platforms/dotnet/)
* [![Forum](https://img.shields.io/badge/forum-sentry-green.svg)](https://forum.sentry.io/c/sdks)
* [![Discord Chat](https://img.shields.io/discord/621778831602221064?logo=discord&logoColor=ffffff&color=7389D8)](https://discord.gg/PXa5Apfe7K)  
* [![Stack Overflow](https://img.shields.io/badge/stack%20overflow-sentry-green.svg)](http://stackoverflow.com/questions/tagged/sentry)
* [![Twitter Follow](https://img.shields.io/twitter/follow/getsentry?label=getsentry&style=social)](https://twitter.com/intent/follow?screen_name=getsentry)
