Title: Configuration Journey


# Configuration Journey 

When the web UI is accessed for the first time a series of configuration
dialogs will be displayed to the administrator. It can be cancelled using the
'skip' button in the top-right corner.

Below are the default windows and window sections that will appear.

^# MAAS (region) name
   ![conf journey step 1][conf-journey-step-1]

^# Connectivity (upstream DNS server, Ubuntu archives, and HTTP proxy)
   ![conf journey step 2][conf-journey-step-2]

^# Ubuntu images
   ![conf journey step 3][conf-journey-step-3]

^# SSH keys (for currently logged in user)
   ![conf journey step 4][conf-journey-step-4]

   Here, two keys appear because they were added when the administrator was
   created via the CLI.

^# Finished (next steps)
   ![conf journey step 5][conf-journey-step-5]


<!-- LINKS -->

[conf-journey-step-1]: ../media/installconfig-webui-conf-journey__region-name.png
[conf-journey-step-2]: ../media/installconfig-webui-conf-journey__connectivity.png
[conf-journey-step-3]: ../media/installconfig-webui-conf-journey__ubuntu-images.png
[conf-journey-step-4]: ../media/installconfig-webui-conf-journey__ssh-keys.png
[conf-journey-step-5]: ../media/installconfig-webui-conf-journey__successfully-setup.png
