#### How it works

The application makes heavy usage of `binary_sensor`. Each code slot in the system has it's own `Status` `binary_sensor`. Whenever the status of that sensor changes, the application will either **_add_** or **_remove_** the PIN associated with that slot from the lock. The `Status` sensor takes the results of the following binary_sensors and combines them using the `and` operator. Note, these sensors are not visible in the UI.

- Enabled
- Access Count
- Date Range
- Sunday
- Monday
- Tuesday
- Thursday
- Friday
- Saturday

**Enabled** This sensor is turned on and off by using the `Enabled` toggle in the UI. Anytime you modify the text of a PIN, this boolean toggle is turned off and must be manually turned on again to "activate" the PIN. By default, all of a slot's other UI elements are in the "always on" setting, so if you enable this boolean the PIN will be automatically added to the lock and remain that way until you turn the turn the toggle on again.

**Access Count** This sensor is controlled by the `Limit Access Count` toggle and the `Access Count` slider. If the toggle is turned on _and_ the value of the Access Count slider is greater than zero, this sensor will report true. Anytime this code slot is used to open a lock, the Access Count slider will be decremented by one. When the Access Count hits zero, this sensor is disabled and the PIN will be removed from the lock and will remain that way until you increase the Access Count slider or turn off the toggle.

**Date Range** This sensor, if enabled by it's boolean toggle will be enabled only if the current system date is between the dates specified in the date fields.

**Sunday - Saturday** These sensors are enabled by default. If you disable any of them, then the PIN won't work on that day. When enabled, the PIN will only work if the current system time falls between the specified time periods. If the periods are equal, then the PIN will work for the entire day.

### PIN Status
This sensor will show you the status as decribed below of the state of the PIN in regards to the lock and Home Assistant.

Status|Meaning
---|---
Connecting|PIN is trying to be added to the lock
Connected|PIN has been added to the lock and confirmed
Disconnecting|Code slot is trying to be cleared
Disconnected|Code slot has been cleared and confirmed
