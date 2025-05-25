+++
title = "4. System Backups"
description = "A how-to tutorial on using Timeshift, a built-in backup & restore tool for Blade OS."
weight = 2
+++

# Timeshift
Blade OS comes with the built in **Timeshift** app, which allows administrators to backup & restore their system with ease.

## Setup Wizzard
If you're using the app for the first time, you'll be met with the setup wizzard.

### Snapshot Type
There's two types of snapshots you can use:

### RSYNC
The slow & recommended way.
* Any drive or partition with a Linux filesystem (Other filesystem's aren't supported)
* Allows the system to be restored if disk is damaged or reformatted
* Full copy of the installed system
* Files & directories can be excluded to save space

### BTRFS
Fast but limiting.
* Using the built-in features of the filesystem
* Created & restored instantly
* Nothing is excluded
* Can only be backed-up on the system partition

{{< tip >}} Blade OS comes with the **btrfs** filesystem by default. If you installed Blade OS using a different filesystem, RSYNC will be your only option. {{< /tip >}}

![Snapshot Type](../../../images/docs/v24/ts-snapshotType.png)

In this guide, we'll be using the **btrfs** type. Things may vary on snapshot type.

### Snapshot Location
You can change the location on where snapshots are stored here.
![Snapshot Location](../../../images/docs/v24/ts-snapshotLocation.png)

### Automatic Backups
You can change the behavior of automatic backups here.

{{< tip "warning" >}} It is highly recommended that you have at least one way of automatic backup in case your system breaks. {{< /tip >}}

![Automatic Backups](../../../images/docs/v24/ts-autoBackup.png)

### Directory Setup
You can include user home directories in backups if wanted. For **rsync** backups, you can include or exclude specific files & directories.

{{< tip >}} You can re-configure these by going into the app settings or clicking **Wizzard** in the main menu at anytime. {{< /tip >}}

## Using Timeshift
Using Timeshift is straightforward. You can create a snapshot at anytime by pressing the **Create** button. You can add a comment by clicking on it's section. To restore a snapshot, Select a snapshot and click **Restore**. Note that restoring a snapshot may take awhile. After the snapshot is restored, restart your system to apply changes.
You can also browse the snapshot files by clicking on **Browse**.
![Timeshift Main Menu](../../../images/docs/v24/ts-mainMenu.png)

## Restoring from a Live System
In the case of your system being broken, You can restore a snapshot through a live medium of Blade OS or another Linux distribution. Open the **Timeshift** app on the live system. You may have to manually install it depending on the distribution your currently using. Make sure all the settings are correct, then select a snapshot to restore. Press the **Restore** button to start the process.
![Timeshift Live Mode](../../../images/docs/v24/ts-liveMode.png)
*Timeshift running in Live Mode on a pre-release version of Blade OS.*

And that's how to use Timeshift. Enjoy backing up & restoring your system!