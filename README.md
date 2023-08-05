# CamON-to-HA
A restful-based Home Assistant integration of selected sensors and switches provided by [CamON Live Streaming app](https://play.google.com/store/apps/details?id=com.spynet.camon&hl=en&gl=US), installed on Android phone.

# Why use this integration?
- If you don't want to install official HA companion app for some reason, but still want to know battery level of the phone.
- Torch works!

# Available entities
## sensor
- camonlive_battery
- camonlive_model
- camonlive_serial
- camonlive_id
- camonlive_version
## binary_sensor
- camonlive_charging
# switch
- camonlive_torch

# Available commands (via HA rest_command service)
- camonlive_torch_on
- camonlive_torch_off
- camonlive_autofocus
- camonlive_zoom_in
- camonlive_zoom_out

# How to install
1. Edit the content of packages/camonlive.yaml and modify the IP address to the where CamON Live Streaming app is running
2. Copy the "packages" dir to your Home Assistant's root directory
3. Add the following line to your configuration.yaml:
```
  packages: !include_dir_named packages
```
4. Restart HA

# Issues
- Only one target IP address (hardcoded) supported
- The data is polled from sensors once a minute, which means there could be a big lag between eg. the moment you switch the torch on and when you observe the entity state actually change.

# No support
I've created this integration for my own usage and decided to share. Although it's not perfect, I do not plan on improving it. But if you think you can, feel free to build from it.
