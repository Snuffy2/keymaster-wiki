## Add the lovelace code

If all goes well, you will also see a new directory (by default `<your config directory/packages/keymaster/>`) for each lock with `yaml` and a lovelace files. So if you add two integrations, one with FrontDoor and the other with BackDoor, you should see two directories with those names. Inside of each of those directories will be a file called `<lockname>_lovelace`. Open that file in a text editor and select the entire contents and copy to the clipboard.

> (Open file) Ctrl-A (select all) Ctrl-C (copy)

Open Home Assistant and open the LoveLace editor by clicking the elipses on the top right of the screen, and then select "Configure UI". Click the elipses again and click "Raw config editor". Scroll down to the bottom of the screen and then paste your clipboard. This will paste a new View for your lock. Click the Save button then click the X to exit.

In order for the lovelace ui to work properly you will need to install the following modules.
1. [lovelace-auto-entities](https://github.com/thomasloven/lovelace-auto-entities)
2. [lovelace-card-tools](https://github.com/thomasloven/lovelace-card-tools)
3. [lovelace-fold-entity-row](https://github.com/thomasloven/lovelace-fold-entity-row)

The easiest way to install these modules is via [Home Assistant Community Store(HACS)](https://hacs.xyz/docs/categories/plugins).