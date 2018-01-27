---
UID: NS:ndischimney._NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS
title: _NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS
author: windows-driver-content
description: The NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure specifies the generic chimney offload miniport entry points of an offload target or intermediate driver.
old-location: netvista\ndis_provider_chimney_offload_generic_characteristics.htm
old-project: netvista
ms.assetid: e80a9999-2e4e-4da0-8aae-54ee71d9249d
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: PNDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, netvista.ndis_provider_chimney_offload_generic_characteristics, ndischimney/NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, ndischimney/PNDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, _NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, *PNDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, tcp_chim_struct_3145314d-c0a6-4d4e-b489-c38dda6c43e5.xml, PNDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista]
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
-	NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS
product: Windows
targetos: Windows
req.typenames: NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, *PNDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS
---

# _NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure specifies the generic chimney
  offload miniport entry points of an offload target or intermediate driver. Generic chimney offload entry
  points pertain to all chimney offload types. Currently, TCP chimney offload is the only defined chimney
  offload type.


## -syntax


````
typedef struct _NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS {
  NDIS_OBJECT_HEADER           Header;
  ULONG                        Flags;
  W_INITIATE_OFFLOAD_HANDLER   InitiateOffloadHandler;
  W_TERMINATE_OFFLOAD_HANDLER  TerminateOffloadHandler;
  W_UPDATE_OFFLOAD_HANDLER     UpdateOffloadHandler;
  W_INVALIDATE_OFFLOAD_HANDLER InvalidateOffloadHandler;
  W_QUERY_OFFLOAD_HANDLER      QueryOffloadHandler;
} NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, *PNDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS;
````


## -struct-fields




### -field Header

The header of the NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure. The header is
     formatted as an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure. The
     NDIS_OBJECT_HEADER structure contains the revision number of the
     NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure and the size of the
     NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure, including the header, in bytes. The 
     <b>Type</b> member of the header is not significant.


### -field Flags

Reserved for system use.


### -field InitiateOffloadHandler

The entry point of the driver's 
     <mshelp:link keywords="netvista.miniportinitiateoffload" tabindex="0"><i>
     MiniportInitiateOffload</i></mshelp:link> function.


### -field TerminateOffloadHandler

The entry point of the driver's 
     <mshelp:link keywords="netvista.miniportterminateoffload" tabindex="0"><i>
     MiniportTerminateOffload</i></mshelp:link> function.


### -field UpdateOffloadHandler

The entry point of the driver's 
     <mshelp:link keywords="netvista.miniportupdateoffload" tabindex="0"><i>
     MiniportUpdateOffload</i></mshelp:link> function.


### -field InvalidateOffloadHandler

The entry point of the driver's 
     <mshelp:link keywords="netvista.miniportinvalidateoffload" tabindex="0"><i>
     MiniportInvalidateOffload</i></mshelp:link> function.


### -field QueryOffloadHandler

The entry point of the driver's 
     <mshelp:link keywords="netvista.miniportqueryoffload" tabindex="0"><i>
     MiniportQueryOffload</i></mshelp:link> function.


## -remarks


To register its generic chimney offload entry points, an offload target or intermediate driver calls
    the 
    <a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a> function
    in the context of the 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570269">MiniportSetOptions</a> function. To the 
    <b>NdisSetOptionalHandlers</b> function, the offload target or intermediate driver passes a pointer to the
    NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure.



## -see-also

<a href="..\ndischimney\nc-ndischimney-w_terminate_offload_handler.md">MiniportTerminateOffload</a>

<a href="..\ndischimney\nc-ndischimney-w_invalidate_offload_handler.md">MiniportInvalidateOffload</a>

<a href="..\ndischimney\nc-ndischimney-w_query_offload_handler.md">MiniportQueryOffload</a>

<a href="..\ndischimney\nc-ndischimney-w_update_offload_handler.md">MiniportUpdateOffload</a>

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570269">MiniportSetOptions</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

<a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a>

<a href="..\ndischimney\nc-ndischimney-w_initiate_offload_handler.md">MiniportInitiateOffload</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

