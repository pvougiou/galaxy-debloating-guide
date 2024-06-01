# Debloating Guide for Samsung Galaxy S24
Simple commands for removing unnecessary Android apps, using Android Debug Bridge (`adb`). The current list of apps is by no means exhaustive, in its current shape, and I'll carry on updating it with new apps that can be safely removed.

Tested on:
- SM-S928B/DS
- One UI version: 6.1 (Android 14)

## Using `adb`

- Basic commands used for connecting to your device using `adb`
  ```sh
  adb shell  # connecting to your device
  pm list packages spotify  # searching for packages including "spotify" in their title
  ```

- List of apps that have been (hopefully!) safely removed as of now:
  ```sh
  # Removing Facebook
  pm uninstall --user 0 com.facebook.appmanager
  pm uninstall --user 0 com.facebook.services
  pm uninstall --user 0 com.facebook.system
  
  # Removing Samsung Pass
  pm uninstall --user 0 com.samsung.android.samsungpassautofill
  pm uninstall --user 0 com.samsung.android.samsungpass

  Disclaimer: The removal of the apps is still tentatively recommended since I haven't tested the phone long
  # enough after their original removal.

  # Removing Microsoft bloatware
  pm uninstall --user 0 com.microsoft.appmanager  # only useful in-case you'd like to link your phone to Windows
  pm uninstall --user 0 com.microsoft.skydrive  # removing Microsoft OneDrive

  # Removing Bixby services
  pm uninstall --user 0 com.samsung.android.bixby.wakeup
  pm uninstall --user 0 com.samsung.android.bixby.agent
  pm uninstall --user 0 com.samsung.android.app.settings.bixby
  ```

- Re-booting the device after we're done debloating:
  ```sh
  reboot
  ```

## References

For the original list of unnecessary apps, please refer to the following resources:

1. https://www.reddit.com/r/GalaxyS23Ultra/comments/153xua6/safely_debloating_our_s23_ultra
2. https://docs.google.com/spreadsheets/d/12jEGQftFUL3vAI03X0Ku1LgoWFQKdwPA_WHuLh_2ics/edit#gid=0
3. https://files.catbox.moe/cyf4t1.txt

