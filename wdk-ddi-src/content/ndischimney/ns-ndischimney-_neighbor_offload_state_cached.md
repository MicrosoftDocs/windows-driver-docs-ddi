---
UID: NS:ndischimney._NEIGHBOR_OFFLOAD_STATE_CACHED
title: "_NEIGHBOR_OFFLOAD_STATE_CACHED"
author: windows-driver-content
description: The NEIGHBOR_OFFLOAD_STATE_CACHED structure contains the cached variables of a neighbor state object.
old-location: netvista\neighbor_offload_state_cached.htm
old-project: netvista
ms.assetid: 5dedffa8-9745-4668-8646-0e896942b9c8
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ndischimney/PNEIGHBOR_OFFLOAD_STATE_CACHED, tcp_chim_struct_053f9a79-057c-4d4b-8ad1-2910f0ad4a9a.xml, ndischimney/NEIGHBOR_OFFLOAD_STATE_CACHED, PNEIGHBOR_OFFLOAD_STATE_CACHED, netvista.neighbor_offload_state_cached, PNEIGHBOR_OFFLOAD_STATE_CACHED structure pointer [Network Drivers Starting with Windows Vista], NEIGHBOR_OFFLOAD_STATE_CACHED, *PNEIGHBOR_OFFLOAD_STATE_CACHED, _NEIGHBOR_OFFLOAD_STATE_CACHED, NEIGHBOR_OFFLOAD_STATE_CACHED structure [Network Drivers Starting with Windows Vista]
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
-	NEIGHBOR_OFFLOAD_STATE_CACHED
product: Windows
targetos: Windows
req.typenames: NEIGHBOR_OFFLOAD_STATE_CACHED, *PNEIGHBOR_OFFLOAD_STATE_CACHED
---

# _NEIGHBOR_OFFLOAD_STATE_CACHED structure


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The NEIGHBOR_OFFLOAD_STATE_CACHED structure contains the cached variables of a neighbor state
  object.


## -syntax


````
typedef struct _NEIGHBOR_OFFLOAD_STATE_CACHED {
  OFFLOAD_STATE_HEADER Header;
  UCHAR                DlDestinationAddress[32];
  ULONG                HostReachabilityDelta;
} NEIGHBOR_OFFLOAD_STATE_CACHED, *PNEIGHBOR_OFFLOAD_STATE_CACHED;
````


## -struct-fields




### -field Header

An 
     <a href="..\ndischimney\ns-ndischimney-_offload_state_header.md">OFFLOAD_STATE_HEADER</a> structure. NDIS
     sets the 
     <b>Length</b> member of 
     <b>Header</b> to the size, in bytes, of the NEIGHBOR_OFFLOAD_STATE_CACHED structure. The 
     <b>RecognizedOptions</b> member of 
     <b>Header</b> is reserved.


### -field DlDestinationAddress

Specifies the media access control (MAC) address of the next hop (neighbor).


### -field HostReachabilityDelta

The host stack's current time minus 
     <b>HostReachabilityDelta</b> is the last time that the host stack confirmed neighbor reachability (see
     forward reachability in RFC 2461). For information about how the offload target uses this variable, see 
     <a href="..\ndischimney\nf-ndischimney-ndismoffloadeventindicate.md">NdisMOffloadEventIndicate</a>. 
     <b>HostReachabilityDelta</b> is measured in units of clock ticks.


## -remarks



Cached variables are owned and maintained by the host stack. An offload target must not change the
    value of a cached variable unless requested to do so by the host stack. If the value of a cached variable
    changes, the host stack requests an update of the variable, which causes NDIS to call the offload
    target's 
    <a href="..\ndischimney\nc-ndischimney-w_update_offload_handler.md">MiniportUpdateOffload</a> function.
    When the host stack terminates the offload of one or more state objects by causing NDIS to call the
    offload target's 
    <a href="..\ndischimney\nc-ndischimney-w_terminate_offload_handler.md">
    MiniportTerminateOffload</a> function, the offload target does not return the value of offloaded
    constant variables to the host stack.

When passed to an offload target, a NEIGHBOR_OFFLOAD_STATE_CACHED structure is associated with an 
    <a href="..\ndischimney\ns-ndischimney-_ndis_miniport_offload_block_list.md">
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure, which contains a header that is formatted as an 
    <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure. The 
    <b>Revision</b> member of the NDIS_OBJECT_HEADER structure, in this case, specifies the revision number of
    the NEIGHBOR_OFFLOAD_STATE_CACHED structure.




## -see-also

<a href="..\ndischimney\nc-ndischimney-w_terminate_offload_handler.md">MiniportTerminateOffload</a>



<a href="..\ndischimney\ns-ndischimney-_offload_state_header.md">OFFLOAD_STATE_HEADER</a>



<a href="..\ndischimney\ns-ndischimney-_neighbor_offload_state_const.md">NEIGHBOR_OFFLOAD_STATE_CONST</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="..\ndischimney\ns-ndischimney-_neighbor_offload_state_delegated.md">
   NEIGHBOR_OFFLOAD_STATE_DELEGATED</a>



<a href="..\ndischimney\nc-ndischimney-w_update_offload_handler.md">MiniportUpdateOffload</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NEIGHBOR_OFFLOAD_STATE_CACHED structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

