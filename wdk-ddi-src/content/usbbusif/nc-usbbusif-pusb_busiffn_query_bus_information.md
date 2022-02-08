---
UID: NC:usbbusif.PUSB_BUSIFFN_QUERY_BUS_INFORMATION
title: PUSB_BUSIFFN_QUERY_BUS_INFORMATION (usbbusif.h)
description: The QueryBusInformation routine gets information about the bus.
old-location: buses\querybusinformation.htm
tech.root: usbref
ms.date: 02/04/2022
keywords: ["PUSB_BUSIFFN_QUERY_BUS_INFORMATION callback function"]
ms.keywords: PUSB_BUSIFFN_QUERY_BUS_INFORMATION, QueryBusInformation, QueryBusInformation callback function [Buses], USB_BUSIFFN_QUERY_BUS_INFORMATION, USB_BUSIFFN_QUERY_BUS_INFORMATION callback, buses.querybusinformation, usbbusif/QueryBusInformation, usbinterKR_91d1f7ee-5cd2-4f87-bc4c-16972039f5e3.xml
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
 - PUSB_BUSIFFN_QUERY_BUS_INFORMATION
 - usbbusif/PUSB_BUSIFFN_QUERY_BUS_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - usbbusif.h
api_name:
 - PUSB_BUSIFFN_QUERY_BUS_INFORMATION
---

# PUSB_BUSIFFN_QUERY_BUS_INFORMATION callback function

## -description

The **QueryBusInformation** routine gets information about the bus.

## -syntax

```cpp
typedef NTSTATUS
  (USB_BUSIFFN *PUSB_BUSIFFN_QUERY_BUS_INFORMATION) (
    IN PVOID,
    IN ULONG,
    IN OUT PVOID,
    IN OUT PULONG,
    OUT PULONG
  );
```

## -parameters

### -param unnamedParam1 [in]

Handle returned in the **BusContext** member of the <a href="/windows-hardware/drivers/ddi/usbbusif/ns-usbbusif-_usb_bus_interface_usbdi_v0">USB_BUS_INTERFACE_USBDI_V0</a> structure by an IRP_MN_QUERY_INTERFACE request.

### -param unnamedParam2 [out, optional]

Specifies the length of the output data.

### -param unnamedParam3 [in, out]

Pointer to a buffer that receives the requested bus information.

### -param unnamedParam4 [out]

On input, the length of the buffer specified by *BusInformationBuffer*. On output, the length of the output data. 

### -param unnamedParam5 [in]

Specifies the level of information to be returned. If *Level* is 0, the function returns the total bandwidth and the total consumed bandwidth in bits per second. If *Level* is 1, the function returns the symbolic name of the controller in Unicode, in addition to the total bandwidth and the total consumed bandwidth.

## -returns

**QueryBusInformation** returns one of the following values:

| Return code | Description |
| --- | --- |
| `STATUS_SUCCESS` | The call completed successfully. |
| `STATUS_BUFFER_TOO_SMALL` | The buffer was too small. This error code is returned in two cases:</br></br>Whenever *Level* == 0, this error code is returned if the size of the buffer pointed to by *BusInformationBuffer* is less than the size of the [USB_BUS_INFORMATION_LEVEL_0](ns-usbbusif-_usb_bus_information_level_0.md) structure.</br></br>Whenever Level == 1, this error code is returned if the size of the buffer pointed to by *BusInformationBuffer* less than the size of the [USB_BUS_INFORMATION_LEVEL_1](ns-usbbusif-_usb_bus_information_level_1.md) structure. |

## -remarks

The exact information returned by this routine depends on the value of the *Level* parameter. This routine replaces the **USBD_QueryBusInformation** library function provided by usbd.sys.

## -see-also

- [USB_BUS_INFORMATION_LEVEL_0](ns-usbbusif-_usb_bus_information_level_0.md)
- [USB_BUS_INFORMATION_LEVEL_1](ns-usbbusif-_usb_bus_information_level_1.md)
- [USB_BUS_INTERFACE_USBDI_V0](ns-usbbusif-_usb_bus_interface_usbdi_v0.md)
