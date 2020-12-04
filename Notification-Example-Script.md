## Example notification script

Please note this is an example and you'll need to adjust the `notify` service for your Home Assistant setup.

```yaml
<doorname>_manual_notify:
  mode: parallel
  sequence:
    - service: notify.phones
      data:
        title: "{{ title }}"
        message: "{{ message }}"
```