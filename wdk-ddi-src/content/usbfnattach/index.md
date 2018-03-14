---
UID: NA:usbfnattach
ms.assetid: f153fba1-6817-3150-8868-0ae60962b0ac
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Usbfnattach.h header



This header is used by Universal Serial Bus(USB). For more information, see
- [Universal Serial Bus(USB)](../_usbref/index.md)

Usbfnattach.h contain these programming interfaces:


## Callback functions

| Title   | Description   |
| ---- |:---- |
| [USBFN_GET_ATTACH_ACTION callback](nc-usbfnattach-usbfn_get_attach_action.md) | The filter driver's implementation that gets invoked when charger is attached to the port. |
| [USBFN_GET_ATTACH_ACTION_ABORT callback](nc-usbfnattach-usbfn_get_attach_action_abort.md) | The filter driver's implementation to abort an attach-detect operation. |
| [USBFN_SET_DEVICE_STATE callback](nc-usbfnattach-usbfn_set_device_state.md) | The filter driver's implementation to set the device state and operating bus speed. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_USBFN_INTERFACE_ATTACH structure](ns-usbfnattach-_usbfn_interface_attach.md) | Stores pointers to driver-implemented callback functions for handling attach and detach operations. |
| [_USBFN_ON_ATTACH structure](ns-usbfnattach-_usbfn_on_attach.md) | Describes the detected port type and attach action. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_USBFN_ATTACH_ACTION enumeration](ne-usbfnattach-_usbfn_attach_action.md) | Defines the actions that the Universal Serial Bus (USB) function stack takes when a device is attached to a USB port. |
