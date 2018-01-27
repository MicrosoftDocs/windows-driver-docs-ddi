---
UID: NS:ndischimney._NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS
title: _NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS
author: windows-driver-content
description: The NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure specifies a protocol driver's generic chimney offload entry points.
old-location: netvista\ndis_client_chimney_offload_generic_characteristics.htm
old-project: netvista
ms.assetid: 66eb9528-e026-44cd-a775-c8d963036adc
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: *PNDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, tcp_chim_struct_5db55d5e-f540-4f60-9f3b-adcd24932b1d.xml, NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], netvista.ndis_client_chimney_offload_generic_characteristics, ndischimney/NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, _NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, PNDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, PNDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], ndischimney/PNDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS
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
-	NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS
product: Windows
targetos: Windows
req.typenames: NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, *PNDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS
---

# _NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure specifies a protocol driver's
  generic chimney offload entry points. Generic chimney offload entry points apply to all chimney offload
  types. Currently, TCP chimney offload is the only defined chimney offload type.


## -syntax


````
typedef struct _NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS {
  NDIS_OBJECT_HEADER                  Header;
  ULONG                               Flags;
  INITIATE_OFFLOAD_COMPLETE_HANDLER   InitiateOffloadCompleteHandler;
  TERMINATE_OFFLOAD_COMPLETE_HANDLER  TerminateOffloadCompleteHandler;
  UPDATE_OFFLOAD_COMPLETE_HANDLER     UpdateOffloadCompleteHandler;
  INVALIDATE_OFFLOAD_COMPLETE_HANDLER InvalidateOffloadCompleteHandler;
  QUERY_OFFLOAD_COMPLETE_HANDLER      QueryOffloadCompleteHandler;
  INDICATE_OFFLOAD_EVENT_HANDLER      IndicateOffloadEventHandler;
} NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, *PNDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS;
````


## -struct-fields




### -field Header

The header of the NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure. The header is
     formatted as an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure. The
     NDIS_OBJECT_HEADER structure contains the revision number of the
     NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure and the size of the
     NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure, including the header, in bytes. The 
     <b>Type</b> member of the header is not significant.


### -field Flags

Reserved for system use.


### -field InitiateOffloadCompleteHandler

Specifies the entry point of the driver's 
     <mshelp:link keywords="netvista.protocolinitiateoffloadcomplete" tabindex="0"><i>
     ProtocolInitiateOffloadComplete</i></mshelp:link> function.


### -field TerminateOffloadCompleteHandler

The entry point of the driver's 
     <mshelp:link keywords="netvista.protocolterminateoffloadcomplete" tabindex="0"><i>
     ProtocolTerminateOffloadComplete</i></mshelp:link> function.


### -field UpdateOffloadCompleteHandler

The entry point of the driver's 
     <mshelp:link keywords="netvista.protocolupdateoffloadcomplete" tabindex="0"><i>
     ProtocolUpdateOffloadComplete</i></mshelp:link> function.


### -field InvalidateOffloadCompleteHandler

The entry point of the driver's 
     <mshelp:link keywords="netvista.protocolinvalidateoffloadcomplete" tabindex="0"><i>
     ProtocolInvalidateOffloadComplete</i></mshelp:link> function.


### -field QueryOffloadCompleteHandler

The entry point of the driver's 
     <mshelp:link keywords="netvista.protocolqueryoffloadcomplete" tabindex="0"><i>
     ProtocolQueryOffloadComplete</i></mshelp:link> function.


### -field IndicateOffloadEventHandler

The entry point of the driver's 
     <mshelp:link keywords="netvista.protocolindicateoffloadevent" tabindex="0"><i>
     ProtocolIndicateOffloadEvent</i></mshelp:link> function.


## -remarks


To register its generic chimney offload entry points, a protocol or intermediate driver calls the 
    <a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a> function
    in the context of the 
    <a href="..\ndis\nc-ndis-set_options.md">ProtocolSetOptions</a> function. To the 
    <b>NdisSetOptionalHandlers</b> function,
    the protocol or intermediate driver passes a pointer to the
    NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure.



## -see-also

<mshelp:link keywords="netvista.protocolterminateoffloadcomplete" tabindex="0"><i>
   ProtocolTerminateOffloadComplete</i></mshelp:link>

<a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a>

<mshelp:link keywords="netvista.protocolindicateoffloadevent" tabindex="0"><i>
   ProtocolIndicateOffloadEvent</i></mshelp:link>

<mshelp:link keywords="netvista.protocolinvalidateoffloadcomplete" tabindex="0"><i>
   ProtocolInvalidateOffloadComplete</i></mshelp:link>

<mshelp:link keywords="netvista.protocolupdateoffloadcomplete" tabindex="0"><i>
   ProtocolUpdateOffloadComplete</i></mshelp:link>

<a href="..\ndis\nc-ndis-set_options.md">ProtocolSetOptions</a>

<mshelp:link keywords="netvista.protocolqueryoffloadcomplete" tabindex="0"><i>
   ProtocolQueryOffloadComplete</i></mshelp:link>

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

<mshelp:link keywords="netvista.protocolinitiateoffloadcomplete" tabindex="0"><i>
   ProtocolInitiateOffloadComplete</i></mshelp:link>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

