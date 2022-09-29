---
UID: NC:usbbusif.PUSB_BUSIFFN_GETUSBDI_VERSION
title: PUSB_BUSIFFN_GETUSBDI_VERSION (usbbusif.h)
description: The GetUSBDIVersion routine returns the USB interface version number and the version number of the USB specification that defines the interface, along with information about host controller capabilities.
old-location: buses\getusbdiversion.htm
tech.root: usbref
ms.date: 02/04/2022
keywords: ["PUSB_BUSIFFN_GETUSBDI_VERSION callback function"]
ms.keywords: GetUSBDIVersion, GetUSBDIVersion callback function [Buses], PUSB_BUSIFFN_GETUSBDI_VERSION, USB_BUSIFFN_GETUSBDI_VERSION, USB_BUSIFFN_GETUSBDI_VERSION callback, buses.getusbdiversion, usbbusif/GetUSBDIVersion, usbinterKR_48f5b2a5-9cd8-46c2-abf9-313469817541.xml
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
 - PUSB_BUSIFFN_GETUSBDI_VERSION
 - usbbusif/PUSB_BUSIFFN_GETUSBDI_VERSION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - usbbusif.h
api_name:
 - PUSB_BUSIFFN_GETUSBDI_VERSION
---

# PUSB_BUSIFFN_GETUSBDI_VERSION callback function

## -description

The **GetUSBDIVersion** routine returns the USB interface version number and the version number of the USB specification that defines the interface, along with information about host controller capabilities.

> [!NOTE]
> [USBD_IsInterfaceVersionSupported](../usbdlib/nf-usbdlib-usbd_isinterfaceversionsupported.md) replaces the **GetUSBDIVersion** routine. To determine the capabilities of the host controller and the underlying USB driver stack, call [USBD_QueryUsbCapability](../usbdlib/nf-usbdlib-usbd_queryusbcapability.md).

## -syntax

```cpp
typedef VOID
  (USB_BUSIFFN *PUSB_BUSIFFN_GETUSBDI_VERSION) (
    IN PVOID,
    IN OUT PUSBD_VERSION_INFORMATION,
    IN OUT PULONG 
  );
```

## -parameters

### -param unnamedParam1 [in]

Handle returned in the **BusContext** member of the [USB_BUS_INTERFACE_USBDI_V0](ns-usbbusif-_usb_bus_interface_usbdi_v0.md) structure by an IRP_MN_QUERY_INTERFACE request.

### -param unnamedParam2 [out, optional]

Returns the host capability flags. Currently, no host capability flags are reported.

### -param unnamedParam3 [out, optional]

Returns a pointer to a [USBD_VERSION_INFORMATION](../usb/ns-usb-_usbd_version_information.md) structure that contains the USB interface version number and the USB specification version number.

## -remarks

The function returns the highest USBDI interface version supported by the port driver. This function replaces the [USBD_GetUSBDIVersion](../usbdlib/nf-usbdlib-usbd_getusbdiversion.md) library function provided by *usbd.sys*.

## -see-also

- [USBD_GetUSBDIVersion](../usbdlib/nf-usbdlib-usbd_getusbdiversion.md)
- [USBD_VERSION_INFORMATION](../usb/ns-usb-_usbd_version_information.md)
- [USB_BUS_INTERFACE_USBDI_V0](ns-usbbusif-_usb_bus_interface_usbdi_v0.md)
