---
UID: NS:ucxusbdevice._USBDEVICE_ADDRESS
title: _USBDEVICE_ADDRESS (ucxusbdevice.h)
description: Contains parameters for a request to transition the specified device to the Addressed state. This structure is passed by UCX in request parameters (Parameters.Others.Arg1) of a framework request object of the EVT_UCX_USBDEVICE_ADDRESS callback function.
old-location: buses\_usbdevice_address.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["USBDEVICE_ADDRESS structure"]
ms.keywords: "*PUSBDEVICE_ADDRESS, P_USBDEVICE_ADDRESS, P_USBDEVICE_ADDRESS structure pointer [Buses], USBDEVICE_ADDRESS, USBDEVICE_ADDRESS structure [Buses], _USBDEVICE_ADDRESS, buses._usbdevice_address, ucxusbdevice/P_USBDEVICE_ADDRESS, ucxusbdevice/_USBDEVICE_ADDRESS"
req.header: ucxusbdevice.h
req.include-header: Ucxclass.h
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
req.irql: 
targetos: Windows
req.typenames: USBDEVICE_ADDRESS, *PUSBDEVICE_ADDRESS
f1_keywords:
 - _USBDEVICE_ADDRESS
 - ucxusbdevice/_USBDEVICE_ADDRESS
 - PUSBDEVICE_ADDRESS
 - ucxusbdevice/PUSBDEVICE_ADDRESS
 - USBDEVICE_ADDRESS
 - ucxusbdevice/USBDEVICE_ADDRESS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ucxusbdevice.h
api_name:
 - USBDEVICE_ADDRESS
---

# _USBDEVICE_ADDRESS structure


## -description

Contains parameters for a request to transition the specified device to the Addressed state. This structure is passed by UCX in request parameters (<b>Parameters.Others.Arg1</b>) of a framework request object of the <a href="/windows-hardware/drivers/ddi/ucxusbdevice/nc-ucxusbdevice-evt_ucx_usbdevice_address">EVT_UCX_USBDEVICE_ADDRESS</a> callback function.

## -struct-fields

### -field Header

A <a href="/windows-hardware/drivers/ddi/ucxusbdevice/ns-ucxusbdevice-_usbdevice_mgmt_header">USBDEVICE_MGMT_HEADER</a> structure that contains  the handle for the USB hub or device.

### -field Reserved

Do not use.

### -field Address

The address of the specified the USB hub or device.

## -see-also

<a href="/windows-hardware/drivers/ddi/ucxusbdevice/nc-ucxusbdevice-evt_ucx_usbdevice_address">EVT_UCX_USBDEVICE_ADDRESS</a>
