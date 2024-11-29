## Add the lovelace code

If all goes well, you will also see a new directory (by default `<your config directory/custom_components/keymaster/lovelace>`) for each lock with a `yaml` lovelace file. So if you add two integrations, one with FrontDoor and the other with BackDoor, you should see two YAML files with those names. Open that file in a text editor and select the entire contents and copy to the clipboard.

> (Open file) Ctrl-A (select all) Ctrl-C (copy)

Open Home Assistant and open the LoveLace editor by clicking the ellipses on the top right of the screen, and then select "Configure UI" or "Edit Dashboard". Click the ellipses again and click "Raw config editor". Scroll down to the bottom of the screen and then paste your clipboard. This will paste a new View for your lock. Click the Save button then click the X to exit.
