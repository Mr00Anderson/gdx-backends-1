## Backends for libGDX, easy to build

Since we have no regular libGDX releases anymore, it is a problem to fix backend behaviour that can't be overriden.
While there's always a way to work around bugs in the core project, this is often not possible in the backends.

This is where this repo comes in.

If you need to change build-in behaviour, but don't manage to get the complete libGDX repo to build, don't want to 
build your very own version or don't want to use snapshot versions, this repo is what you need.


### How

* Clone this repo
* Checkout the revision you need (next paragraph)
* Type `gradlew install`
* Change your project's backend dependency to the one you wish

## Changes compared to libGDX 1.9.8

### 1.98.0

This is exactly like libGDX 1.9.8. The backends in this version can be used only with libGDX 1.9.8.

Checkout branch [release/1.98.0](https://github.com/MrStahlfelge/gdx-backends/tree/release/1.98.0) to use this version.

### 1.98.1

Checkout branch `master` to use this version.

Can be used with libGDX 1.9.9 and 1.9.8.

This is mainly targeted towards replacing the original GWT and iOS backends for libGDX 1.9.8 if you need one of the 
following improvements:

Downgraded from libGDX 1.9.9
* Android, GWT, iOS: Added all fixes from 1.9.9 (check the commit history)
* iOS/GWT: Added support for pressure from 1.9.9 with one caveat: `isPeriphalAvailable` will report false for `Pressure`.
* iOS: Added configuration options for iPhone X (hideHomeIndicator, screenEdgesDeferringSystemGestures) from 1.9.9
* iOS: New devices added

Downgraded from libGDX 1.9.10
* Android, GWT, iOS: Added all fixes from 1.9.10-SNAPSHOT as of 05/31/19 (check the commit history)
* iOS: Compatible with RoboVM 2.3.6 and this with iOS 12
* iOS: New devices added
* GWT: Use the real clipboard
* GWT: Change logging to JavaScript console
* GWT: Unimplemented HttpResponse operations throw exceptions instead of returning null. [See PR](https://github.com/libgdx/libgdx/pull/5661).
* GWT: Accelerometer support [See PR by @SimonIT](https://github.com/libgdx/libgdx/pull/5654)
* iOS: allowIpod defaults to true
* iOS: Possibility to add new devices without changing the backend. [See PR](https://github.com/libgdx/libgdx/pull/5676).
* GWT: Preload logo and progress bar style adjustable. [See PR](https://github.com/libgdx/libgdx/pull/5678).
* iOS: Make UIViewController customizable. See [current PR](https://github.com/libgdx/libgdx/pull/5684).

Own additions
* GWT: Switched to WebAudio, fixes sounds for mobiles too. [Original PR by @barkholt](https://github.com/libgdx/libgdx/pull/4220). See [current PR](https://github.com/libgdx/libgdx/pull/5659) for more information.
* GWT: Faster bootstrap process by lazy loading assets. See [current PR](https://github.com/libgdx/libgdx/pull/5677) for more information.
* GWT: Fixed density problems on mobile with new config setting. See [current PR](https://github.com/libgdx/libgdx/pull/5691)

## Future work

### iOS
- [ ] iPhone X helper
- [ ] keyboard handling

### GWT
- [ ] Move resizable browser window support into the backend, no template hazzle any more