Are you interested in creating automations when your lock state changes from locked to unlocked? We try to provide some good defaults out of the box, but in case these don't meet your needs, feel free to build your own! You will want to use an `event` trigger for the `keymaster_lock_state_changed` event. The format of the event is as follows:

```json
{
  "lockname": "frontdoor",
  "state": "locked",
  "action_text": "Keypad Lock",
  "code_slot": 1,
  "code_slot_name": "Jack"
}
```

You can access these parameters in your conditions and actions for the automation by by using [trigger templates](https://www.home-assistant.io/docs/automation/templating/#event). For example, to use the name that's entered into the code slot that triggered the event, use `{{ trigger.event.data.code_slot_name }}`