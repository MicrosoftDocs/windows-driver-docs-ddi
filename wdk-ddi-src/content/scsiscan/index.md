---
UID: NA:scsiscan
ms.assetid: fb5a05ac-d1d3-3550-a11a-67ef84846ede
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Scsiscan.h header



This header is used by Imaging devices. For more information, see
- [Imaging devices](../_image/index.md)

Scsiscan.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [_SCSISCAN_CMD structure](ns-scsiscan-_scsiscan_cmd.md) | The SCSISCAN_CMD structure is used as a parameter to DeviceIoControl, when the specified I/O control code is IOCTL_SCSISCAN_CMD. |
| [_SCSISCAN_INFO structure](ns-scsiscan-_scsiscan_info.md) | The SCSISCAN_INFO structure is used as a parameter to DeviceIoControl (described in the Microsoft Windows SDK documentation), when the specified I/O control code is IOCTL_SCSISCAN_GET_INFO. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_SCSISCAN_CMD IOCTL](ni-scsiscan-ioctl_scsiscan_cmd.md) | Creates a customized SCSI control descriptor block (CDB) and sends it to the kernel-mode still image driver for SCSI buses. |
| [IOCTL_SCSISCAN_GET_INFO IOCTL](ni-scsiscan-ioctl_scsiscan_get_info.md) | The IOCTL_SCSISCAN_GET_INFO I/O control code returns device information. |
| [IOCTL_SCSISCAN_LOCKDEVICE IOCTL](ni-scsiscan-ioctl_scsiscan_lockdevice.md) | Reserved for use by Microsoft. |
| [IOCTL_SCSISCAN_SET_TIMEOUT IOCTL](ni-scsiscan-ioctl_scsiscan_set_timeout.md) | The IOCTL_SCSISCAN_SET_TIMEOUT control code modifies the time-out value used by the kernel-mode still image driver for SCSI buses when it accesses a device. |
| [IOCTL_SCSISCAN_UNLOCKDEVICE IOCTL](ni-scsiscan-ioctl_scsiscan_unlockdevice.md) | Reserved for use by Microsoft. |
