# xiaomi-vacuum-card

Simple card for Xiaomi (and some other) robot vaccums in Home Assistant's Lovelace UI

[![GH-release](https://img.shields.io/badge/version-2.4.0-red.svg?style=flat-square)](https://raw.githubusercontent.com/benct/lovelace-xiaomi-vacuum-card/master/xiaomi-vacuum-card.js)
[![GH-last-commit](https://img.shields.io/github/last-commit/benct/lovelace-xiaomi-vacuum-card.svg?style=flat-square)](https://github.com/benct/lovelace-xiaomi-vacuum-card/commits/master)
[![GH-code-size](https://img.shields.io/github/languages/code-size/benct/lovelace-xiaomi-vacuum-card.svg?style=flat-square)](https://github.com/benct/lovelace-xiaomi-vacuum-card)
[![hacs_badge](https://img.shields.io/badge/HACS-Default-orange.svg)](https://github.com/custom-components/hacs)

## Setup

Install using [HACS](https://hacs.xyz/), or add [xiaomi-vacuum-card.js](https://raw.githubusercontent.com/benct/lovelace-xiaomi-vacuum-card/master/xiaomi-vacuum-card.js)
to your `<config>/www/` folder and add the following to your `ui-lovelace.yaml` file:

```yaml
resources:
  - url: /local/xiaomi-vacuum-card.js?v=2.4.0
    type: module
```
If you want to use the vacuum background image, add [img/vacuum.png](https://raw.githubusercontent.com/benct/lovelace-xiaomi-vacuum-card/master/img/vacuum.png)
to `<config>/www/img/`.

Using HACS, you might need to set the `image` config to something like `/local/community/lovelace-xiaomi-vacuum-card/vacuum.png`.

## Options

| Name | Type | Default | Description
| ---- | ---- | ------- | -----------
| type | string | **Required** | `custom:xiaomi-vacuum-card`
| entity | string | **Required** | `vacuum.my_xiaomi_vacuum`
| name | string/bool | `friendly_name` | Override entity friendly name (set to `false` to hide title)
| image | string/bool | `/local/img/vacuum.png` | Custom path/name of background image (set to `false` to disable background)
| buttons | object/bool | *(see below)* | Set to `false` to hide button row
| labels | object/bool | *(see below)* | Set to `false` to hide details/labels

### Buttons object

| Name | Type | Default | Description
| ---- | ---- | ------- | -----------
| start | bool | `true` | Show or hide start button
| pause | bool | `true` | Show or hide pause button
| stop | bool | `true` | Show or hide stop button
| spot | bool | `false` | Show or hide clean spot button
| locate | bool | `true` | Show or hide locate button
| return | bool | `true` | Show or hide return to home button

### Labels object

Customize or translate label names.

| Name | Type | Default | Description
| ---- | ---- | ------- | -----------
| status | string | `Status` | Change status label
| battery | string | `Battery` | Change battery label
| mode | string | `Mode` | Change mode label
| main_brush | string | `Main Brush` | Change main brush label
| side_brush | string | `Side Brush` | Change side brush label
| filter | string | `Filter` | Change filter label
| sensor | string | `Sensor` | Change sensor label
| hours | string | `h` | Change hours label

### Other vendors

This card was originally written for Xiaomi (Roborock) vacuum cleaners, but version `2.0` and later has added support for some other vendors too.
If you think any more vendors should be added, feel free to open an issue or contribute directly with a PR.

| Name | Type | Default | Description
| ---- | ---- | ------- | -----------
| vendor | string | `xiaomi` | Supported vendors: `xiaomi`, `valetudo`, `ecovacs`, `deebot`, `robovac`

*Note: Vendor `ecovacs` and `robovac` shows the clean spot button instead of the stop button by default*

## Examples

![xiaomi-vacuum-card](https://raw.githubusercontent.com/benct/lovelace-xiaomi-vacuum-card/master/examples/default.png)

Hidden title/name

![xiaomi-vacuum-card-no-title](https://raw.githubusercontent.com/benct/lovelace-xiaomi-vacuum-card/master/examples/no-title.png)

Hidden button row

![xiaomi-vacuum-card-no-buttons](https://raw.githubusercontent.com/benct/lovelace-xiaomi-vacuum-card/master/examples/no-buttons.png)

No background image

![xiaomi-vacuum-card-no-background](https://raw.githubusercontent.com/benct/lovelace-xiaomi-vacuum-card/master/examples/no-background.png)

```yaml
- type: custom:xiaomi-vacuum-card
  entity: vacuum.xiaomi_vacuum_cleaner
  image: /local/custom/folder/background.png
  name: Xiaomi Vacuum
  buttons: true
  labels:
    status: Etat
    battery: Batterie
    mode: Puissance
    main_brush: Brosse Principale
    side_brush: Brosse Latérale
    filter: Filtre
    sensor: Capteurs
```

## Disclaimer

This project is not affiliated, associated, authorized, endorsed by, or in any way officially connected with the Xiaomi Corporation, or any of its subsidiaries or its affiliates. The official Xiaomi website can be found at https://www.mi.com/global/.

## My cards

[xiaomi-vacuum-card](https://github.com/benct/lovelace-xiaomi-vacuum-card) | 
[github-entity-row](https://github.com/benct/lovelace-github-entity-row) | 
[multiple-entity-row](https://github.com/benct/lovelace-multiple-entity-row) | 
[attribute-entity-row](https://github.com/benct/lovelace-attribute-entity-row)

[![BMC](https://www.buymeacoffee.com/assets/img/custom_images/white_img.png)](https://www.buymeacoff.ee/benct)
