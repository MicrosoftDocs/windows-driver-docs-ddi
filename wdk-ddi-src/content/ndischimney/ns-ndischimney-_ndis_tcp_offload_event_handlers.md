---
UID: NS:ndischimney._NDIS_TCP_OFFLOAD_EVENT_HANDLERS
title: _NDIS_TCP_OFFLOAD_EVENT_HANDLERS
author: windows-driver-content
description: The NDIS_TCP_OFFLOAD_EVENT_HANDLERS structure contains the entry points for the NDIS functions for the TCP chimney.
old-location: netvista\ndis_tcp_offload_event_handlers.htm
old-project: netvista
ms.assetid: 72863a3e-9907-43e1-ad83-831a972ab823
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndis_tcp_offload_event_handlers, tcp_chim_struct_ae670e4d-ac1a-4dd2-95f5-2f2b202003e4.xml, _NDIS_TCP_OFFLOAD_EVENT_HANDLERS, ndischimney/PNDIS_TCP_OFFLOAD_EVENT_HANDLERS, PNDIS_TCP_OFFLOAD_EVENT_HANDLERS, ndischimney/NDIS_TCP_OFFLOAD_EVENT_HANDLERS, PNDIS_TCP_OFFLOAD_EVENT_HANDLERS structure pointer [Network Drivers Starting with Windows Vista], NDIS_TCP_OFFLOAD_EVENT_HANDLERS structure [Network Drivers Starting with Windows Vista], NDIS_TCP_OFFLOAD_EVENT_HANDLERS, *PNDIS_TCP_OFFLOAD_EVENT_HANDLERS
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	ndischimney.h
apiname: 
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
     <mshelp:link keywords="netvista.ndistcpoffloadeventhandler" tabindex="0"><b>
     NdisTcpOffloadEventHandler</b></mshelp:link> function.


### -field NdisTcpOffloadReceiveHandler

The entry point for the 
     <mshelp:link keywords="netvista.ndistcpoffloadreceivehandler" tabindex="0"><b>
     NdisTcpOffloadReceiveHandler</b></mshelp:link> function.


### -field NdisTcpOffloadSendComplete

The entry point for the 
     <mshelp:link keywords="netvista.ndistcpoffloadsendcomplete" tabindex="0"><b>
     NdisTcpOffloadSendComplete</b></mshelp:link> function.


### -field NdisTcpOffloadReceiveComplete

The entry point for the 
     <mshelp:link keywords="netvista.ndistcpoffloadreceivecomplete" tabindex="0"><b>
     NdisTcpOffloadReceiveComplete</b></mshelp:link> function.


### -field NdisTcpOffloadDisconnectComplete

The entry point for the 
     <mshelp:link keywords="netvista.ndistcpoffloaddisconnectcomplete" tabindex="0"><b>
     NdisTcpOffloadDisconnectComplete</b></mshelp:link> function.


### -field NdisTcpOffloadForwardComplete

The entry point for the 
     <mshelp:link keywords="netvista.ndistcpoffloadforwardcomplete" tabindex="0"><b>
     NdisTcpOffloadForwardComplete</b></mshelp:link> function.


## -remarks


An offload target copies the entry points in the NDIS_TCP_OFFLOAD_EVENT_HANDLERS structure into its
    own internal data structure.



## -see-also

<a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_receive_indicate.md">NdisTcpOffloadReceiveHandler</a>

<mshelp:link keywords="netvista.ndistcpoffloadreceivecomplete" tabindex="0"><b>
   NdisTcpOffloadReceiveComplete</b></mshelp:link>

<a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_event_indicate.md">NdisTcpOffloadEventHandler</a>

<a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_send_complete.md">NdisTcpOffloadSendComplete</a>

<a href="..\ndischimney\nf-ndischimney-ndismgetoffloadhandlers.md">NdisMGetOffloadHandlers</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

<mshelp:link keywords="netvista.ndistcpoffloaddisconnectcomplete" tabindex="0"><b>
   NdisTcpOffloadDisconnectComplete</b></mshelp:link>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_TCP_OFFLOAD_EVENT_HANDLERS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

