## Install keymaster via HACS

This integration can be added to your installation manually, but the *supported* method requires you to use The [Home Assistant Community Store](https://community.home-assistant.io/t/custom-component-hacs/121727). If you dont't already have HACS, it is [simple to install](https://hacs.xyz/docs/setup/prerequisites/).

Open HACS and select the Integrations tab. Click the + icon at the bottom right and search for `keymaster`. You will then get a message that the integration requires Home Assistant to be restarted. Please do so.

You need to create an integration for each lock you want to control. Select Configuration | Integrations. Click the + icon at the bottom right and search for **keymaster** and select it.

If the integration **_does not_** show up when searching, press `F5` from the integration screen to refresh the list of integrations. 

The integration UI will prompt you for several values. Below we are using the default entity names that are created for a Schlage BE469 lock.

***
## What you'll see

***IMAGE PENDING UPDATE***

<img src="https://github.com/FutureTense/keymaster/raw/main/docs/integration_screen_wiki.png" alt="Integration Screen" />

#### 1. **Parent lock**

Use this to make this lock a `child` of the specified `parent` lock. This will copy all of the names/PIN/settings from the parent to this lock. Any changes made to the parent lock will happen on this lock allowing you to manage multiple locks from one location. 

#### 2. **Z-Wave lock**
    
Use the dropdown and select your Z-Wave lock. The default for Schlage looks like `lock.be469zp_connect_smart_deadbolt_locked`, this drop down will only show available lock devices.

#### 3. **Code slots**

The number of code slots or PINS you want to manage. The maximum number is dependant upon your lock. Don't create more slots than you will actually need, because too many can slow your lovelace UI down.

#### 4. **Start from code slot #** 

Unless you are using an `ID Brand` lock or a lock where the user codes do not start at slot 1, leave this as the default `1`, otherwise `ID Brand` locks start at around user code 50 due to RFID/Bluetooth/etc codes.

#### 5. **Lock Name**

Give your lock a name that will be used in notifications, e.g. *frontdoor*

#### 6. **Door Sensor**

If your lock has a sensor that determines if the door is opened/closed, select it here. The Schlage doesn't have one but you can use a third party sensor or specify any sensor here.

#### 7. **User Code Sensor**

This sensor returns the slot number for a user that just entered their lock PIN. Schlage value: `sensor.be469zp_connect_smart_deadbolt_user_code`

#### 8. **Access Control Sensor**

This sensor returns the command number just executed by the lock. Schlage value: `sensor.be469zp_connect_smart_deadbolt_access_control`    
