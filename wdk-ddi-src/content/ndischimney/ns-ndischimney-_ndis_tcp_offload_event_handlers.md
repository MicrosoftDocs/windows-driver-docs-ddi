---
UID: NS:ndischimney._NDIS_TCP_OFFLOAD_EVENT_HANDLERS
title: "_NDIS_TCP_OFFLOAD_EVENT_HANDLERS"
author: windows-driver-content
description: The NDIS_TCP_OFFLOAD_EVENT_HANDLERS structure contains the entry points for the NDIS functions for the TCP chimney.
old-location: netvista\ndis_tcp_offload_event_handlers.htm
old-project: netvista
ms.assetid: 72863a3e-9907-43e1-ad83-831a972ab823
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PNDIS_TCP_OFFLOAD_EVENT_HANDLERS, NDIS_TCP_OFFLOAD_EVENT_HANDLERS, NDIS_TCP_OFFLOAD_EVENT_HANDLERS structure [Network Drivers Starting with Windows Vista], PNDIS_TCP_OFFLOAD_EVENT_HANDLERS, PNDIS_TCP_OFFLOAD_EVENT_HANDLERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_TCP_OFFLOAD_EVENT_HANDLERS, ndischimney/NDIS_TCP_OFFLOAD_EVENT_HANDLERS, ndischimney/PNDIS_TCP_OFFLOAD_EVENT_HANDLERS, netvista.ndis_tcp_offload_event_handlers, tcp_chim_struct_ae670e4d-ac1a-4dd2-95f5-2f2b202003e4.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndischimney.h
api_name:
-	NDIS_TCP_OFFLOAD_EVENT_HANDLERS
product: Windows
targetos: Windows
req.typenames: NDIS_TCP_OFFLOAD_EVENT_HANDLERS, *PNDIS_TCP_OFFLOAD_EVENT_HANDLERS
---

# _NDIS_TCP_OFFLOAD_EVENT_HANDLERS structure


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The NDIS_TCP_OFFLOAD_EVENT_HANDLERS structure contains the entry points for the NDIS functions for
  the TCP chimney.


## -syntax


````
typedef struct _NDIS_TCP_OFFLOAD_EVENT_HANDLERS {
  NDIS_OBJECT_HEADER                   Header;
  NDIS_TCP_OFFLOAD_EVENT_INDICATE      NdisTcpOffloadEventHandler;
  NDIS_TCP_OFFLOAD_RECEIVE_INDICATE    NdisTcpOffloadReceiveHandler;
  NDIS_TCP_OFFLOAD_SEND_COMPLETE       NdisTcpOffloadSendComplete;
  NDIS_TCP_OFFLOAD_RECEIVE_COMPLETE    NdisTcpOffloadReceiveComplete;
  NDIS_TCP_OFFLOAD_DISCONNECT_COMPLETE NdisTcpOffloadDisconnectComplete;
  NDIS_TCP_OFFLOAD_FORWARD_COMPLETE    NdisTcpOffloadForwardComplete;
} NDIS_TCP_OFFLOAD_EVENT_HANDLERS, *PNDIS_TCP_OFFLOAD_EVENT_HANDLERS;
````


## -struct-fields




### -field Header

The NDIS object header, which is formatted as an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.


### -field NdisTcpOffloadEventHandler

The entry point for the 
     <a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_event_indicate.md">
     NdisTcpOffloadEventHandler</a> function.


### -field NdisTcpOffloadReceiveHandler

The entry point for the 
     <a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_receive_indicate.md">
     NdisTcpOffloadReceiveHandler</a> function.


### -field NdisTcpOffloadSendComplete

The entry point for the 
     <a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_send_complete.md">
     NdisTcpOffloadSendComplete</a> function.


### -field NdisTcpOffloadReceiveComplete

The entry point for the 
     <a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_receive_complete.md">
     NdisTcpOffloadReceiveComplete</a> function.


### -field NdisTcpOffloadDisconnectComplete

The entry point for the 
     <a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_disconnect_complete.md">
     NdisTcpOffloadDisconnectComplete</a> function.


### -field NdisTcpOffloadForwardComplete

The entry point for the 
     <a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_forward_complete.md">
     NdisTcpOffloadForwardComplete</a> function.


## -remarks



An offload target copies the entry points in the NDIS_TCP_OFFLOAD_EVENT_HANDLERS structure into its
    own internal data structure.




## -see-also

<a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_send_complete.md">NdisTcpOffloadSendComplete</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="..\ndischimney\nf-ndischimney-ndismgetoffloadhandlers.md">NdisMGetOffloadHandlers</a>



<a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_receive_complete.md">
   NdisTcpOffloadReceiveComplete</a>



<a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_receive_indicate.md">NdisTcpOffloadReceiveHandler</a>



<a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_disconnect_complete.md">
   NdisTcpOffloadDisconnectComplete</a>



<a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_event_indicate.md">NdisTcpOffloadEventHandler</a>



 

 


