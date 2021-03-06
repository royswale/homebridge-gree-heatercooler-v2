# homebridge-gree-heatercooler-v2

![version](https://img.shields.io/npm/v/homebridge-gree-heatercooler-v2) ![license](https://img.shields.io/npm/l/homebridge-gree-heatercooler-v2)

Homebridge plugin for Gree air conditioners.

## Install

```shell
$ npm install -g homebridge-gree-heatercooler-v2
```

## Config Example

```json
{
  "bridge": {
    "name": "Homebridge",
    "username": "CC:22:3D:E3:CE:30",
    "port": 51826,
    "pin": "031-45-154"
  },
  "accessories": [
    {
      "accessory": "GreeHeaterCooler",
      "address": "10.0.1.128",
      "model": "KFR-35GW(35592)FNhAc-A1(WIFI)",
      "name": "Living Room AC",
      "serialNumber": "4R0099H012345",
      "minimumTargetTemperature": 16,
      "maximumTargetTemperature": 30,
      "fakeSensor": false,
      "sensorOffset": 0,
      "updateInterval": 1000,
      "retryInterval": 5000
    }
  ]
}
```

### Params

* `accessory`: Accessory name to load. Not compatible with other plugins with the same name.
* `address`: Local IP address of the AC unit. It has to be connected to local network before using this plugin.
* `model`, `name`, `serialNumber`: Information of the AC unit. Does not affect functions.
* `minimumTargetTemperature`, `maximumTargetTemperature`: (in °C) Range of target temperature supported by the AC unit. May vary depending on your model.
* `fakeSensor`: (true | false) For those models without built-in temperature sensor. This option enables a fake sensor using target temperature as current. Use of this option disables detection of whether AC is actively heating/cooling or being idle at target temperature.
* `sensorOffset`: (0 or 40) Some models have an offset of 40 on temperature sensor to avoid negative values. If the temperature shown is abnormally high, set it to `40`.
* `updateInterval`: (in ms) Interval for refreshing current status of the AC unit.
* `retryInterval`: (in ms) Retry interval when connnection fails.

## License

This project is released under the terms and conditions of the [GPL license](https://www.gnu.org/licenses/#GPL). See [LICENSE](/LICENSE) for details.

## Contact

This project is designed and developed by [Elethom Hunter](http://github.com/Elethom). You can reach me via:

* Email: elethomhunter@gmail.com
* Telegram: [@elethom](http://telegram.me/elethom)

## Credits

* Based on: [gree-remote](https://github.com/tomikaa87/gree-remote)
* Inspired by: [homebridge-gree-heatercooler](https://github.com/ddenisyuk/homebridge-gree-heatercooler)
