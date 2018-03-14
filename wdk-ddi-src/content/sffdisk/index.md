---
UID: NA:sffdisk
ms.assetid: 0ffe1314-78d0-3840-8dbe-bec79732f0dd
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Sffdisk.h header



This header is used by SD. For more information, see
- [SD](../_SD/index.md)

Sffdisk.h contain these programming interfaces:


## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_SFFDISK_DEVICE_COMMAND IOCTL](ni-sffdisk-ioctl_sffdisk_device_command.md) | User-mode applications use this IOCTL to send Secure Digital (SD) card commands to an SD card. |
| [IOCTL_SFFDISK_DEVICE_PASSWORD IOCTL](ni-sffdisk-ioctl_sffdisk_device_password.md) | User-mode applications use this IOCTL to perform basic operations on a Secure Digital (SD) card, such as setting the password on the card, resetting the card, or locking and unlocking the card. |
| [IOCTL_SFFDISK_QUERY_DEVICE_PROTOCOL IOCTL](ni-sffdisk-ioctl_sffdisk_query_device_protocol.md) | User-mode applications use this IOCTL to retrieve a protocol value that identifies the card as either an SD card or an MMC card. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [SFFDISK_DCMD enumeration](ne-sffdisk-sffdisk_dcmd.md) | The SFFDISK_DCMD enumeration identifies the type of Secure Digital (SD) card operation. |
| [SFFDISK_DPCMD enumeration](ne-sffdisk-sffdisk_dpcmd.md) | The SFFDISK_DPCMD enumeration lists the operations performed by an IOCTL_SFFDISK_DEVICE_PASSWORD request. |
