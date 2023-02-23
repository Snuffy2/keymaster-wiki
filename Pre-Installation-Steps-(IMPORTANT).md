## Before installing

You will need to add to your `configuration.yaml` the following lines (if you have this already you can skip this step):

```yaml
homeassistant:
  packages: !include_dir_named packages
```

You will also need to create the `packages` directory in your Home Assistant configuration directory (the directory that contains `configuration.yaml`).
