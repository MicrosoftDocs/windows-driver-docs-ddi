---
UID: NF:ndis.NdisFDevicePnPEventNotify
title: NdisFDevicePnPEventNotify function (ndis.h)
description: A filter driver can call the NdisFDevicePnPEventNotify function to forward a device Plug and Play (PnP) or Power Management event to underlying drivers.
old-location: netvista\ndisfdevicepnpeventnotify.htm
tech.root: netvista
ms.assetid: ae5dd48b-7777-4232-89ad-ac4464e03e57
ms.date: 05/02/2018
keywords: ["NdisFDevicePnPEventNotify function"]
ms.keywords: NdisFDevicePnPEventNotify, NdisFDevicePnPEventNotify function [Network Drivers Starting with Windows Vista], filter_ndis_functions_ref_56e249ae-0200-4c98-b20c-03cc8d3fdd7d.xml, ndis/NdisFDevicePnPEventNotify, netvista.ndisfdevicepnpeventnotify
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Filter_Driver_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisFDevicePnPEventNotify
 - ndis/NdisFDevicePnPEventNotify
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisFDevicePnPEventNotify
---

# NdisFDevicePnPEventNotify function


## -description

A filter driver can call the 
  <b>NdisFDevicePnPEventNotify</b> function to forward a device Plug and Play (PnP) or Power Management event
  to underlying drivers.

## -parameters

### -param NdisFilterHandle 

[in]
The NDIS handle that identifies this filter module. NDIS passed the handle to the filter driver in
     a call to the 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a> function.

### -param NetDevicePnPEvent 

[in]
A pointer to a 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_device_pnp_event">NET_DEVICE_PNP_EVENT</a> structure that
     describes a device Plug and Play event.

## -remarks

NDIS calls a filter driver's 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_device_pnp_event_notify">
    FilterDevicePnPEventNotify</a> function to notify the filter driver of device PnP and Power Management
    events that affect an underlying device object.

Filter drivers can forward these notifications to underlying drivers. To forward a request, call the 
    <b>NdisFDevicePnPEventNotify</b> function before returning from the 
    <i>FilterDevicePnPEventNotify</i> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_device_pnp_event_notify">FilterDevicePnPEventNotify</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_device_pnp_event">NET_DEVICE_PNP_EVENT</a>