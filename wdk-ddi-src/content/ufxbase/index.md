---
UID: NA:ufxbase
ms.assetid: 852c4c2e-5b6d-36ca-9232-1ebba63ec849
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Ufxbase.h header



This header is used by Universal Serial Bus(USB). For more information, see
- [Universal Serial Bus(USB)](../_usbref/index.md)

Ufxbase.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [_UFX_DEVICE_CAPABILITIES structure](ns-ufxbase-_ufx_device_capabilities.md) | The UFX_DEVICE_CAPABILITIES structure is used USB to define properties of the Universal Serial Bus (USB) device created by the controller. |
| [_UFX_HARDWARE_FAILURE_CONTEXT structure](ns-ufxbase-_ufx_hardware_failure_context.md) | The UFX_HARDWARE_FAILURE_CONTEXT structure is used to define controller-specific hardware failure properties. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_INTERNAL_USBFN_DESCRIPTOR_UPDATE IOCTL](ni-ufxbase-ioctl_internal_usbfn_descriptor_update.md) | The USB function class extension sends this request to the client driver to update to the endpoint descriptor for the specified endpoint. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_USBFN_ACTION enumeration](ne-ufxbase-_usbfn_action.md) | Defines special actions UFX should take when the client driver calls the UfxDevicePortDetectCompleteEx function. |
