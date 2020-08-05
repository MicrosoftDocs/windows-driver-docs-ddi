---
UID: NS:ndischimney._NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS
title: _NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS (ndischimney.h)
description: The NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure specifies an offload target's TCP chimney offload-specific entry points.
old-location: netvista\ndis_provider_chimney_offload_tcp_characteristics.htm
tech.root: netvista
ms.assetid: 3eabbad5-b84b-4034-a0b6-d4d515cbc117
ms.date: 05/02/2018
keywords: ["NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure"]
ms.keywords: "*PNDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS, NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS, NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS, PNDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS, ndischimney/NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS, ndischimney/PNDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS, netvista.ndis_provider_chimney_offload_tcp_characteristics, tcp_chim_struct_f701c1a0-6057-4cf3-ae27-6e72352b4829.xml"
f1_keywords:
 - "ndischimney/NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS"
 - "NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS"
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
- NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS
targetos: Windows
req.typenames: NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS, *PNDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS
---

# _NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure specifies an offload target's TCP
  chimney offload-specific entry points.


## -struct-fields




### -field Header

The header of the NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure. The header is
     formatted as an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure. The
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
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_tcp_offload_send_handler">
     MiniportTcpOffloadSend</a> function.


### -field TcpOffloadReceiveHandler

The entry point of the driver's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_tcp_offload_receive_handler">
     MiniportTcpOffloadReceive</a> function.


### -field TcpOffloadDisconnectHandler

The entry point of the driver's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_tcp_offload_disconnect_handler">
     MiniportTcpOffloadDisconnect</a> function.


### -field TcpOffloadForwardHandler

The entry point of the driver's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_tcp_offload_forward_handler">
     MiniportTcpOffloadForward</a> function.


### -field TcpOffloadReceiveReturnHandler

The entry point of the driver's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_tcp_offload_receive_return_handler">
     MiniportTcpOffloadReceiveReturn</a> function.


## -remarks



To register its TCP chimney offload-specific entry points, an offload target calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissetoptionalhandlers">NdisSetOptionalHandlers</a> function
    in the context of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-set_options">MiniportSetOptions</a> function. To the 
    <b>NdisSetOptionalHandlers</b> function, the offload target passes a pointer to the
    NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-set_options">MiniportSetOptions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_tcp_offload_disconnect_handler">
   MiniportTcpOffloadDisconnect</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_tcp_offload_forward_handler">MiniportTcpOffloadForward</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_tcp_offload_receive_handler">MiniportTcpOffloadReceive</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_tcp_offload_receive_return_handler">
   MiniportTcpOffloadReceiveReturn</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_tcp_offload_send_handler">MiniportTcpOffloadSend</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissetoptionalhandlers">NdisSetOptionalHandlers</a>
 

 

