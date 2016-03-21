# What is *Wire*

[Wire](https://wire.com)™ is a an app for modern, private communications. So far we released those components of the app that take care of encryption and data handling as Open Source.

Wire is available for a number of platforms: iOS, Android, OSX, Windows, and modern web browsers.

The [privacy page](https://wire.com/privacy/) and the [privacy](https://wire.com/resource/Wire%20Privacy%20Whitepaper/download/) and [security](https://wire.com/resource/Wire%20Security%20Whitepaper/download/) whitepapers explain the details of the encryption algorithms and protocols used.
The source code that implements those algorithms and protocols can be found in the following section.

# Wire architecture

The Wire mobile app has an architectural layer that we call *sync engine*. It is the client-side layer that processes all the data that is displayed in the mobile app. It handles network communication and authentication with the backend, push notifications, local caching of data, client-side business logic, signaling with the audio-video libraries, encryption and decryption (using encryption libraries from a lower level) and other bits and pieces.

The user interface layer of the mobile app is built on top of the *sync engine*, which provides the data to display to the UI.
The sync engine itself is built on top of a few third-party frameworks, and uses Wire components that are shared between platforms for cryptography (Proteus/Cryptobox) and audio-video signaling (AVS).

![Mobile app architecture](/assets/mobile-architecture.png?raw=true "Mobile app architecture")

We are looking into releasing more components in the future. For the moment, we provide source code for encryption (Proteus/Cryptobox) and data handling (Sync Engine and AVS).

## iOS

*ZMessaging-cocoa* is the top-most layer of the iOS *sync engine*, and it is using on a number of lower-level frameworks. *ZMessaging-cocoa* and the lower-lever frameworks constitute the iOS *sync engine*, as illustrated in the following picture.

![iOS architecture](/assets/ios-architecture.png?raw=true "iOS architecture")

The iOS sync engine is developed in a mix of Objective-C and Swift (and just a handful of classes in Objective-C++). It is a result of a long development process that was started in Objective-C when Swift was not yet available. In the past year, parts of it have been written or rewritten in Swift. Going forward, expect new functionalities to be developed almost exclusively in Swift.

### Repositories

- [zmessaging-cocoa](https://github.com/wireapp/zmessaging-cocoa): topmost layer that implements client-side business logic, caching, encryption and client-side backend communication protocol
- [zmc-utilities](https://github.com/wireapp/zmc-utilities): implements common data structures, algorithms (such as symmetric encryption) and application environment detection (internal or public build / production or staging backend)
- [zmc-system](https://github.com/wireapp/zmc-system): covers interaction with ASL (Apple logging), profiling and wrappers of some foundation/cocoa classes
- [zmc-transport](https://github.com/wireapp/zmc-transport): abstracts the network communication with the backend: handles authentication of requests, network failures and retries transparently
- [zmc-testing](https://github.com/wireapp/zmc-testing): testing utilities
- [zmc-protos](https://github.com/wireapp/zmc-protos): precompiled protocol buffer definitions for objective-c / swift and some convenience methods around them
- [zmc-mocktransport](https://github.com/wireapp/zmc-mocktransport): simulates the entire network component (including backend behaviour) for testing purposes
- [zmc-images](https://github.com/wireapp/zmc-images): performs rotation and scaling of images
- [zmc-cryptobox](https://github.com/wireapp/zmc-cryptobox): higher level convenience wrappers around cryptobox for iOS
- [cryptobox-ios](https://github.com/wireapp/cryptobox-ios): iOS binaries for cryptobox

## Android

The Android *sync engine* is developed in Scala.

### Repositories

- [zmessaging-android](https://github.com/wireapp/zmessaging-android): Sync engine library for Android, in Scala
- [cryptobox-jni](https://github.com/wireapp/cryptobox-jni): JNI bindings for cryptobox with support for cross-compilation to Android


## Web App & Native Apps

Wire's web application (called “Wire for Web”) is a web application which runs in modern browsers (Chrome, Edge, Firefox & Opera). It's core is written in CoffeeScript and automatically transpiled into JavaScript. Wire for Windows and Wire for OS X are native applications powered by [Electron](http://electron.atom.io/) and embedding (wrapping) Wire's web application.

The cryptography libraries used in Wire for Web are the following:

### Repositories

- [cbor-codec.js](https://github.com/wireapp/cbor-codec.js): JavaScript implementation of [CBOR](http://cbor.io/) 
- [cryptobox-bower](https://github.com/wireapp/cryptobox-bower): Redistributables of Cryptobox
- [cryptobox.js](https://github.com/wireapp/cryptobox.js): API layer for Proteus
- [libsodium.js](https://github.com/wireapp/libsodium.js): JavaScript implementation of [Sodium](https://download.libsodium.org/doc/), with convenient wrappers 
- [proteus.js](https://github.com/wireapp/proteus.js): Implementation of the Axolotl protocol

### Dependencies

[cryptobox-bower](https://github.com/wireapp/cryptobox-bower) → [cryptobox.js](https://github.com/wireapp/cryptobox.js) → [proteus.js](https://github.com/wireapp/proteus.js) → [libsodium.js](https://github.com/wireapp/libsodium.js) & [cbor-codec.js](https://github.com/wireapp/cbor-codec.js)

## AVS

The audio, video, and signaling (AVS) library of Wire is developed in ANSI C/C++. The code is cross compiled for Android and iOS. Wrappers for interaction with upstream modules are written in Java for Android and Objective-C for iOS.

### Repositories

- [avs](https://github.com/wireapp/avs): Audio-video library for calling (mostly C), then cross compiled for iOS and Android

## Proteus/Cryptobox

The Axolotl protocol implementation and other cryptographic and utility libraries are developed in Rust, then cross-compiled for iOS and Android. The web version has its own port of these libraries in JavaScript.

### Repositories

- [proteus](https://github.com/wireapp/proteus): Axolotl Protocol Implementation in Rust, then cross compiled for iOS and Android
- [libsodium](https://github.com/wireapp/libsodium): A modern and easy-to-use crypto library. 
- [cryptobox](https://github.com/wireapp/cryptobox): High-level API with persistent storage for proteus
- [cryptobox-haskell](https://github.com/wireapp/cryptobox-haskell): Haskell bindings to cryptobox
- [cryptobox-c](https://github.com/wireapp/cryptobox-c): C-FFI to cryptobox 
- [hkdf](https://github.com/wireapp/hkdf): HKDF implementation (RFC 5869) in Rust, then cross compiled to iOS and Android

## Common definitions

Protocol buffer definitions are used by all clients to communicate with each other and with the backend.

### Repositories

- [generic-message-proto](https://github.com/wireapp/generic-message-proto): Protocol buffer definitions that are part of the cross-platform client communication protocol
- [backend-api-protobuf](https://github.com/wireapp/backend-api-protobuf): Protocol buffer definitions that are part of the backend communication protocol 

