---
UID: NA:usbprint
ms.assetid: d4ccb935-1ce5-3e92-bd28-a309ad34ad92
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Usbprint.h header



This header is used by print. For more information, see
- [print](../_print/index.md)

Usbprint.h contain these programming interfaces:


## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_USBPRINT_GET_1284_ID IOCTL](ni-usbprint-ioctl_usbprint_get_1284_id.md) | The IOCTL_USBPRINT_GET_1284_ID control code allows upper-layer software (such as a language monitor), to request and obtain the printer's IEEE 1284 device ID string. |
| [IOCTL_USBPRINT_GET_LPT_STATUS IOCTL](ni-usbprint-ioctl_usbprint_get_lpt_status.md) | The IOCTL_USBPRINT_GET_LPT_STATUS request allows upper-layer software (such as a language monitor), to request and obtain the printer status byte from a USB printer. |
| [IOCTL_USBPRINT_SOFT_RESET IOCTL](ni-usbprint-ioctl_usbprint_soft_reset.md) | The IOCTL_USBPRINT_SOFT_RESET request allows upper-layer software (such as a language monitor), to issue a class-specific soft reset command to the printer. |
| [IOCTL_USBPRINT_VENDOR_GET_COMMAND IOCTL](ni-usbprint-ioctl_usbprint_vendor_get_command.md) | The IOCTL_USBPRINT_VENDOR_GET_COMMAND request allows upper-layer software (such as a language monitor), to issue a vendor-specific GET command to the target device. |
| [IOCTL_USBPRINT_VENDOR_SET_COMMAND IOCTL](ni-usbprint-ioctl_usbprint_vendor_set_command.md) | The IOCTL_USBPRINT_VENDOR_SET_COMMAND request allows upper-layer software (such as a language monitor) to issue a vendor-specific SET command to the target device. |
