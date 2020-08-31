---
UID: NS:ucxusbdevice._USBDEVICE_RESET
title: _USBDEVICE_RESET (ucxusbdevice.h)
description: Contains parameters for a request to reset the specified device. This structure is passed by UCX in request parameters (Parameters.Others.Arg1) of a framework request object of the EVT_UCX_USBDEVICE_RESET callback function.
old-location: buses\_usbdevice_reset.htm
tech.root: usbref
ms.assetid: 4C07239D-89AE-4A9F-B7EB-CFFE6D47F10B
ms.date: 05/07/2018
keywords: ["USBDEVICE_RESET structure"]
ms.keywords: "*PUSBDEVICE_RESET, P_USBDEVICE_RESET, P_USBDEVICE_RESET structure pointer [Buses], USBDEVICE_RESET, USBDEVICE_RESET structure [Buses], _USBDEVICE_RESET, buses._usbdevice_reset, ucxusbdevice/P_USBDEVICE_RESET, ucxusbdevice/_USBDEVICE_RESET"
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
req.typenames: USBDEVICE_RESET, *PUSBDEVICE_RESET
f1_keywords:
 - _USBDEVICE_RESET
 - ucxusbdevice/_USBDEVICE_RESET
 - PUSBDEVICE_RESET
 - ucxusbdevice/PUSBDEVICE_RESET
 - USBDEVICE_RESET
 - ucxusbdevice/USBDEVICE_RESET
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ucxusbdevice.h
api_name:
 - USBDEVICE_RESET
---

# _USBDEVICE_RESET structure


## -description

Contains parameters for a request to reset the specified device.  This structure is passed by UCX in request parameters (<b>Parameters.Others.Arg1</b>) of a framework request object of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/nc-ucxusbdevice-evt_ucx_usbdevice_reset">EVT_UCX_USBDEVICE_RESET</a> callback function.

## -struct-fields

### -field Header

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/ns-ucxusbdevice-_usbdevice_mgmt_header">USBDEVICE_MGMT_HEADER</a> structure that contains  the handle for the USB hub or device.

### -field DefaultEndpoint

The default endpoint for the USB hub or device.

### -field EndpointsToDisableCount

The number of endpoints to disable.

### -field EndpointsToDisable

A pointer to an array of handles to endpoints to disable.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/nc-ucxusbdevice-evt_ucx_usbdevice_reset">EVT_UCX_USBDEVICE_RESET</a>

