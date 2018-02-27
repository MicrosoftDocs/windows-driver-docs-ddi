---
UID: NA:ntddtape
ms.assetid: d256bd60-5dd4-3212-aedd-dbf0a73383e6
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Ntddtape.h header



This header is used by Storage. For more information, see
- [Storage](../_storage/index.md)

Ntddtape.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [_TAPE_CREATE_PARTITION structure](ns-ntddtape-_tape_create_partition.md) | The TAPE_CREATE_PARTITION structure is used in conjunction with the IOCTL_TAPE_CREATE_PARTITION request to create a specified number of fixed, select, or initiator partitions of a given size on the tape media. |
| [_TAPE_ERASE structure](ns-ntddtape-_tape_erase.md) | The TAPE_ERASE structure is used in conjunction with the IOCTL_TAPE_ERASE request to erase the current tape partition. |
| [_TAPE_GET_DRIVE_PARAMETERS structure](ns-ntddtape-_tape_get_drive_parameters.md) | The TAPE_GET_DRIVE_PARAMETERS structure is used in conjunction with the IOCTL_TAPE_GET_DRIVE_PARAMS request to retrieve information about capabilities of the tape drive. |
| [_TAPE_GET_MEDIA_PARAMETERS structure](ns-ntddtape-_tape_get_media_parameters.md) | The TAPE_GET_MEDIA_PARAMETERS structure is used in conjunction with the TapeMiniGetMediaParameters routine to retrieve tape media parameters. |
| [_TAPE_GET_POSITION structure](ns-ntddtape-_tape_get_position.md) | The TAPE_GET_POSITION structure is used in conjunction with the IOCTL_TAPE_GET_POSITION request to retrieve the current absolute, logical, or pseudological partition and offset position on the tape. |
| [_TAPE_PREPARE structure](ns-ntddtape-_tape_prepare.md) | The TAPE_PREPARE structure is used in conjunction with the IOCTL_TAPE_PREPARE request to load or unload tape, reset the tape's tension, lock or unlock the ejection mechanism, or format the tape. |
| [_TAPE_SET_DRIVE_PARAMETERS structure](ns-ntddtape-_tape_set_drive_parameters.md) | The TAPE_SET_DRIVE_PARAMETERS structure is used in conjunction with the IOCTL_TAPE_SET_DRIVE_PARAMS request to adjust the configurable parameters of a tape drive. |
| [_TAPE_SET_MEDIA_PARAMETERS structure](ns-ntddtape-_tape_set_media_parameters.md) | The TAPE_SET_MEDIA_PARAMETERS structure is used in conjunction with the IOCTL_TAPE_SET_MEDIA_PARAMS request to reset the block size of the media in a tape drive. |
| [_TAPE_SET_POSITION structure](ns-ntddtape-_tape_set_position.md) | The TAPE_SET_POSITION structure is used in conjunction with the IOCTL_TAPE_SET_POSITION request to move the current position on the tape to the specified partition and offset. |
| [_TAPE_WMI_OPERATIONS structure](ns-ntddtape-_tape_wmi_operations.md) | The tape miniclass driver passes this structure to its TapeMiniWMIControl routine to indicate which WMI operation must be performed by the device. |
| [_TAPE_WRITE_MARKS structure](ns-ntddtape-_tape_write_marks.md) | The TAPE_WRITE_MARKS structure is used in conjunction with an IOCTL_TAPE_WRITE_MARKS request to write a setmark, a filemark, a short filemark, or a long filemark to tape. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_TAPE_CREATE_PARTITION IOCTL](ni-ntddtape-ioctl_tape_create_partition.md) | Creates the specified number of fixed, select, or initiator partition(s) of the given size on the media. |
| [IOCTL_TAPE_ERASE IOCTL](ni-ntddtape-ioctl_tape_erase.md) | Erases the current tape partition, either as a TAPE_ERASE_LONG (in other words, a &#0034;secure&#0034;) operation that overwrites data with a pattern or as a TAPE_ERASE_SHORT (in other words, a &#0034;quick&#0034;) operation that writes an end-of-recorded-data mark at the current position. |
| [IOCTL_TAPE_GET_DRIVE_PARAMS IOCTL](ni-ntddtape-ioctl_tape_get_drive_params.md) | Returns information about the tape drive's capabilities, such as its default block size, maximum and minimum block sizes, maximum partition count, whether the drive has EEC, compression, data padding, and report-setmark capabilities, that is, which configurable features the drive supports, including the EOT warning zone size. |
| [IOCTL_TAPE_GET_MEDIA_PARAMS IOCTL](ni-ntddtape-ioctl_tape_get_media_params.md) | Returns information about the media's total and remaining capacity, its block size, the number of partitions, and whether it is write-protected. |
| [IOCTL_TAPE_GET_POSITION IOCTL](ni-ntddtape-ioctl_tape_get_position.md) | Returns the current absolute, logical, or pseudological partition and offset position on the tape. |
| [IOCTL_TAPE_GET_STATUS IOCTL](ni-ntddtape-ioctl_tape_get_status.md) | Returns the current status of the drive in the Status field of the I/O status block. |
| [IOCTL_TAPE_PREPARE IOCTL](ni-ntddtape-ioctl_tape_prepare.md) | Loads or unloads the tape, resets tape tension, locks or unlocks the ejection mechanism, or formats the tape. |
| [IOCTL_TAPE_SET_DRIVE_PARAMS IOCTL](ni-ntddtape-ioctl_tape_set_drive_params.md) | Adjusts a tape drive's configurable parameters. |
| [IOCTL_TAPE_SET_MEDIA_PARAMS IOCTL](ni-ntddtape-ioctl_tape_set_media_params.md) | Resets the block size of the media in the drive. |
| [IOCTL_TAPE_SET_POSITION IOCTL](ni-ntddtape-ioctl_tape_set_position.md) | Moves the current position on the tape to the specified partition and offset, according to the given method. |
| [IOCTL_TAPE_WRITE_MARKS IOCTL](ni-ntddtape-ioctl_tape_write_marks.md) | Writes one of setmarks, filemarks, short filemarks, or long filemarks to tape. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_TAPE_DRIVE_PROBLEM_TYPE enumeration](ne-ntddtape-_tape_drive_problem_type.md) | The TAPE_DRIVE_PROBLEM_TYPE enumerator is used to report problems with the tape drive. |
