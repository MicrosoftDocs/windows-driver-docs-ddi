---
UID: NE:usbfnbase._USBFN_DEVICE_STATE
title: "_USBFN_DEVICE_STATE"
author: windows-driver-content
description: Defines the Universal Serial Bus (USB) device states for the device/controller. These states correspond to the USB device states as defined in section 9.1 of the USB 2.0 Specification.
old-location: buses\usbfn_device_state.htm
old-project: usbref
ms.assetid: B367D0F7-5026-4C88-B88A-69068F76B675
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: UsbfnDeviceStateMinimum, UsbfnDeviceStateConfigured, *PUSBFN_DEVICE_STATE, UsbfnDeviceStateAttached, usbfnbase/UsbfnDeviceStateDetached, usbfnbase/UsbfnDeviceStateSuspended, usbfnbase/UsbfnDeviceStateAttached, buses.usbfn_device_state, USBFN_DEVICE_STATE enumeration [Buses], usbfnbase/UsbfnDeviceStateDefault, usbfnbase/USBFN_DEVICE_STATE, UsbfnDeviceStateDetached, usbfnbase/UsbfnDeviceStateMinimum, UsbfnDeviceStateDefault, usbfnbase/UsbfnDeviceStateAddressed, usbfnbase/UsbfnDeviceStateStateMaximum, _USBFN_DEVICE_STATE, USBFN_DEVICE_STATE, usbfnbase/UsbfnDeviceStateConfigured, UsbfnDeviceStateStateMaximum, UsbfnDeviceStateAddressed, UsbfnDeviceStateSuspended
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: usbfnbase.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	usbfnbase.h
apiname:
-	USBFN_DEVICE_STATE
product: Windows
targetos: Windows
req.typenames: USBFN_DEVICE_STATE, *PUSBFN_DEVICE_STATE
req.product: Windows 10 or later.
---

# _USBFN_DEVICE_STATE enumeration


## -description


Defines the Universal Serial Bus (USB) device states for the device/controller.  These states correspond to the USB device states as defined in section 9.1 of the USB 2.0 Specification.


## -syntax


````
typedef enum _USBFN_DEVICE_STATE { 
  UsbfnDeviceStateMinimum       = 0x0,
  UsbfnDeviceStateAttached,
  UsbfnDeviceStateDefault,
  UsbfnDeviceStateDetached,
  UsbfnDeviceStateAddressed,
  UsbfnDeviceStateConfigured,
  UsbfnDeviceStateSuspended,
  UsbfnDeviceStateStateMaximum
} USBFN_DEVICE_STATE;
````


## -enum-fields




#### - UsbfnDeviceStateMinimum

The minimum value of the enumeration.


#### - UsbfnDeviceStateAttached

Device is attached to an upstream port.


#### - UsbfnDeviceStateDefault

Device is attached and connected to an upstream port but has not been reset.


#### - UsbfnDeviceStateDetached

Device is not attached to an upstream port.


#### - UsbfnDeviceStateAddressed

Device has been assigned a non-default USB address by the host.


#### - UsbfnDeviceStateConfigured

Device has been configured by the host.


#### - UsbfnDeviceStateSuspended

Device has been suspended.


#### - UsbfnDeviceStateStateMaximum

The maximum value of the enumeration.

