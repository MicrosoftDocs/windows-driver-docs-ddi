---
UID: NF:ndis.NdisCompleteNetPnPEvent
title: NdisCompleteNetPnPEvent function (ndis.h)
description: Protocol drivers call the NdisCompleteNetPnPEvent function to complete a response to a Plug and Play or Power Management event for which the caller's ProtocolNetPnPEvent function returned NDIS_STATUS_PENDING.
old-location: netvista\ndiscompletenetpnpevent.htm
tech.root: netvista
ms.assetid: 2a59e6a1-d018-4b95-8e50-8351a3b69d86
ms.date: 05/02/2018
keywords: ["NdisCompleteNetPnPEvent function"]
ms.keywords: NdisCompleteNetPnPEvent, NdisCompleteNetPnPEvent function [Network Drivers Starting with Windows Vista], ndis/NdisCompleteNetPnPEvent, netvista.ndiscompletenetpnpevent, protocol_ndis_functions_ref_4f57d0f9-c9bf-4451-a612-caa665d0b6be.xml
f1_keywords:
 - "ndis/NdisCompleteNetPnPEvent"
 - "NdisCompleteNetPnPEvent"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Protocol_Driver_Function
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
- NdisCompleteNetPnPEvent
targetos: Windows
req.typenames: 
---

# NdisCompleteNetPnPEvent function


## -description


Protocol drivers call the 
  <b>NdisCompleteNetPnPEvent</b> function to complete a response to a Plug and Play or Power Management event
  for which the caller's 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_net_pnp_event">ProtocolNetPnPEvent</a> function returned
  NDIS_STATUS_PENDING.


## -parameters




### -param NdisBindingHandle [in]

The handle that NDIS provided at the 
     <i>NdisBindingHandle</i> parameter of the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a> function. The handle
     identifies the binding between the caller and the underlying miniport adapter.


### -param NetPnPEventNotification

A pointer to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_pnp_event_notification">
     NET_PNP_EVENT_NOTIFICATION</a> structure that NDIS passed to the caller's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_net_pnp_event">
     ProtocolNetPnPEvent</a> function.

### -param Status [in]

The protocol driver's response to the pending Plug and Play or Power Management event
     notification. To succeed such an event, specify NDIS_STATUS_SUCCESS. For information about other status
     values, see the return values of the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_net_pnp_event">
     ProtocolNetPnPEvent</a> function.


## -remarks



When a protocol driver returns NDIS_STATUS_PENDING from its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_net_pnp_event">ProtocolNetPnPEvent</a> function, it
    must eventually call 
    <b>NdisCompleteNetPnPEvent</b> to indicate its response to the given Plug and Play or Power Management
    notification.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_pnp_event_notification">NET_PNP_EVENT_NOTIFICATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_net_pnp_event">ProtocolNetPnPEvent</a>
 

 

