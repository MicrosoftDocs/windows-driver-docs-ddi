---
UID: NS:ndischimney._PATH_OFFLOAD_STATE_CONST
title: _PATH_OFFLOAD_STATE_CONST (ndischimney.h)
description: The PATH_OFFLOAD_STATE_CONST structure contains the constant variables of a path state object.
old-location: netvista\path_offload_state_const.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["PATH_OFFLOAD_STATE_CONST structure"]
ms.keywords: "*PPATH_OFFLOAD_STATE_CONST, PATH_OFFLOAD_STATE_CONST, PATH_OFFLOAD_STATE_CONST structure [Network Drivers Starting with Windows Vista], PPATH_OFFLOAD_STATE_CONST, PPATH_OFFLOAD_STATE_CONST structure pointer [Network Drivers Starting with Windows Vista], _PATH_OFFLOAD_STATE_CONST, ndischimney/PATH_OFFLOAD_STATE_CONST, ndischimney/PPATH_OFFLOAD_STATE_CONST, netvista.path_offload_state_const, tcp_chim_struct_4412519c-3610-4f0a-a4c6-400ff661d205.xml"
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
targetos: Windows
req.typenames: PATH_OFFLOAD_STATE_CONST, *PPATH_OFFLOAD_STATE_CONST
f1_keywords:
 - _PATH_OFFLOAD_STATE_CONST
 - ndischimney/_PATH_OFFLOAD_STATE_CONST
 - PPATH_OFFLOAD_STATE_CONST
 - ndischimney/PPATH_OFFLOAD_STATE_CONST
 - PATH_OFFLOAD_STATE_CONST
 - ndischimney/PATH_OFFLOAD_STATE_CONST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndischimney.h
api_name:
 - _PATH_OFFLOAD_STATE_CONST
 - PPATH_OFFLOAD_STATE_CONST
 - PATH_OFFLOAD_STATE_CONST
---

# _PATH_OFFLOAD_STATE_CONST structure


## -description

<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The PATH_OFFLOAD_STATE_CONST structure contains the constant variables of a path state object.

## -struct-fields

### -field Header

An 
     <a href="/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_offload_state_header">OFFLOAD_STATE_HEADER</a> structure. NDIS
     sets the 
     <b>Length</b> member of 
     <b>Header</b> to the size, in bytes, of the PATH_OFFLOAD_STATE_CONST structure. The 
     <b>RecognizedOptions</b> member of 
     <b>Header</b> is reserved.

### -field SourceAddress

A pointer to the source IP address of a TCP connection. If the TCP connection is over IPv4, the
     address is a 4-byte IPv4 address. If the TCP connection is over IPv6, the address is a 16-byte IPv6
     address. The source address bytes are always in network byte order.

### -field DestinationAddress

A pointer to the destination IP address of a TCP connection. If the TCP connection is over IPv4,
     the address is a 4-byte IPv4 address. If the TCP connection is over IPv6, the address is a 16-byte IPv6
     address. The destination address bytes are always in network byte order.

## -remarks

The value of each path constant variable does not change during the life of a TCP connection. Neither
    the host stack nor the offload target changes the values of a path constant variable. When the host stack
    terminates the offload of the path state object by causing NDIS to call the offload target's 
    <a href="/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_terminate_offload_handler">
    MiniportTerminateOffload</a> function, the offload target does not return the value of the offloaded
    path constant variables to the host stack.

When passed to an offload target, a PATH_OFFLOAD_STATE_CONST structure is associated with an 
    <a href="/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_miniport_offload_block_list">
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure, which contains a header that is formatted as an 
    <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure. The 
    <b>Revision</b> member of the NDIS_OBJECT_HEADER structure, in this case, specifies the revision number of
    the PATH_OFFLOAD_STATE_CONST structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_terminate_offload_handler">MiniportTerminateOffload</a>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_offload_state_header">OFFLOAD_STATE_HEADER</a>



<a href="/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_path_offload_state_cached">PATH_OFFLOAD_STATE_CACHED</a>



<a href="/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_path_offload_state_delegated">PATH_OFFLOAD_STATE_DELEGATED</a>

