---
UID: NS:ndischimney._NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS
title: "_NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS"
author: windows-driver-content
description: The NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure specifies an offload target's TCP chimney offload-specific entry points.
old-location: netvista\ndis_provider_chimney_offload_tcp_characteristics.htm
old-project: netvista
ms.assetid: 3eabbad5-b84b-4034-a0b6-d4d515cbc117
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PNDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS, ,, A, C, D, E, F, H, I, L, M, N, NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS, NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], O, P, PNDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS, PNDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], R, S, T, V, Y, _, _NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS, ndischimney/NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS, ndischimney/PNDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS, netvista.ndis_provider_chimney_offload_tcp_characteristics, tcp_chim_struct_f701c1a0-6057-4cf3-ae27-6e72352b4829.xml"
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
-	NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS
product: Windows
targetos: Windows
req.typenames: NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS, *PNDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS
---

# _NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure specifies an offload target's TCP
  chimney offload-specific entry points.


## -syntax


````
typedef struct _NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS {
  NDIS_OBJECT_HEADER                   Header;
  ULONG                                Flags;
  NDIS_CHIMNEY_OFFLOAD_TYPE            OffloadType;
  W_TCP_OFFLOAD_SEND_HANDLER           TcpOffloadSendHandler;
  W_TCP_OFFLOAD_RECEIVE_HANDLER        TcpOffloadReceiveHandler;
  W_TCP_OFFLOAD_DISCONNECT_HANDLER     TcpOffloadDisconnectHandler;
  W_TCP_OFFLOAD_FORWARD_HANDLER        TcpOffloadForwardHandler;
  W_TCP_OFFLOAD_RECEIVE_RETURN_HANDLER TcpOffloadReceiveReturnHandler;
} NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS, *PNDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS;
````


## -struct-fields




### -field Header

The header of the NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure. The header is
     formatted as an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure. The
     NDIS_OBJECT_HEADER structure contains the revision number of the
     NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure and the size of the
     NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure, including the header, in bytes. The 
     <b>Type</b> member of the header is not significant.


### -field Flags

Reserved for system use.


### -field OffloadType

The chimney offload type. The only allowable value is 
     <b>NdisTcpChimneyOffload</b>, which specifies a TCP chimney.


### -field TcpOffloadSendHandler

The entry point of the driver's 
     <a href="..\ndischimney\nc-ndischimney-w_tcp_offload_send_handler.md">
     MiniportTcpOffloadSend</a> function.


### -field TcpOffloadReceiveHandler

The entry point of the driver's 
     <a href="..\ndischimney\nc-ndischimney-w_tcp_offload_receive_handler.md">
     MiniportTcpOffloadReceive</a> function.


### -field TcpOffloadDisconnectHandler

The entry point of the driver's 
     <a href="..\ndischimney\nc-ndischimney-w_tcp_offload_disconnect_handler.md">
     MiniportTcpOffloadDisconnect</a> function.


### -field TcpOffloadForwardHandler

The entry point of the driver's 
     <a href="..\ndischimney\nc-ndischimney-w_tcp_offload_forward_handler.md">
     MiniportTcpOffloadForward</a> function.


### -field TcpOffloadReceiveReturnHandler

The entry point of the driver's 
     <a href="..\ndischimney\nc-ndischimney-w_tcp_offload_receive_return_handler.md">
     MiniportTcpOffloadReceiveReturn</a> function.


## -remarks



To register its TCP chimney offload-specific entry points, an offload target calls the 
    <a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a> function
    in the context of the 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570269">MiniportSetOptions</a> function. To the 
    <b>NdisSetOptionalHandlers</b> function, the offload target passes a pointer to the
    NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure.




## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="..\ndischimney\nc-ndischimney-w_tcp_offload_send_handler.md">MiniportTcpOffloadSend</a>



<a href="..\ndischimney\nc-ndischimney-w_tcp_offload_receive_handler.md">MiniportTcpOffloadReceive</a>



<a href="..\ndischimney\nc-ndischimney-w_tcp_offload_forward_handler.md">MiniportTcpOffloadForward</a>



<a href="..\ndischimney\nc-ndischimney-w_tcp_offload_disconnect_handler.md">
   MiniportTcpOffloadDisconnect</a>



<a href="..\ndischimney\nc-ndischimney-w_tcp_offload_receive_return_handler.md">
   MiniportTcpOffloadReceiveReturn</a>



<a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570269">MiniportSetOptions</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

