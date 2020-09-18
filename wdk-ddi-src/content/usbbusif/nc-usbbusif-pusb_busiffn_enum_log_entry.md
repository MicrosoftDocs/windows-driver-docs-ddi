---
UID: NC:usbbusif.PUSB_BUSIFFN_ENUM_LOG_ENTRY
title: USB_BUSIFFN_ENUM_LOG_ENTRY (usbbusif.h)
description: This callback function is not supported.The EnumLogEntry routine makes a log entry.
old-location: buses\enumlogentry.htm
tech.root: usbref
ms.assetid: 6c7f1ab6-bbd8-45d8-92af-030db336c97c
ms.date: 02/24/2018
keywords: ["PUSB_BUSIFFN_ENUM_LOG_ENTRY callback"]
ms.keywords: EnumLogEntry, EnumLogEntry callback function [Buses], USB_BUSIFFN_ENUM_LOG_ENTRY, buses.enumlogentry, usbbusif/EnumLogEntry, usbinterKR_a05ba50b-df81-4211-918b-e7409bc1d5ff.xml
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
req.irql: ANY
targetos: Windows
req.typenames: USBD_VERSION_INFORMATION, *PUSBD_VERSION_INFORMATION
req.product: Windows 10 or later.
f1_keywords:
 - PUSB_BUSIFFN_ENUM_LOG_ENTRY
 - usbbusif/PUSB_BUSIFFN_ENUM_LOG_ENTRY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - usbbusif.h
api_name:
 - EnumLogEntry
---

# PUSB_BUSIFFN_ENUM_LOG_ENTRY callback


## -description

This callback function is not supported.

The <i>EnumLogEntry</i> routine makes a log entry.

## -parameters

#### - BusContext [in]

Handle to the bus context returned in the <i>BusContext</i> member of the <a href="..\usbbusif\ns-usbbusif-_usb_bus_interface_usbdi_v2.md">USB_BUS_INTERFACE_USBDI_V2</a> structure by an IRP_MN_QUERY_INTERFACE request.


#### - DriverTag [in]


#### - EnumTag [in]

Vendor-defined data to store in the enumeration log.


#### - P1 [in]

Vendor-defined data to store in the enumeration log.


#### - P2 [in]

Vendor-defined data to store in the enumeration log.

## -returns

The <i>EnumLogEntry </i>routine always returns STATUS_SUCCESS.

## -prototype

```cpp
USB_BUSIFFN_ENUM_LOG_ENTRY EnumLogEntry;

NTSTATUS EnumLogEntry(
  _In_ PVOID BusContext,
  _In_ ULONG DriverTag,
  _In_ ULONG EnumTag,
  _In_ ULONG P1,
  _In_ ULONG P2
)
{ ... }
```

## -remarks

The routine definition that is provided on this reference page is an example routine whose parameters are just placeholder names. The actual prototype of the routine is declared in <i>usbbusif.h</i> as follows:


```
typedef NTSTATUS
  (USB_BUSIFFN *PUSB_BUSIFFN_ENUM_LOG_ENTRY) (
    IN PVOID,
    IN ULONG,
    IN ULONG,
    IN ULONG,
    IN ULONG
);
```


