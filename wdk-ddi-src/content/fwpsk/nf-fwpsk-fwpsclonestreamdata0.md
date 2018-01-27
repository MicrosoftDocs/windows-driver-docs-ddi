---
UID: NF:fwpsk.FwpsCloneStreamData0
title: FwpsCloneStreamData0 function
author: windows-driver-content
description: The FwpsCloneStreamData0 function allocates a clone of an existing FWPS_STREAM_DATA0 data stream.Note  FwpsCloneStreamData0 is a specific version of FwpsCloneStreamData.
old-location: netvista\fwpsclonestreamdata0.htm
old-project: netvista
ms.assetid: 66041ccb-e63a-4843-85ec-d93b924bb335
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: wfp_ref_2_funct_3_fwps_C_e155a116-043a-43e5-af71-db0552806978.xml, FwpsCloneStreamData0, netvista.fwpsclonestreamdata0, FwpsCloneStreamData0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsCloneStreamData0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	LibDef
apilocation: 
-	Fwpkclnt.lib
-	Fwpkclnt.dll
apiname: 
-	FwpsCloneStreamData0
product: Windows
targetos: Windows
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---

# FwpsCloneStreamData0 function


## -description


The 
  <b>FwpsCloneStreamData0</b> function allocates a clone of an existing 
  <a href="..\fwpsk\ns-fwpsk-fwps_stream_data0_.md">FWPS_STREAM_DATA0</a> data stream.
<div class="alert"><b>Note</b>  <b>FwpsCloneStreamData0</b> is a specific version of <b>FwpsCloneStreamData</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -syntax


````
NTSTATUS NTAPI FwpsCloneStreamData0(
  _Inout_  FWPS_STREAM_DATA0 *calloutStreamData,
  _In_opt_ NDIS_HANDLE       netBufferListPoolHandle,
  _In_opt_ NDIS_HANDLE       netBufferPoolHandle,
  _In_     ULONG             allocateCloneFlags,
  _Out_    NET_BUFFER_LIST   **netBufferListChain
);
````


## -parameters




### -param calloutStreamData [in, out]

A pointer to the original 
     <a href="..\fwpsk\ns-fwpsk-fwps_stream_data0_.md">FWPS_STREAM_DATA0</a> structure that is to
     have its 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure cloned.


### -param netBufferListPoolHandle [in, optional]

A 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> pool handle that was
     obtained from a previous call to the 
     <a href="..\ndis\nf-ndis-ndisallocatenetbufferlistpool.md">NdisAllocateNetBufferListPool</a> function. This parameter is optional and can be <b>NULL</b>.


### -param netBufferPoolHandle [in, optional]

A 
     <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> pool handle that was obtained from a
     previous call to the 
     <mshelp:link keywords="netvista.ndisallocatenetbufferpool" tabindex="0"><b>
     NdisAllocateNetBufferPool</b></mshelp:link> function. This parameter is optional and can be <b>NULL</b>.


### -param allocateCloneFlags [in]

There are currently no flags defined for this function. Callout drivers should set this parameter
     to zero.


### -param netBufferListChain [out]

A pointer to a location that receives a pointer to a chain of 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures that describe
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
       <a href="..\fwpsk\ns-fwpsk-fwps_stream_data0_.md">FWPS_STREAM_DATA0</a> structure was
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
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures contained in the
    existing 
    <a href="..\fwpsk\ns-fwpsk-fwps_stream_data0_.md">FWPS_STREAM_DATA0</a> data stream. The
    function trims unused data such that a callout driver can successfully pass the cloned chain to the 
    <mshelp:link keywords="netvista.fwpsstreaminjectasync0" tabindex="0"><b>
    FwpsStreamInjectAsync0</b></mshelp:link> function.

After stream data in the clone NET_BUFFER_LIST structure chain has been successfully injected into the
    network stack, the 
    <a href="..\fwpsk\nc-fwpsk-fwps_inject_complete0.md">completionFn</a> callout function is called for
    each clone NET_BUFFER_LIST structure, and a callout should call 
    <a href="..\fwpsk\nf-fwpsk-fwpsfreeclonenetbufferlist0.md">FwpsFreeCloneNetBufferList0</a> to
    free the clone NET_BUFFER_LIST structure.

A callout should call the 
    <a href="..\fwpsk\nf-fwpsk-fwpsdiscardclonedstreamdata0.md">FwpsDiscardClonedStreamData0</a> function if the cloned stream data is to be discarded without being
    reinjected.



## -see-also

<a href="..\fwpsk\ns-fwpsk-fwps_stream_data0_.md">FWPS_STREAM_DATA0</a>

<a href="..\fwpsk\nf-fwpsk-fwpsfreeclonenetbufferlist0.md">FwpsFreeCloneNetBufferList0</a>

<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>

<a href="..\fwpsk\nf-fwpsk-fwpsdiscardclonedstreamdata0.md">FwpsDiscardClonedStreamData0</a>

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>

<a href="..\fwpsk\nf-fwpsk-fwpsstreaminjectasync0.md">FwpsStreamInjectAsync0</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsCloneStreamData0 function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

