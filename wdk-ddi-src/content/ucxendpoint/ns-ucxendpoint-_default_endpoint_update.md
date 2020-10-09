---
UID: NS:ucxendpoint._DEFAULT_ENDPOINT_UPDATE
title: _DEFAULT_ENDPOINT_UPDATE (ucxendpoint.h)
description: Contains the handle to the default endpoint to update in a framework request that is passed by UCX when it invokes EVT_UCX_DEFAULT_ENDPOINT_UPDATE callback function.
old-location: buses\_default_endpoint_update.htm
tech.root: usbref
ms.assetid: 3E85D9AE-F8D3-4763-B1A2-51F95D00422D
ms.date: 05/07/2018
keywords: ["DEFAULT_ENDPOINT_UPDATE structure"]
ms.keywords: "*PDEFAULT_ENDPOINT_UPDATE, DEFAULT_ENDPOINT_UPDATE, DEFAULT_ENDPOINT_UPDATE structure [Buses], P_DEFAULT_ENDPOINT_UPDATE, P_DEFAULT_ENDPOINT_UPDATE structure pointer [Buses], _DEFAULT_ENDPOINT_UPDATE, buses._default_endpoint_update, ucxendpoint/P_DEFAULT_ENDPOINT_UPDATE, ucxendpoint/_DEFAULT_ENDPOINT_UPDATE"
req.header: ucxendpoint.h
req.include-header: Ucxclass.h, Ucxendpoint.h
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
req.typenames: DEFAULT_ENDPOINT_UPDATE, *PDEFAULT_ENDPOINT_UPDATE
f1_keywords:
 - _DEFAULT_ENDPOINT_UPDATE
 - ucxendpoint/_DEFAULT_ENDPOINT_UPDATE
 - PDEFAULT_ENDPOINT_UPDATE
 - ucxendpoint/PDEFAULT_ENDPOINT_UPDATE
 - DEFAULT_ENDPOINT_UPDATE
 - ucxendpoint/DEFAULT_ENDPOINT_UPDATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ucxendpoint.h
api_name:
 - DEFAULT_ENDPOINT_UPDATE
---

# _DEFAULT_ENDPOINT_UPDATE structure


## -description

Contains the handle to the default endpoint to update in a framework request that is passed by UCX when it invokes <a href="/windows-hardware/drivers/ddi/ucxendpoint/nc-ucxendpoint-evt_ucx_default_endpoint_update">EVT_UCX_DEFAULT_ENDPOINT_UPDATE</a> callback function.

## -struct-fields

### -field Header

A <a href="/windows-hardware/drivers/ddi/ucxusbdevice/ns-ucxusbdevice-_usbdevice_mgmt_header">USBDEVICE_MGMT_HEADER</a> structure that contains header information related to the USB device or hub endpoint.

### -field DefaultEndpoint

A handle to the  default endpoint to update.

### -field MaxPacketSize

The maximum packet size of the default endpoint.

## -see-also

<a href="/windows-hardware/drivers/ddi/ucxendpoint/nc-ucxendpoint-evt_ucx_default_endpoint_update">EVT_UCX_DEFAULT_ENDPOINT_UPDATE</a>