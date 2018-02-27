---
UID: NA:hidport
ms.assetid: a158f664-a913-37af-9370-c18096783d37
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Hidport.h header



This header is used by Human Interface Devices (HID). For more information, see
- [Human Interface Devices (HID)](../_hid/index.md)

This section describes the system-supplied routines that user-mode applications, kernel-mode drivers, and HID minidrivers use to operate devices in the HIDClass device setup class.

As a general rule, user-mode applications can use the HidD_Xxx and HidP_Xxx routines. However, kernel-mode drivers can only call HidP_Xxx routines. 

HID minidrivers use only the HidRegisterMinidriver routine.

For Windows 8.1 Microsoft introduced the new Windows.Devices.HumanInterfaceDevice API which lets you write Windows apps that  access HID devices.

The header  defines  IOCTLs that a HID minidriver must support. Only the HID class driver sends these IOCTLs to a HID minidriver. User-mode applications and other kernel-mode  drivers can  only communicate with HID collections by using the HIDClass support routines and HID class driver ioctls.

## Related topics

Send comments about this topic to Microsoft

