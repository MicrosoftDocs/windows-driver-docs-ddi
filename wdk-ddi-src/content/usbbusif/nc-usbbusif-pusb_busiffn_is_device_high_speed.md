---
UID: NC:usbbusif.PUSB_BUSIFFN_IS_DEVICE_HIGH_SPEED
title: PUSB_BUSIFFN_IS_DEVICE_HIGH_SPEED (usbbusif.h)
description: The USB_BUSIFFN_IS_DEVICE_HIGH_SPEED routine returns TRUE if the device is operating at high speed.
old-location: buses\isdevicehighspeed.htm
tech.root: usbref
ms.date: 02/04/2022
keywords: ["PUSB_BUSIFFN_IS_DEVICE_HIGH_SPEED callback function"]
ms.keywords: IsDeviceHighSpeed, IsDeviceHighSpeed callback function [Buses], PUSB_BUSIFFN_IS_DEVICE_HIGH_SPEED, USB_BUSIFFN_IS_DEVICE_HIGH_SPEED, USB_BUSIFFN_IS_DEVICE_HIGH_SPEED callback, buses.isdevicehighspeed, usbbusif/IsDeviceHighSpeed, usbinterKR_eaf122ed-eee1-4924-a186-b0474b8c9816.xml
req.header: usbbusif.h
req.include-header: Usbbusif.h
req.target-type: Desktop
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
req.irql: < = DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PUSB_BUSIFFN_IS_DEVICE_HIGH_SPEED
 - usbbusif/PUSB_BUSIFFN_IS_DEVICE_HIGH_SPEED
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - usbbusif.h
api_name:
 - PUSB_BUSIFFN_IS_DEVICE_HIGH_SPEED
---

# PUSB_BUSIFFN_IS_DEVICE_HIGH_SPEED callback function

## -description

The USB_BUSIFFN_IS_DEVICE_HIGH_SPEED routine returns `TRUE` if the device  is operating at high speed.

## -syntax

```cpp
typedef BOOLEAN
  (USB_BUSIFFN *PUSB_BUSIFFN_IS_DEVICE_HIGH_SPEED) (
    IN PVOID
  );
```

## -parameters

### -param unnamedParam1 [in, optional]

Handle returned in the **BusContext** member of the [USB_BUS_INTERFACE_USBDI_V1](ns-usbbusif-_usb_bus_interface_usbdi_v1.md) structure by an IRP_MN_QUERY_INTERFACE request.

## -returns

USB_BUSIFFN_IS_DEVICE_HIGH_SPEED implementation returns `TRUE` if the USB device is operating at high speed USB 2.0 compliant device; `FALSE` otherwise.

## -remarks

## -see-also

- [USB_BUS_INTERFACE_USBDI_V1](ns-usbbusif-_usb_bus_interface_usbdi_v1.md)
