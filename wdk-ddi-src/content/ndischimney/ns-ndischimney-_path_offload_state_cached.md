---
UID: NS:ndischimney._PATH_OFFLOAD_STATE_CACHED
title: _PATH_OFFLOAD_STATE_CACHED (ndischimney.h)
description: The PATH_OFFLOAD_STATE_CACHED structure contains the cached variable of a path state object.
old-location: netvista\path_offload_state_cached.htm
tech.root: netvista
ms.assetid: 5afd2499-3f47-481e-9d20-770842f79677
ms.date: 05/02/2018
keywords: ["PATH_OFFLOAD_STATE_CACHED structure"]
ms.keywords: "*PPATH_OFFLOAD_STATE_CACHED, PATH_OFFLOAD_STATE_CACHED, PATH_OFFLOAD_STATE_CACHED structure [Network Drivers Starting with Windows Vista], PPATH_OFFLOAD_STATE_CACHED, PPATH_OFFLOAD_STATE_CACHED structure pointer [Network Drivers Starting with Windows Vista], _PATH_OFFLOAD_STATE_CACHED, ndischimney/PATH_OFFLOAD_STATE_CACHED, ndischimney/PPATH_OFFLOAD_STATE_CACHED, netvista.path_offload_state_cached, tcp_chim_struct_768560e8-d67c-42f3-aa43-78c48e198eef.xml"
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
req.typenames: PATH_OFFLOAD_STATE_CACHED, *PPATH_OFFLOAD_STATE_CACHED
f1_keywords:
 - _PATH_OFFLOAD_STATE_CACHED
 - ndischimney/_PATH_OFFLOAD_STATE_CACHED
 - PPATH_OFFLOAD_STATE_CACHED
 - ndischimney/PPATH_OFFLOAD_STATE_CACHED
 - PATH_OFFLOAD_STATE_CACHED
 - ndischimney/PATH_OFFLOAD_STATE_CACHED
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndischimney.h
api_name:
 - PATH_OFFLOAD_STATE_CACHED
---

# _PATH_OFFLOAD_STATE_CACHED structure


## -description

<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The PATH_OFFLOAD_STATE_CACHED structure contains the cached variable of a path state object.

## -struct-fields

### -field Header

An 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_offload_state_header">OFFLOAD_STATE_HEADER</a> structure. NDIS
     sets the 
     <b>Length</b> member of 
     <b>Header</b> to the size, in bytes, of the PATH_OFFLOAD_STATE_CACHED structure. The 
     <b>RecognizedOptions</b> member of 
     <b>Header</b> is reserved.

### -field PathMtu

The maximum transmission unit (MTU) for the path (see RFC 1191 for IPv4, and RFC 1981 for
     IPv6).

## -remarks

Cached variables are owned and maintained by the host stack. An offload target must not change the
    value of a cached variable unless requested to do so by the host stack. If the value of a cached variable
    changes, the host stack requests an update of the variable, which causes NDIS to call the offload
    target's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_update_offload_handler">MiniportUpdateOffload</a> function.
    When the host stack terminates the offload of one or more state objects by causing NDIS to call the
    offload target's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_terminate_offload_handler">
    MiniportTerminateOffload</a> function, the offload target does not return the value of offloaded
    constant variables to the host stack.

When passed to an offload target, a PATH_OFFLOAD_STATE_CACHED structure is associated with an 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_miniport_offload_block_list">
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure, which contains a header that is formatted as an 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure. The 
    <b>Revision</b> member of the NDIS_OBJECT_HEADER structure, in this case, specifies the revision number of
    the PATH_OFFLOAD_STATE_CACHED structure.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_terminate_offload_handler">MiniportTerminateOffload</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_update_offload_handler">MiniportUpdateOffload</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_offload_state_header">OFFLOAD_STATE_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_path_offload_state_const">PATH_OFFLOAD_STATE_CONST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_path_offload_state_delegated">PATH_OFFLOAD_STATE_DELEGATED</a>

