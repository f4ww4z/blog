---
title: "How to get Travis CI Working for Android API Level 28"
categories: ["tutorial"]
tags: ["travis", "ci", "android"]
date: 2019-02-02T08:15:00+07:00
---

I was recently stumbling on setting up [Continuous Integration](https://en.wikipedia.org/wiki/Continuous_integration) (CI) for my newest Android project. As usual, I added a `.travis.yml` file in the root directory of my project (which is hosted at [GitHub](http://github.com/)), and followed [their docs](https://docs.travis-ci.com/user/languages/android/) accordingly so that my app is tested on every commit.
However, even after copying and pasting exactly the code snippets hosted on their documentation, the Travis build is still somehow **failing**. The error shown in the console was rather peculiar:

```
> Failed to install the following Android SDK packages as some licences have not been accepted.
build-tools;28.0.3 Android SDK Build-Tools 28.0.3
platforms;android-28 Android SDK Platform 28
To build this project, accept the SDK license agreements and install the missing components using the Android Studio SDK Manager.
Alternatively, to transfer the license agreements from one workstation to another, see http://d.android.com/r/studio-ui/export-licenses.html
```
Which I could not wrap my head around, as I wanted to use Android API level **27** using the build-tools version **27.0.3** at that current time. So there was no reference at all to use level 28. Here *was* the `.travis.yml` file of the failed build:

<script src="https://gist.github.com/f4ww4z/63e7aa96895336d14b7249627de13291.js"></script>

It is quite clear that the latest version of the Android API is level 28, so I figured I just needed to increment it in my `.travis.yml`. Changing `ANDROID_API_LEVEL` to `28` and `ANDROID_BUILD_TOOLS_VERSION` to `28.0.3`, the build failed once again, with the same error as above.
When all hope was lost (nearly!), something caught my eye in the [Android developers documentation](https://developer.android.com/studio/command-line/sdkmanager) : `sdkmanager`. From the docs,

>The `sdkmanager` is a command line tool that allows you to view, install, update, and uninstall packages for the Android SDK.

This was the tool that I needed all along to install the newest Android SDK packages. It turns out that it is a modernized version of the `android` CLI, which could suggest the behavior of the current Travis Android configuration. Nevertheless, I removed almost all dependencies from the *android components* section, and installed them using `sdkmanager` instead, right at `before_install`.

Here's the new `.travis.yml`:

<script src="https://gist.github.com/f4ww4z/80ea49108ce9fb3aa3256061ab14728f.js"></script>

Key changes:

  * Removed `android-28` and `build-tools-28.0.3` from *android components* section.
  * Install the Android API and build tools with the commands: `yes | sdkmanager "platforms;android-28"` and `yes | sdkmanager "build-tools;28.0.3"`

### Notes

`tools` and `platform-tools` are kept in place to not overload the Travis build length  -  yes, there such thing. When installing the latest `tools` and `platform-tools` via `sdkmanager`, the following error occurs:

![travis build error maximum length](https://cdn-images-1.medium.com/max/1067/1*p9E9MyuCr18UGf60r4tMuw.png)

It is fine to install the latest version using the normal method, as suggested by the Travis documentation.