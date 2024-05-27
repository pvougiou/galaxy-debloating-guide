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
  # Facebook
  pm uninstall --user 0 com.facebook.appmanager
  pm uninstall --user 0 com.facebook.services
  pm uninstall --user 0 com.facebook.system
  
  # Samsung Pass
  pm uninstall --user 0 com.samsung.android.samsungpassautofill
  pm uninstall --user 0 com.samsung.android.samsungpass
  ```

- Re-booting the device after we're done debloating:
  ```sh
  reboot
  ```

## References

1. https://www.reddit.com/r/GalaxyS23Ultra/comments/153xua6/safely_debloating_our_s23_ultra
2. https://docs.google.com/spreadsheets/d/12jEGQftFUL3vAI03X0Ku1LgoWFQKdwPA_WHuLh_2ics/edit#gid=0
3. https://files.catbox.moe/cyf4t1.txt

