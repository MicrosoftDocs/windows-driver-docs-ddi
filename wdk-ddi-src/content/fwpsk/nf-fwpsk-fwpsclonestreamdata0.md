---
UID: NF:fwpsk.FwpsCloneStreamData0
title: FwpsCloneStreamData0 function (fwpsk.h)
description: The FwpsCloneStreamData0 function allocates a clone of an existing FWPS_STREAM_DATA0 data stream.Note  FwpsCloneStreamData0 is a specific version of FwpsCloneStreamData.
old-location: netvista\fwpsclonestreamdata0.htm
tech.root: netvista
ms.assetid: 66041ccb-e63a-4843-85ec-d93b924bb335
ms.date: 05/02/2018
keywords: ["FwpsCloneStreamData0 function"]
ms.keywords: FwpsCloneStreamData0, FwpsCloneStreamData0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsCloneStreamData0, netvista.fwpsclonestreamdata0, wfp_ref_2_funct_3_fwps_C_e155a116-043a-43e5-af71-db0552806978.xml
f1_keywords:
 - "fwpsk/FwpsCloneStreamData0"
 - "FwpsCloneStreamData0"
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Fwpkclnt.lib
- Fwpkclnt.dll
api_name:
- FwpsCloneStreamData0
targetos: Windows
req.typenames: 
---

# FwpsCloneStreamData0 function


## -description


The 
  <b>FwpsCloneStreamData0</b> function allocates a clone of an existing 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_stream_data0_">FWPS_STREAM_DATA0</a> data stream.
<div class="alert"><b>Note</b>  <b>FwpsCloneStreamData0</b> is a specific version of <b>FwpsCloneStreamData</b>. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters




### -param calloutStreamData 
[in, out]
A pointer to the original 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_stream_data0_">FWPS_STREAM_DATA0</a> structure that is to
     have its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure cloned.


### -param netBufferListPoolHandle 
[in, optional]
A 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> pool handle that was
     obtained from a previous call to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlistpool">NdisAllocateNetBufferListPool</a> function. This parameter is optional and can be <b>NULL</b>.


### -param netBufferPoolHandle 
[in, optional]
A 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> pool handle that was obtained from a
     previous call to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferpool">
     NdisAllocateNetBufferPool</a> function. This parameter is optional and can be <b>NULL</b>.


### -param allocateCloneFlags 
[in]
There are currently no flags defined for this function. Callout drivers should set this parameter
     to zero.


### -param netBufferListChain 
[out]
A pointer to a location that receives a pointer to a chain of 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures that describe
     all of the cloned stream data.


## -returns



The 
     <b>FwpsCloneStreamData0</b> function returns one of the following NTSTATUS codes.

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
The clone 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_stream_data0_">FWPS_STREAM_DATA0</a> structure was
       successfully allocated.

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



This cloned stream data can be injected by a callout driver into the TCP/IP network stack at a later
    time.

The 
    <b>FwpsCloneStreamData0</b> function clones the entire chain of 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structures contained in the
    existing 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_stream_data0_">FWPS_STREAM_DATA0</a> data stream. The
    function trims unused data such that a callout driver can successfully pass the cloned chain to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsstreaminjectasync0">
    FwpsStreamInjectAsync0</a> function.

After stream data in the clone NET_BUFFER_LIST structure chain has been successfully injected into the
    network stack, the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_inject_complete0">completionFn</a> callout function is called for
    each clone NET_BUFFER_LIST structure, and a callout should call 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsfreeclonenetbufferlist0">FwpsFreeCloneNetBufferList0</a> to
    free the clone NET_BUFFER_LIST structure.

A callout should call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsdiscardclonedstreamdata0">FwpsDiscardClonedStreamData0</a> function if the cloned stream data is to be discarded without being
    reinjected.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_stream_data0_">FWPS_STREAM_DATA0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsdiscardclonedstreamdata0">FwpsDiscardClonedStreamData0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsfreeclonenetbufferlist0">FwpsFreeCloneNetBufferList0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsstreaminjectasync0">FwpsStreamInjectAsync0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>
 

 

