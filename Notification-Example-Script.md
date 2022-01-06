## Example notification script

Please note this is an example and you'll need to adjust the `notify` service for your Home Assistant setup.

```yaml
keymaster_<doorname>_manual_notify:
  mode: parallel
  sequence:
    - service: notify.phones
      data:
        title: "{{ title }}"
        message: "{{ message }}"
```

The script should be created in [![Open your Home Assistant instance and show your scripts.](https://my.home-assistant.io/badges/scripts.svg)](https://my.home-assistant.io/redirect/scripts/)