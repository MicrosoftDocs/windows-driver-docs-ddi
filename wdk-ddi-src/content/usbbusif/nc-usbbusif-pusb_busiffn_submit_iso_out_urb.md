---
UID: NC:usbbusif.PUSB_BUSIFFN_SUBMIT_ISO_OUT_URB
title: PUSB_BUSIFFN_SUBMIT_ISO_OUT_URB (usbbusif.h)
description: This callback function is not supported.The SubmitIsoOutUrb function submits a USB request block (URB) directly to the bus driver without requiring the allocation of an IRP.
old-location: buses\submitisoouturb.htm
tech.root: usbref
ms.date: 02/04/2022
keywords: ["PUSB_BUSIFFN_SUBMIT_ISO_OUT_URB callback function"]
ms.keywords: PUSB_BUSIFFN_SUBMIT_ISO_OUT_URB, PUSB_BUSIFFN_SUBMIT_ISO_OUT_URB callback, SubmitIsoOutUrb, SubmitIsoOutUrb callback function [Buses], buses.submitisoouturb, usbbusif/SubmitIsoOutUrb, usbinterKR_7caf9f1e-d3e3-4d26-b91f-c2864594703a.xml
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
req.typenames: 
f1_keywords:
 - PUSB_BUSIFFN_SUBMIT_ISO_OUT_URB
 - usbbusif/PUSB_BUSIFFN_SUBMIT_ISO_OUT_URB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - usbbusif.h
api_name:
 - PUSB_BUSIFFN_SUBMIT_ISO_OUT_URB
---

# PUSB_BUSIFFN_SUBMIT_ISO_OUT_URB callback function

## -description

This callback function is not supported.

The *SubmitIsoOutUrb* function submits a USB request block (URB) directly to the bus driver without requiring the allocation of an IRP.

## -syntax

```cpp
typedef NTSTATUS
  (USB_BUSIFFN *PUSB_BUSIFFN_SUBMIT_ISO_OUT_URB) (
    IN PVOID,
    IN PURB
  );
```

## -parameters

### -param unnamedParam1 [in]

Handle returned in the *BusContext* member of the [USB_BUS_INTERFACE_USBDI_V0](ns-usbbusif-_usb_bus_interface_usbdi_v0.md) structure by an IRP_MN_QUERY_INTERFACE request.

### -param unnamedParam2 [in]

Pointer to the [URB](../usb/ns-usb-_urb.md) to be passed to the port driver.

## -returns

**SubmitIsoOutUrb** returns one of the following values:

| Return code            | Description                                                                                 |
|------------------------|---------------------------------------------------------------------------------------------|
| `STATUS_SUCCESS`       | The call completed successfully.                                                            |
| `STATUS_NOT_SUPPORTED` | Fast isochronous interfaces and real-time threads are not supported by the host controller. |

## -remarks

This function replaces the **USBD_BusSubmitIsoOutUrb** library function provided by *usbd.sys*.

This function allows clients running in real-time threads at an elevated IRQL to have rapid access to the bus driver. This USB host controller must support real-time threads for this function to work.

The calling driver forfeits any packet-level error information when calling this function.

## -seealso

- [USB_BUS_INTERFACE_USBDI_V0](ns-usbbusif-_usb_bus_interface_usbdi_v0.md)
- [URB](../usb/ns-usb-_urb.md)
