## **NOTE: These steps are only needed for v0.0.22 and earlier. If you are on a later version, you can skip these steps**

***


## Before installing

You will need to add to your `configuration.yaml` the following lines (if you have this already you can skip this step):

```yaml
homeassistant:
  packages: !include_dir_named packages
```

You will also need to create the `packages` directory in your Home Assistant configuration directory (the directory that contains `configuration.yaml`).

## Additional entities required

Before your lock will respond to automations, you will need to create `input_boolean.allow_automation_execution` and a few template sensors  These are used _extensivly_ throught the project.  When Home Assistant starts up, several of keymaster’s automations will be called, which if you have notifications on will send unnecessary notifications. The allow_automations boolean will prevent those automations from firing.  When Home Assistant is finished loading, the allow_automations should be turned on, allowing keymaster automations to execute.

We have found the best way to add these entities and associated automations is to create a new directory in your `packages` directory called `additional_yaml` and add one of the following files from the repository into this directory, choosing the file matching your Z-Wave Network.

## Z-Wave JS Package File:
[assets/additional_yaml/zwave_js.yaml](https://github.com/FutureTense/keymaster/raw/main/assets/additional_yaml/zwave_js.yaml)

## OZW Package File:

[assets/additional_yaml/ozw.yaml](https://github.com/FutureTense/keymaster/raw/main/assets/additional_yaml/ozw.yaml)

## ZWave Package File:

[assets/additional_yaml/zwave.yaml](https://github.com/FutureTense/keymaster/raw/main/assets/additional_yaml/zwave.yaml)