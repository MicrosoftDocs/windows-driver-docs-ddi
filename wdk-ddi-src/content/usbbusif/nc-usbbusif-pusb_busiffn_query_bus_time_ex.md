---
UID: NC:usbbusif.PUSB_BUSIFFN_QUERY_BUS_TIME_EX
title: PUSB_BUSIFFN_QUERY_BUS_TIME_EX (usbbusif.h)
description: The QueryBusTimeEx routine gets the current 32-bit USB micro-frame number.
old-location: buses\querybustimeex.htm
tech.root: usbref
ms.date: 02/04/2022
keywords: ["PUSB_BUSIFFN_QUERY_BUS_TIME_EX callback function"]
ms.keywords: PUSB_BUSIFFN_QUERY_BUS_TIME_EX, QueryBusTimeEx, QueryBusTimeEx callback function [Buses], USB_BUSIFFN_QUERY_BUS_TIME_EX, USB_BUSIFFN_QUERY_BUS_TIME_EX callback, buses.querybustimeex, usbbusif/QueryBusTimeEx
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
 - PUSB_BUSIFFN_QUERY_BUS_TIME_EX
 - usbbusif/PUSB_BUSIFFN_QUERY_BUS_TIME_EX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - usbbusif.h
api_name:
 - PUSB_BUSIFFN_QUERY_BUS_TIME_EX
---

# PUSB_BUSIFFN_QUERY_BUS_TIME_EX callback function

## -description

This request is not supported.

The **QueryBusTimeEx** routine gets the current 32-bit USB micro-frame number.

## -syntax

```cpp
typedef NTSTATUS
  (USB_BUSIFFN *PUSB_BUSIFFN_QUERY_BUS_TIME_EX) (
    IN PVOID,
    IN PULONG
  );
```

## -parameters

### -param unnamedParam1 [in]

Handle returned in the **BusContext** member of the [USB_BUS_INTERFACE_USBDI_V3](ns-usbbusif-_usb_bus_interface_usbdi_v3.md) structure by an IRP_MN_QUERY_INTERFACE request.

### -param unnamedParam2 [out]

Receives the current USB micro-frame number.

## -returns

**QueryBusTimeEx** returns one of the following values:

| Return code            | Description                                                                      |
|------------------------|----------------------------------------------------------------------------------|
| `STATUS_SUCCESS`       | The call completed successfully.                                                 |
| `STATUS_NOT_SUPPORTED` | The function was called for a USB host controller that does not support USB 2.0. |

## -remarks

**QueryBusTimeEx** gets the current USB 2.0 frame/micro-frame number when called for a USB device attached to a USB 2.0 host controller.  

The lowest 3 bits of the returned micro-frame value will contain the current 125us micro-frame, while the upper 29 bits will contain the current 1ms USB frame number.

## -see-also

- [USB_BUS_INTERFACE_USBDI_V3](ns-usbbusif-_usb_bus_interface_usbdi_v3.md)
