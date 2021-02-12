# Troubleshooting

## Missing Sensors
If you are not seeing your `User Code`, `Access Control`, `Alarm Type`, or `Alarm Level`, please note in `ozw` and `zwave_js` they are disabled by default as the preferred method is to use the `Home Security` sensor. Enabling these sensors does not break anything and allows the automations to accurately process the lock information. If you can't find these sensors (enabled or disabled) and you are using the `zwave_js` integration, your lock notifications may be coming in as events and you can use `sensor.fake` when setting these sensor values during set up.

## Code Slots
The code slots are updated every 5 seconds internally in Home Assistant, this method does not poll the lock and wake it up resulting in battery drain.

## Unable to set codes
This usually occurs due to the `allow_automations` boolean being off. This should only turn off when your ZWave network is down or you've just restarted Home Assistant (only the old `zwave` integration). If it's showing as off, please check the [**pre-install instructions**](https://github.com/FutureTense/keymaster/wiki/Pre-Installation-Steps-(IMPORTANT)) page for corrections to automations to help resolve this.

## Entity not available messages
This usually occurs when you haven't added the `packages` configuration to your `configuration.yaml` file. Please [**see the pre-install instructions**](https://github.com/FutureTense/keymaster/wiki/Pre-Installation-Steps-(IMPORTANT)) on how to do that.

## Enable Debugging
This will be needed from time to time to get more data to find out what's going on. Navigate to `Dev-tools` -> `Services` tab in Home Assistant.
Select the service `logger.set_level` in data enter `custom_components.keymaster: debug` and press `Call Service`.
Your log will now start showing debug data in the Home Assistant log.

If you are missing the service `logger.set_level` this usually because `logger` wasn't added to your `configuration.yaml` add the following to enable this super useful service.

```yaml
logger:
  default: warning
```