# Wire™

[![Wire logo](https://github.com/wireapp/wire/blob/master/assets/header-small.png?raw=true)](https://wire.com/jobs/)

# Open source

The [privacy page](https://wire.com/privacy/) and the [privacy](https://wire.com/resource/Wire%20Privacy%20Whitepaper/download/) and [security](https://wire.com/resource/Wire%20Security%20Whitepaper/download/) whitepapers explain the details of the encryption algorithms and protocols used.

For licensing information, see the attached LICENSE file and the list of third-party licenses at [wire.com/legal/licenses/](https://wire.com/legal/licenses/).

If you compile the open source software that we make available from time to time to develop your own mobile, desktop or web application, and cause that application to connect to our servers for any purposes, we refer to that resulting application as an “Open Source App”.  All Open Source Apps are subject to, and may only be used and/or commercialized in accordance with, the Terms of Use applicable to the Wire Application, which can be found at https://wire.com/legal/#terms.  Additionally, if you choose to build an Open Source App, certain restrictions apply, as follows:

a. You agree not to change the way the Open Source App connects and interacts with our servers; b. You agree not to weaken any of the security features of the Open Source App; c. You agree not to use our servers to store data for purposes other than the intended and original functionality of the Open Source App; d. You acknowledge that you are solely responsible for any and all updates to your Open Source App. 

For clarity, if you compile the open source software that we make available from time to time to develop your own mobile, desktop or web application, and do not cause that application to connect to our servers for any purposes, then that application will not be deemed an Open Source App and the foregoing will not apply to that application.

No license is granted to the Wire trademark and its associated logos, all of which will continue to be owned exclusively by Wire Swiss GmbH. Any use of the Wire trademark and/or its associated logos is expressly prohibited without the express prior written consent of Wire Swiss GmbH.

# Build your own Wire client

## iOS
See [wire-ios](https://github.com/wireapp/wire-ios)

## Android
See [wire-android](https://github.com/wireapp/wire-android)

## Desktop
See [wire-desktop](https://github.com/wireapp/wire-desktop)

## Wire for Web
See [wire-webapp](https://github.com/wireapp/wire-webapp)

# Components

## AVS

The audio, video, and signaling (AVS) library of Wire is developed in ANSI C/C++. The code is cross compiled for Android and iOS. Wrappers for interaction with upstream modules are written in Java for Android and Objective-C for iOS.

### Repositories

- [avs](https://github.com/wireapp/avs): Audio-video library for calling (mostly C), then cross compiled for iOS and Android

## Proteus/Cryptobox

The Axolotl protocol implementation and other cryptographic and utility libraries are developed in Rust, then cross-compiled for iOS and Android. The web version has its own port of these libraries in JavaScript.

### Repositories

- [proteus](https://github.com/wireapp/proteus): Axolotl Protocol Implementation in Rust, then cross compiled for iOS and Android
- [cryptobox](https://github.com/wireapp/cryptobox): High-level API with persistent storage for proteus
- [cryptobox-haskell](https://github.com/wireapp/cryptobox-haskell): Haskell bindings to cryptobox
- [cryptobox-c](https://github.com/wireapp/cryptobox-c): C-FFI to cryptobox 
- [hkdf](https://github.com/wireapp/hkdf): HKDF implementation (RFC 5869) in Rust, then cross compiled to iOS and Android

## Server

The Wire server components can be found in the [wire-server](https://github.com/wireapp/wire-server) repository.

## Common definitions

Protocol buffer definitions are used by all clients to communicate with each other and with the backend.

### Repositories

- [generic-message-proto](https://github.com/wireapp/generic-message-proto): Protocol buffer definitions that are part of the cross-platform client communication protocol
- [backend-api-protobuf](https://github.com/wireapp/backend-api-protobuf): Protocol buffer definitions that are part of the backend communication protocol 

# Contributions

You can contribute to Wire in several ways:

## Finding bugs

If you find a bug in how Wire apps work, please submit a ticket to [our support](https://wire.com/support) and we will keep you informed about the progress.

## Contributing to the code

If you wish to contribute source code to one of our repositories you have to sign our [Contributor Agreement](https://github.com/wireapp/wire/raw/master/assets/Wire%20Contributor%20Agreement.pdf) first.

When you submit your first pull request, you can sign the agreement electronically by filling in the required information. You will not have to sign it again for subsequent pull requests from the same GitHub account.

## Translating the apps

You can help with the crowdsourced translations from Wire Apps on [Crowdin](https://crowdin.com/projects/wire).

