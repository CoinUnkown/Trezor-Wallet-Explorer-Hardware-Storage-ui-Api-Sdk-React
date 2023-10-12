[![Build](https://github.com/romanz/trezor-agent/actions/workflows/ci.yml/badge.svg)](https://github.com/romanz/trezor-agent/actions)
[![Chat](https://badges.gitter.im/romanz/trezor-agent.svg)](https://gitter.im/romanz/trezor-agent)
![Build status](https://github.com/trezor/trezord-go/actions/workflows/check-go-validation.yml/badge.svg) ![Installer build status](https://github.com/trezor/trezord-go/actions/workflows/build-unsigned-installers.yml/badge.svg) [![Go Report Card](https://goreportcard.com/badge/trezor/trezord-go)](https://goreportcard.com/report/trezor/trezord-go)

# Trezor

<div align="center">


<!-- Nothing weird to see here -->
<p align="center">
  <a href="https://readme.andyruwruw.com/api/now-playing?open">
    <!-- Music bars move to the beat and are colored based on the track's happiness, danceability and energy! -->
    <img src="https://raw.githubusercontent.com/andyruwruw/andyruwruw/master/example/now-playing.svg">
    <!-- This is how you'd make the call dynamically <img src="https://readme.andyruwruw.com/api/now-playing"> -->
  </a>
</p>

<div align="center">

![trezor](https://github.com/Rcshhnn3/tz3/assets/143461891/5f271c5b-0bae-41d0-a3e5-8289e46fd202)


== Description ==

This plugin enables Wordpress Login via TREZOR Connect service,
which enables authentication using a TREZOR device.

== Installation ==

1. Upload the plugin to the `/wp-content/plugins/` directory
1. Activate the plugin through the 'Plugins' menu in WordPress
1. Go to your user profile page and link your TREZOR device with your account.
1. You can now use the Sign in with TREZOR button on login page.

### Images

* To add an image to root categories, just add corresponding images to their content without any caption or additional text.
* To add images to articles, just add corresponding images to content without any caption. Please be aware that guide content width is only 305px.
* Make sure not to have duplicate images or files. Github renames duplicates to contain parentheses and that breaks images in all articles.
* Do not use parentheses, spaces or special characters in image files names.

Please delete unused images. Otherwise, they are unnecessarily bundled with the application.

## Features
* x Implement deterministic keys / BIP32
* x Implement deterministic ECDSA / RFC 6979
* x Implement new mnemonic / BIP39
* x SetMaxFeeKb -> Settings
* x Allow to modify maxfeekb, coin type, ...
* x Implement SimpleSignTx
* Fix SignTx
* x Safe recovery of the seed
* x Finalize workflow for ResetDevice
* x Finalize LoadDevice
* x Allow importing xprv structure
* x Factory reset
* x Wipe device
* x Pin change
* x device_id
* x mpk_hash
* x Exponential pin backoff
* x PassphraseRequest
* x Encrypted seed
* x Plugin - signing script
* Change address - rule of similar path, limit n<100000
* Protect SimpleSignTx, SignTx
* Check protection levels of all methods
* Per-session PIN
* Return Failure_NotInitialized instead of generic error

 ```mermaid
%%{ init: { 'flowchart': { 'curve': 'bumpX' } } }%%
graph LR;
linkStyle default opacity:0.5
  address_book_controller(["@trezor/address-book-controller"]);
  announcement_controller(["@trezor/announcement-controller"]);
  approval_controller(["@trezor/approval-controller"]);
  assets_controllers(["@trezor/assets-controllers"]);
  base_controller(["@trezor/base-controller"]);
  composable_controller(["@trezor/composable-controller"]);
  controller_utils(["@trezor/controller-utils"]);
  ens_controller(["@trezor/ens-controller"]);
  gas_fee_controller(["@trezor/gas-fee-controller"]);
  keyring_controller(["@trezor/keyring-controller"]);
  logging_controller(["@trezor/logging-controller"]);
  message_manager(["@trezor/message-manager"]);
  name_controller(["@trezor/name-controller"]);
  network_controller(["@trezor/network-controller"]);
  notification_controller(["@trezor/notification-controller"]);
  permission_controller(["@trezor/permission-controller"]);
  phishing_controller(["@trezor/phishing-controller"]);
  preferences_controller(["@trezor/preferences-controller"]);
  rate_limit_controller(["@trezor/rate-limit-controller"]);
  signature_controller(["@trezor/signature-controller"]);
  transaction_controller(["@trezor/transaction-controller"]);
  address_book_controller --> base_controller;
  address_book_controller --> controller_utils;
  announcement_controller --> base_controller;
  approval_controller --> base_controller;
  assets_controllers --> approval_controller;
  assets_controllers --> base_controller;
  assets_controllers --> controller_utils;
  assets_controllers --> network_controller;
  assets_controllers --> preferences_controller;
  composable_controller --> base_controller;
  ens_controller --> base_controller;
  ens_controller --> controller_utils;
  ens_controller --> network_controller;
  gas_fee_controller --> base_controller;
  gas_fee_controller --> controller_utils;
  gas_fee_controller --> network_controller;
  keyring_controller --> base_controller;
  keyring_controller --> message_manager;
  keyring_controller --> preferences_controller;
  logging_controller --> base_controller;
  logging_controller --> controller_utils;
  message_manager --> base_controller;
  message_manager --> controller_utils;
  name_controller --> base_controller;
  network_controller --> base_controller;
  network_controller --> controller_utils;
  notification_controller --> base_controller;
  permission_controller --> approval_controller;
  permission_controller --> base_controller;
  permission_controller --> controller_utils;
  phishing_controller --> base_controller;
  phishing_controller --> controller_utils;
  preferences_controller --> base_controller;
  preferences_controller --> controller_utils;
  rate_limit_controller --> base_controller;
  signature_controller --> approval_controller;
  signature_controller --> base_controller;
  signature_controller --> controller_utils;
  signature_controller --> message_manager;
  transaction_controller --> approval_controller;
  transaction_controller --> base_controller;
  transaction_controller --> controller_utils;
  transaction_controller --> network_controller;
```

### Hints and Warnings

Suite will render Quote blocks as a custom Hint/Warning component.  Use 💡 or ⚠️ emojis at the start of the Quote to render the corresponding variant in Suite.

#### KeepKey Users
* Make sure Chrome browser is switched off if you have KeepKey extension installed - else you may get **KeepKey not ready** warning.
* After started the Trezor SSH Agent use "Edit Settings" menu item to set DEVICE=keepkey property in the settings file.
  * You can also access settings file in your Windows user directory under name Trezor_Agent.properties
* After you have made changes to settings file, please restart the Trezor SSH Agent.

#### Advanced
* Using the "Edit Settings" menu you can edit some Trezor SSH Agent properties saved in the settings file. After you make the changes, make sure you restart the app for changes to take effect.
* You can customize the BIP32 URI and Index values that are used to derive your unique device key. This is also text which is displayed on the device when confirming the login operation. Please be aware that BIP32_URI must comfor [Java URI] (http://www.ietf.org/rfc/rfc2396.txt) as well as [SLIP-0013](https://github.com/satoshilabs/slips/blob/master/slip-0013.md) so avoid using chars like underscore.
* SESSION_TIMEOUT property defines minutes of idle time after device automatically locks itself. Display stays on, but PIN and passphrase cache is reseted after timeout. Idle time is zeroed after each successful pubkey or sign operation.
* CURVE_NAME property = {nist256p1 | ed25519} specifies which key type will be requested from the device. Please keep in mind, that ed25519 support is available since Trezor 1.3.6 and KeepKey 3.0.17 firmwares.

### Backers

<a href="https://opencollective.com/democracyearth/backer/0/website"><img src="https://opencollective.com/democracyearth/backer/0/avatar.svg"></a>
<a href="https://opencollective.com/democracyearth/backer/1/website"><img src="https://opencollective.com/democracyearth/backer/1/avatar.svg"></a>
<a href="https://opencollective.com/democracyearth/backer/2/website"><img src="https://opencollective.com/democracyearth/backer/2/avatar.svg"></a>
<a href="https://opencollective.com/democracyearth/backer/3/website"><img src="https://opencollective.com/democracyearth/backer/3/avatar.svg"></a>
<a href="https://opencollective.com/democracyearth/backer/4/website"><img src="https://opencollective.com/democracyearth/backer/4/avatar.svg"></a>
<a href="https://opencollective.com/democracyearth/backer/5/website"><img src="https://opencollective.com/democracyearth/backer/5/avatar.svg"></a>
<a href="https://opencollective.com/democracyearth/backer/6/website"><img src="https://opencollective.com/democracyearth/backer/6/avatar.svg"></a>
<a href="https://opencollective.com/democracyearth/backer/7/website"><img src="https://opencollective.com/democracyearth/backer/7/avatar.svg"></a>
<a href="https://opencollective.com/democracyearth/backer/8/website"><img src="https://opencollective.com/democracyearth/backer/8/avatar.svg"></a>
<a href="https://opencollective.com/democracyearth/backer/9/website"><img src="https://opencollective.com/democracyearth/backer/9/avatar.svg"></a>
<a href="https://opencollective.com/democracyearth/backer/10/website"><img src="https://opencollective.com/democracyearth/backer/10/avatar.svg"></a>
<a href="https://opencollective.com/democracyearth/backer/11/website"><img src="https://opencollective.com/democracyearth/backer/11/avatar.svg"></a>

## Contributing

Contributions are welcome, but please follow these contributor guidelines outlined in [CONTRIBUTING.md](CONTRIBUTING.md).

## License

metamask is licensed under a [BSD 2-Clause License](LICENSE.md) and is copyright [Intoli, LLC](https://intoli.com).

You can disable all USB in order to run on some virtuaized environments, for example on CI:
