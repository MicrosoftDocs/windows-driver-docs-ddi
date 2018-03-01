---
UID: NA:mountdev
ms.assetid: be9fed45-a126-3ee3-a8af-d3afa08baea2
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Mountdev.h header



This header is used by Storage. For more information, see
- [Storage](../_storage/index.md)

Mountdev.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [_MOUNTDEV_SUGGESTED_LINK_NAME structure](ns-mountdev-_mountdev_suggested_link_name.md) | Mount manager clients that are able to keep track of their drive letters use this structure to request that the mount manager assign them a particular link name. |
| [_MOUNTDEV_UNIQUE_ID structure](ns-mountdev-_mountdev_unique_id.md) | The MOUNTDEV_UNIQUE_ID structure contains a unique volume ID that a mount manager client provides to the mount manager in response to an IOCTL_MOUNTDEV_QUERY_UNIQUE_ID request. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_MOUNTDEV_LINK_CREATED IOCTL](ni-mountdev-ioctl_mountdev_link_created.md) | Support for this IOCTL by the mount manager clients is optional. The mount manager uses this IOCTL to alert the client driver that a persistent name has been assigned to its volume. The input for this IOCTL is the persistent name assigned. |
| [IOCTL_MOUNTDEV_LINK_DELETED IOCTL](ni-mountdev-ioctl_mountdev_link_deleted.md) | Support for this IOCTL by the mount manager clients is optional. It alerts the mount manager client that a persistent name associated with it has been deleted. The input for this IOCTL is the persistent name that was deleted. |
| [IOCTL_MOUNTDEV_QUERY_SUGGESTED_LINK_NAME IOCTL](ni-mountdev-ioctl_mountdev_query_suggested_link_name.md) | Support for this IOCTL by the mount manager clients is optional. |
| [IOCTL_MOUNTDEV_QUERY_UNIQUE_ID IOCTL](ni-mountdev-ioctl_mountdev_query_unique_id.md) | Support for this IOCTL by mount manager clients is mandatory. |
