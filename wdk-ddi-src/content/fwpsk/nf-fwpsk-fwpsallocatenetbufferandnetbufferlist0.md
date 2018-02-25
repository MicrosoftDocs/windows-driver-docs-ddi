---
UID: NF:fwpsk.FwpsAllocateNetBufferAndNetBufferList0
title: FwpsAllocateNetBufferAndNetBufferList0 function
author: windows-driver-content
description: The FwpsAllocateNetBufferAndNetBufferList0 function allocates a new NET_BUFFER_LIST structure.Note  FwpsAllocateNetBufferAndNetBufferList0 is a specific version of FwpsAllocateNetBufferAndNetBufferList.
old-location: netvista\fwpsallocatenetbufferandnetbufferlist0.htm
old-project: netvista
ms.assetid: d7f2d3c0-f2c9-4624-b3e1-9fbbf64c7186
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , 0, A, B, F, FwpsAllocateNetBufferAndNetBufferList0, FwpsAllocateNetBufferAndNetBufferList0 function [Network Drivers Starting with Windows Vista], L, N, a, c, d, e, f, fwpsk/FwpsAllocateNetBufferAndNetBufferList0, i, l, n, netvista.fwpsallocatenetbufferandnetbufferlist0, o, p, r, s, t, u, w, wfp_ref_2_funct_3_fwps_A-B_9a88a8c9-a5fb-48a9-bc42-ae30de234468.xml"
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	fwpkclnt.lib
-	fwpkclnt.dll
apiname:
-	FwpsAllocateNetBufferAndNetBufferList0
product: Windows
targetos: Windows
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---

# FwpsAllocateNetBufferAndNetBufferList0 function


## -description


The 
  <b>FwpsAllocateNetBufferAndNetBufferList0</b> function allocates a new 
  <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.
<div class="alert"><b>Note</b>  <b>FwpsAllocateNetBufferAndNetBufferList0</b> is a specific version of <b>FwpsAllocateNetBufferAndNetBufferList</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -syntax


````
NTSTATUS NTAPI FwpsAllocateNetBufferAndNetBufferList0(
  _In_     NDIS_HANDLE     poolHandle,
  _In_     USHORT          contextSize,
  _In_     USHORT          contextBackFill,
  _In_opt_ MDL             *mdlChain,
  _In_     ULONG           dataOffset,
  _In_     SIZE_T          dataLength,
  _Out_    NET_BUFFER_LIST **netBufferList
);
````


## -parameters




### -param poolHandle [in]

A 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> pool handle that was
     obtained from a previous call to the 
     <a href="..\ndis\nf-ndis-ndisallocatenetbufferlistpool.md">NdisAllocateNetBufferListPool</a> function.


### -param contextSize [in]

The size, in bytes, of used data space in the 
     <a href="..\ndis\ns-ndis-_net_buffer_list_context.md">NET_BUFFER_LIST_CONTEXT</a> structure
     to reserve for the callout driver. The value of this parameter must be a multiple of the value defined
     by <b>MEMORY_ALLOCATION_ALIGNMENT</b>.


### -param contextBackFill [in]

The size, in bytes, of 
     unused data space (backfill space) that the callout driver requires. The 
     <b>FwpsAllocateNetBufferAndNetBufferList0</b> function adds this value to the value specified in the 
     <i>ContextSize</i> parameter and allocates additional space. The value of this parameter must be a
     multiple of the value defined by <b>MEMORY_ALLOCATION_ALIGNMENT</b>.


### -param mdlChain [in, optional]

A pointer to an MDL chain that is used to initialize the preallocated NET_BUFFER structure. This
     parameter is optional and can be <b>NULL</b>.


### -param dataOffset [in]

The initial offset, in bytes, from the start of the buffer to the start of the 
     used data space in the MDL chain. Data space ahead of this offset is 
     unused data space. Therefore, this value also represents the initial amount of available backfill
     space in the MDL chain.


### -param dataLength [in]

The length, in bytes, of the 
     used data space in the MDL chain.


### -param netBufferList [out]

A pointer to a variable that receives a pointer to the new 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.


## -returns



The 
     <b>FwpsAllocateNetBufferAndNetBufferList0</b> function returns one of the following NTSTATUS
     codes.

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
The new 
       <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure was
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



A callout driver calls the 
    <b>FwpsAllocateNetBufferAndNetBufferList0</b> function to allocate a new 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.

This function is a wrapper around the 
    <a href="..\ndis\nf-ndis-ndisallocatenetbufferandnetbufferlist.md">
    NdisAllocateNetBufferAndNetBufferList</a> function, but it is specialized for use by WFP 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff545018">packet injection functions</a>.

After the data described by the new <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure has been successfully injected into the
    network stack, the callout driver frees the new <b>NET_BUFFER_LIST</b> structure by calling the 
    <a href="..\fwpsk\nf-fwpsk-fwpsfreenetbufferlist0.md">
    FwpsFreeNetBufferList0</a> function.




## -see-also

<a href="..\fwpsk\nf-fwpsk-fwpsfreenetbufferlist0.md">FwpsFreeNetBufferList0</a>



<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="..\ndis\ns-ndis-_net_buffer_list_context.md">NET_BUFFER_LIST_CONTEXT</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff545018">Packet Injection Functions</a>



<a href="..\ndis\nf-ndis-ndisallocatenetbufferandnetbufferlist.md">
   NdisAllocateNetBufferAndNetBufferList</a>



<a href="..\ndis\nf-ndis-ndisallocatenetbufferlistpool.md">
   NdisAllocateNetBufferListPool</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsAllocateNetBufferAndNetBufferList0 function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

