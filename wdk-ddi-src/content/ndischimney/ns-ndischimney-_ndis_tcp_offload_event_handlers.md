---
UID: NS:ndischimney._NDIS_TCP_OFFLOAD_EVENT_HANDLERS
title: _NDIS_TCP_OFFLOAD_EVENT_HANDLERS (ndischimney.h)
description: The NDIS_TCP_OFFLOAD_EVENT_HANDLERS structure contains the entry points for the NDIS functions for the TCP chimney.
old-location: netvista\ndis_tcp_offload_event_handlers.htm
tech.root: netvista
ms.assetid: 72863a3e-9907-43e1-ad83-831a972ab823
ms.date: 05/02/2018
keywords: ["_NDIS_TCP_OFFLOAD_EVENT_HANDLERS structure"]
ms.keywords: "*PNDIS_TCP_OFFLOAD_EVENT_HANDLERS, NDIS_TCP_OFFLOAD_EVENT_HANDLERS, NDIS_TCP_OFFLOAD_EVENT_HANDLERS structure [Network Drivers Starting with Windows Vista], PNDIS_TCP_OFFLOAD_EVENT_HANDLERS, PNDIS_TCP_OFFLOAD_EVENT_HANDLERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_TCP_OFFLOAD_EVENT_HANDLERS, ndischimney/NDIS_TCP_OFFLOAD_EVENT_HANDLERS, ndischimney/PNDIS_TCP_OFFLOAD_EVENT_HANDLERS, netvista.ndis_tcp_offload_event_handlers, tcp_chim_struct_ae670e4d-ac1a-4dd2-95f5-2f2b202003e4.xml"
f1_keywords:
 - "ndischimney/NDIS_TCP_OFFLOAD_EVENT_HANDLERS"
 - "NDIS_TCP_OFFLOAD_EVENT_HANDLERS"
req.header: ndischimney.h
req.include-header: Ndischimney.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndischimney.h
api_name:
- NDIS_TCP_OFFLOAD_EVENT_HANDLERS
product:
- Windows
targetos: Windows
req.typenames: NDIS_TCP_OFFLOAD_EVENT_HANDLERS, *PNDIS_TCP_OFFLOAD_EVENT_HANDLERS
---

# _NDIS_TCP_OFFLOAD_EVENT_HANDLERS structure


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The NDIS_TCP_OFFLOAD_EVENT_HANDLERS structure contains the entry points for the NDIS functions for
  the TCP chimney.


## -struct-fields




### -field Header

The NDIS object header, which is formatted as an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.


### -field NdisTcpOffloadEventHandler

The entry point for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-ndis_tcp_offload_event_indicate">
     NdisTcpOffloadEventHandler</a> function.


### -field NdisTcpOffloadReceiveHandler

The entry point for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-ndis_tcp_offload_receive_indicate">
     NdisTcpOffloadReceiveHandler</a> function.


### -field NdisTcpOffloadSendComplete

The entry point for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-ndis_tcp_offload_send_complete">
     NdisTcpOffloadSendComplete</a> function.


### -field NdisTcpOffloadReceiveComplete

The entry point for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-ndis_tcp_offload_receive_complete">
     NdisTcpOffloadReceiveComplete</a> function.


### -field NdisTcpOffloadDisconnectComplete

The entry point for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-ndis_tcp_offload_disconnect_complete">
     NdisTcpOffloadDisconnectComplete</a> function.


### -field NdisTcpOffloadForwardComplete

The entry point for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-ndis_tcp_offload_forward_complete">
     NdisTcpOffloadForwardComplete</a> function.


## -remarks



An offload target copies the entry points in the NDIS_TCP_OFFLOAD_EVENT_HANDLERS structure into its
    own internal data structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nf-ndischimney-ndismgetoffloadhandlers">NdisMGetOffloadHandlers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-ndis_tcp_offload_disconnect_complete">
   NdisTcpOffloadDisconnectComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-ndis_tcp_offload_event_indicate">NdisTcpOffloadEventHandler</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-ndis_tcp_offload_receive_complete">
   NdisTcpOffloadReceiveComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-ndis_tcp_offload_receive_indicate">NdisTcpOffloadReceiveHandler</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-ndis_tcp_offload_send_complete">NdisTcpOffloadSendComplete</a>
 

 

