# keymaster
Home Assistant keymaster integration for Z-Wave enabled locks. This integration allows you to control one (or more) Z-Wave enabled locks that have been added to your Z-Wave network. Besides being able to control your lock with lock/unlock commands, you can also control who may lock/unlock the device using the lock's front facing keypad. With the integration you may create multiple users or slots and each slot (the number depends upon the lock model) has its own PIN code.

Setting up a lock for the entire family can be accomplished in a matter of seconds. Did you just leave town and forgot to turn the stove off? through the Home Assistant interface you can create a new PIN instantly and give it to a neighbor and delete it later. Do you have house cleaners that come at specific times? With the advanced PIN settings you can create a slot that only unlocks on specific date and time ranges. You may also create slots that allow a number of entries, after which the lock won't respond to the PIN.

## Z-Wave JS

Currently, keymaster only supports locks setup with [`zwave_js`](https://www.home-assistant.io/integrations/zwave_js/).

Depending on the type of your home assistant installation, this may be as easy as using the [add-on store](https://www.home-assistant.io/addons/).  Or if you use docker, there is a [container for `zwave_js`](https://hub.docker.com/r/zwavejs/zwavejs2mqtt). Please review the [Community Guides](https://community.home-assistant.io/c/community-guides/51) for more information on how to get started.