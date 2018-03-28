---
UID: NA:ntddvol
ms.assetid: 8e87c3d1-6f05-3860-b49c-2ea9e281b96f
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Ntddvol.h header



This header is used by Storage. For more information, see
- [Storage](../_storage/index.md)

Ntddvol.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [_DISK_EXTENT structure](ns-ntddvol-_disk_extent.md) | The DISK_EXTENT structure contains information defining the location and length of a volume extent on a disk. |
| [_VOLUME_DISK_EXTENTS structure](ns-ntddvol-_volume_disk_extents.md) | The VOLUME_DISK_EXTENTS structure is used in conjunction with the IOCTL_VOLUME_GET_VOLUME_DISK_EXTENTS request to retrieve information about all the extents on a given volume. |
| [_VOLUME_LOGICAL_OFFSET structure](ns-ntddvol-_volume_logical_offset.md) | The VOLUME_LOGICAL_OFFSET structure contains a logical offset into a volume. |
| [_VOLUME_PHYSICAL_OFFSET structure](ns-ntddvol-_volume_physical_offset.md) | The VOLUME_PHYSICAL_OFFSET structure contains a physical offset into a volume and its accompanying physical disk number and is used with IOCTL_VOLUME_PHYSICAL_TO_LOGICAL and IOCTL_VOLUME_LOGICAL_TO_PHYSICAL to request a logical offset equivalent of a physical offset or a physical offset equivalent of a logical offset, respectively. |
| [_VOLUME_PHYSICAL_OFFSETS structure](ns-ntddvol-_volume_physical_offsets.md) | The VOLUME_PHYSICAL_OFFSETS structure contains an array of physical offsets and accompanying physical disk numbers and is used with IOCTL_VOLUME_LOGICAL_TO_PHYSICAL to request a series of pairs of physical offsets and disk numbers that correspond to a single logical offset. |
| [_VOLUME_READ_PLEX_INPUT structure](ns-ntddvol-_volume_read_plex_input.md) | This structure is used in conjunction with IOCTL_VOLUME_READ_PLEX to read data from a specific plex in a volume. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_VOLUME_GET_VOLUME_DISK_EXTENTS IOCTL](ni-ntddvol-ioctl_volume_get_volume_disk_extents.md) | Returns the physical location(s) of a volume on one or more disks. |
| [IOCTL_VOLUME_IS_CLUSTERED IOCTL](ni-ntddvol-ioctl_volume_is_clustered.md) | Allows a driver or application to determine if a volume is clustered. |
| [IOCTL_VOLUME_LOGICAL_TO_PHYSICAL IOCTL](ni-ntddvol-ioctl_volume_logical_to_physical.md) | Returns physical offsets and physical disk numbers for a given volume logical offset. |
| [IOCTL_VOLUME_OFFLINE IOCTL](ni-ntddvol-ioctl_volume_offline.md) | The IOCTL_VOLUME_OFFLINE IOCTL puts the volume in an OFFLINE state, which is a state where read and write operations will fail. |
| [IOCTL_VOLUME_ONLINE IOCTL](ni-ntddvol-ioctl_volume_online.md) | The IOCTL_VOLUME_ONLINE IOCTL puts the volume in an ONLINE state, which is a state where read and write operations will be executed. |
| [IOCTL_VOLUME_PHYSICAL_TO_LOGICAL IOCTL](ni-ntddvol-ioctl_volume_physical_to_logical.md) | Returns the logical offset corresponding to a physical disk number and a physical offset. |
| [IOCTL_VOLUME_READ_PLEX IOCTL](ni-ntddvol-ioctl_volume_read_plex.md) | Performs a read on a specific plex of a volume. |
