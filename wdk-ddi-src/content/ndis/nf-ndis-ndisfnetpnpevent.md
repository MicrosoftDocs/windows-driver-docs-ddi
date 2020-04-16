---
UID: NF:ndis.NdisFNetPnPEvent
title: NdisFNetPnPEvent function (ndis.h)
description: A filter driver can call the NdisFNetPnPEvent function to forward a network Plug and Play (PnP) or Power Management event to overlying drivers.
old-location: netvista\ndisfnetpnpevent.htm
tech.root: netvista
ms.assetid: 383f9dcb-68ba-4323-b25f-668169043f35
ms.date: 05/02/2018
keywords: ["NdisFNetPnPEvent function"]
ms.keywords: NdisFNetPnPEvent, NdisFNetPnPEvent function [Network Drivers Starting with Windows Vista], filter_ndis_functions_ref_36921970-788b-4b5e-9cf0-c54f8dcdeef2.xml, ndis/NdisFNetPnPEvent, netvista.ndisfnetpnpevent
f1_keywords:
 - "ndis/NdisFNetPnPEvent"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisFNetPnPEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisFNetPnPEvent function


## -description


A filter driver can call the 
  <b>NdisFNetPnPEvent</b> function to forward a network Plug and Play (PnP) or Power Management event to
  overlying drivers.


## -parameters




### -param NdisFilterHandle

A handle to the context area for the filter module. The filter driver created and initialized this
     context area in the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a> function.

### -param NetPnPEventNotification

A pointer to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_pnp_event_notification">
     NET_PNP_EVENT_NOTIFICATION</a> structure, which describes the network PnP event or Power Management
     event being forwarded by the filter driver.

## -returns



<b>NdisFNetPnPEvent</b> can return either of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The overlying driver succeeded in processing the PnP event.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
The overlying driver failed the PnP event.

</td>
</tr>
</table>
 




## -remarks



NDIS calls a filter driver's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_net_pnp_event">FilterNetPnPEvent</a> function to notify
    the filter driver of network PnP and Power Management events.

Filter drivers can forward these notifications to overlying drivers. To forward a request, call the 
    <b>NdisFNetPnPEvent</b> function from 
    <i>FilterNetPnPEvent</i>.

<div class="alert"><b>Note</b>  NDIS drivers must not call 
    <b>NdisFNetPnPEvent</b> from within the context of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_oid_request">FilterOidRequest</a> function.</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_net_pnp_event">FilterNetPnPEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_oid_request">FilterOidRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_pnp_event_notification">NET_PNP_EVENT_NOTIFICATION</a>
 

 

