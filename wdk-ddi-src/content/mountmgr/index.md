---
UID: NA:mountmgr
ms.assetid: f85c530f-35d6-36ba-99e3-5ed06a65e9c8
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Mountmgr.h header



This header is used by Storage. For more information, see
- [Storage](../_storage/index.md)

Mountmgr.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [_MOUNTDEV_NAME structure](ns-mountmgr-_mountdev_name.md) | The MOUNTDEV_NAME structure holds the name of a device. |
| [_MOUNTMGR_CHANGE_NOTIFY_INFO structure](ns-mountmgr-_mountmgr_change_notify_info.md) | The MOUNTMGR_CHANGE_NOTIFY_INFO structure is used by the mount manager to send epic numbers to its clients and vice versa. |
| [_MOUNTMGR_CREATE_POINT_INPUT structure](ns-mountmgr-_mountmgr_create_point_input.md) | The MOUNTMGR_CREATE_POINT_INPUT structure is used by the mount manager to send a symbolic link name to a client that has requested symbolic link name by means of an IOCTL_MOUNTMGR_CREATE_POINT request. |
| [_MOUNTMGR_DRIVE_LETTER_INFORMATION structure](ns-mountmgr-_mountmgr_drive_letter_information.md) | The MOUNTMGR_DRIVE_LETTER_INFORMATION structure is used by the mount manager to furnish a drive letter to a client that has requested a driver letter by means of an IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER request. |
| [_MOUNTMGR_DRIVE_LETTER_TARGET structure](ns-mountmgr-_mountmgr_drive_letter_target.md) | The MOUNTMGR_DRIVE_LETTER_TARGET structure is used by a mount manager client with an IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER request to furnish a nonpersistent target device name to the mount manager. |
| [_MOUNTMGR_MOUNT_POINT structure](ns-mountmgr-_mountmgr_mount_point.md) | The MOUNTMGR_MOUNT_POINT structure is used by mount manager clients in conjunction with an IOCTL_MOUNTMGR_QUERY_POINTS request to query the mount manager for all of the mount points (symbolic links) associated with a device. |
| [_MOUNTMGR_MOUNT_POINTS structure](ns-mountmgr-_mountmgr_mount_points.md) | The MOUNTMGR_MOUNT_POINTS structure is used by mount manager to send a client the list of mount points associated with a device. |
| [_MOUNTMGR_TARGET_NAME structure](ns-mountmgr-_mountmgr_target_name.md) | The MOUNTMGR_TARGET_NAME structure contains the nonpersistent target device name for a device and is used by mount manager clients with the IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE request to tell the mount manager to keep the symbolic link for a device active even after the device has gone offline. |
| [_MOUNTMGR_VOLUME_MOUNT_POINT structure](ns-mountmgr-_mountmgr_volume_mount_point.md) | The MOUNTMGR_VOLUME_MOUNT_POINT structure is used in conjunction with the IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_CREATED request to inform the mount manager that a volume mount point has been created. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_MOUNTDEV_QUERY_DEVICE_NAME IOCTL](ni-mountmgr-ioctl_mountdev_query_device_name.md) | Support for this IOCTL by the mount manager clients is mandatory. |
| [IOCTL_MOUNTMGR_AUTO_DL_ASSIGNMENTS IOCTL](ni-mountmgr-ioctl_mountmgr_auto_dl_assignments.md) | This IOCTL informs the mount manager that it should assign drive letters to volumes automatically as they are introduced in the system. |
| [IOCTL_MOUNTMGR_CHANGE_NOTIFY IOCTL](ni-mountmgr-ioctl_mountmgr_change_notify.md) | Clients send this IOCTL to the mount manager to be informed whenever there is a change in the mount manager's persistent symbolic link name database. |
| [IOCTL_MOUNTMGR_CHECK_UNPROCESSED_VOLUMES IOCTL](ni-mountmgr-ioctl_mountmgr_check_unprocessed_volumes.md) | When a volume arrives in the system, it registers for the MOUNTDEV_MOUNTED_DEVICE_GUID interface class and the mount manager receives a Plug and Play notification (see Mount Manager I/O Control Codes for a discussion of this process). |
| [IOCTL_MOUNTMGR_CREATE_POINT IOCTL](ni-mountmgr-ioctl_mountmgr_create_point.md) | The mount manager clients can use this IOCTL to request that the mount manager create a persistent symbolic link name for the indicated volume. |
| [IOCTL_MOUNTMGR_DELETE_POINTS IOCTL](ni-mountmgr-ioctl_mountmgr_delete_points.md) | This IOCTL is identical in input and output to IOCTL_MOUNTMGR_QUERY_POINTS. The difference is that IOCTL_MOUNTMGR_DELETE_POINTS has the side effect of deleting the symbolic links and the mount manager database entries for the triples returned. |
| [IOCTL_MOUNTMGR_DELETE_POINTS_DBONLY IOCTL](ni-mountmgr-ioctl_mountmgr_delete_points_dbonly.md) | This IOCTL is identical in input and output to IOCTL_MOUNTMGR_QUERY_POINTS. |
| [IOCTL_MOUNTMGR_KEEP_LINKS_WHEN_OFFLINE IOCTL](ni-mountmgr-ioctl_mountmgr_keep_links_when_offline.md) | This IOCTL directs the mount manager to keep a symbolic link active after the Plug and Play manager has given notification that its corresponding volume has gone offline. |
| [IOCTL_MOUNTMGR_NEXT_DRIVE_LETTER IOCTL](ni-mountmgr-ioctl_mountmgr_next_drive_letter.md) | This IOCTL checks to see if the given volume has a drive letter. |
| [IOCTL_MOUNTMGR_QUERY_POINTS IOCTL](ni-mountmgr-ioctl_mountmgr_query_points.md) | This IOCTL returns triples that consist of a persistent symbolic link name for the volume (that is, a mount point), a unique ID for the volume, and a nonpersistent device name (such as &#0034;\Device\HarddiskVolume1&#0034;) for the volume. |
| [IOCTL_MOUNTMGR_VOLUME_ARRIVAL_NOTIFICATION IOCTL](ni-mountmgr-ioctl_mountmgr_volume_arrival_notification.md) | This IOCTL allows a client to simulate a Plug and Play device interface arrival notification with the given volume name. |
| [IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_CREATED IOCTL](ni-mountmgr-ioctl_mountmgr_volume_mount_point_created.md) | This IOCTL alerts the mount manager that a volume mount point has been created, so that the mount manager can replicate the database entry for the given mount point. |
| [IOCTL_MOUNTMGR_VOLUME_MOUNT_POINT_DELETED IOCTL](ni-mountmgr-ioctl_mountmgr_volume_mount_point_deleted.md) | The mount manager clients use this IOCTL to alert the mount manager that a volume mount point has been deleted so that the mount manager can replicate the database entry for the given mount point. |
