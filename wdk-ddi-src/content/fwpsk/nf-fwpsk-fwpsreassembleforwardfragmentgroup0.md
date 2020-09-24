---
UID: NF:fwpsk.FwpsReassembleForwardFragmentGroup0
title: FwpsReassembleForwardFragmentGroup0 function (fwpsk.h)
description: The FwpsReassembleForwardFragmentGroup0 function assembles a list of IP fragments in the forwarding data path into a single packet.Note  FwpsReassembleForwardFragmentGroup0 is a specific version of FwpsReassembleForwardFragmentGroup.
old-location: netvista\fwpsreassembleforwardfragmentgroup0.htm
tech.root: netvista
ms.assetid: 00322dbf-0099-439a-8d65-bf530129cea1
ms.date: 05/02/2018
keywords: ["FwpsReassembleForwardFragmentGroup0 function"]
ms.keywords: FwpsReassembleForwardFragmentGroup0, FwpsReassembleForwardFragmentGroup0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsReassembleForwardFragmentGroup0, netvista.fwpsreassembleforwardfragmentgroup0, wfp_ref_2_funct_3_fwps_R-Z_354e1536-de02-474d-b99f-b5d81875aecd.xml
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Server 2008.
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
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FwpsReassembleForwardFragmentGroup0
 - fwpsk/FwpsReassembleForwardFragmentGroup0
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - fwpkclnt.lib
 - fwpkclnt.dll
api_name:
 - FwpsReassembleForwardFragmentGroup0
---

# FwpsReassembleForwardFragmentGroup0 function


## -description

The 
  <b>FwpsReassembleForwardFragmentGroup0</b> function assembles a list of IP fragments in the forwarding data
  path into a single packet.
<div class="alert"><b>Note</b>  <b>FwpsReassembleForwardFragmentGroup0</b> is a specific version of <b>FwpsReassembleForwardFragmentGroup</b>. See <a href="/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters

### -param addressFamily 

[in]
One of the following address families:
     





#### AF_INET

The IPv4 address family.



#### AF_INET6

The IPv6 address family.

### -param fragmentGroupNblChain 

[in, out]
A pointer to the 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> chain of IP fragments to
     reassemble into a single packet. For more information on the usage of
     this parameter, see Remarks.

### -param netBufferAndNetBufferListPoolHandle 

[in, optional]
An optional 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure pool handle that
     was previously returned from the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlistpool">
     NdisAllocateNetBufferListPool</a> function. The 
     <b>fAllocateNetBuffer</b> member of the 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_pool_parameters">NET_BUFFER_LIST_POOL_PARAMETERS</a> structure that the caller passed to 
     <b>NdisAllocateNetBufferListPool</b> must have been set to <b>TRUE</b>, and the 
     <b>DataSize</b> member set to zero. If this parameter is <b>NULL</b>, NDIS uses an internal pool.

### -param dataBackFill 

[in]
If allocation of 
     unused data space (backfill space) is required, this parameter specifies the number of bytes of
     unused data space to allocate.

### -param flags 

[in]
Reserved. Callout drivers must set this parameter to zero.

### -param reassembledNbl 

[out]
A pointer to a 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> pointer that receives the
     address of the reassembled single network buffer list.

## -returns

The 
     <b>FwpsReassembleForwardFragmentGroup0</b> function returns one of the following NTSTATUS codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The list of IP fragments was successfully reassembled into a single 
       <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FWP_TCPIP_NOT_READY</b></dt>
</dl>
</td>
<td width="60%">
The TCP/IP network stack is not ready to perform packet reassembly. This error can occur if this
       function is called before 
       Tcpip.sys is loaded, or after 
       Tcpip.sys has been unloaded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred.

</td>
</tr>
</table>

## -remarks

The 
    <b>FwpsReassembleForwardFragmentGroup0</b> function assembles a list of IP fragments in the forwarding
    data path, described by a 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> chain, into a single packet.
    The reassembled packet is a single net buffer list that contains one net buffer and references the input
    fragment chain. This function is typically used by edge firewalls to inspect network packets.

The input chain of IP fragments, 
    <i>fragmentGroupNblChain</i>, must be one that is indicated by the 
    <a href="/windows-hardware/drivers/ddi/_netvista/">classifyFn</a> callout function to the
    FWPS_LAYER_IPFORWARD_V4 or FWPS_LAYER_IPFORWARD_V6 layer when the FWP_CONDITION_FLAG_IS_FRAGMENT_GROUP
    flag is set. If this is not the case, the behavior of 
    <b>FwpsReassembleForwardFragmentGroup0</b> is undefined.

Call the 
    <a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsfreenetbufferlist0">FwpsFreeNetBufferList0</a> function to
    free the 
    <i>reassembledNbl</i> NET_BUFFER_LIST structure and all of the associated 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structures and MDL chains. 
    <b>FwpsFreeNetBufferList0</b> dereferences the original input fragment chain.

You can use the following command to view the current "Group Forwarded Fragments" setting for the
    system: 
    <b>netsh interface {ipv4|ipv6} show global</b>.

Because 
    <b>FwpsReassembleForwardFragmentGroup0</b> references the input fragment chain, it is not necessary for
    callouts to reference or clone the chain prior to calling this function.

## -see-also

<a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsfreenetbufferlist0">FwpsFreeNetBufferList0</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_pool_parameters">NET_BUFFER_LIST_POOL_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlistpool">
   NdisAllocateNetBufferListPool</a>



<a href="/windows-hardware/drivers/ddi/_netvista/">classifyFn</a>