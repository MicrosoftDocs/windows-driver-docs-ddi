---
UID: NC:ndis.MINIPORT_ALLOCATE_SHARED_MEM_COMPLETE
title: MINIPORT_ALLOCATE_SHARED_MEM_COMPLETE
author: windows-driver-content
description: NDIS calls a miniport driver's MiniportSharedMemoryAllocateComplete function to complete a shared memory allocation request that the miniport driver started by calling the NdisMAllocateSharedMemoryAsyncEx function.
old-location: netvista\miniportsharedmemoryallocatecomplete.htm
old-project: netvista
ms.assetid: d102a001-960c-4fe6-af2d-d740bba744b1
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: MINIPORT_ALLOCATE_SHARED_MEM_COMPLETE, MiniportSharedMemoryAllocateComplete, MiniportSharedMemoryAllocateComplete callback function [Network Drivers Starting with Windows Vista], ndis/MiniportSharedMemoryAllocateComplete, ndis_sgdma_ref_0099c752-42ac-4b2d-9787-98deca358cfc.xml, netvista.miniportsharedmemoryallocatecomplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndis.h
api_name:
-	MiniportSharedMemoryAllocateComplete
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# MINIPORT_ALLOCATE_SHARED_MEM_COMPLETE callback


## -description


NDIS calls a miniport driver's 
   <i>MiniportSharedMemoryAllocateComplete</i> function to complete a shared memory allocation request that
   the miniport driver started by calling the 
   <a href="https://msdn.microsoft.com/ccbe98ca-7da9-4159-ac1a-c25ec6745ff4">
   NdisMAllocateSharedMemoryAsyncEx</a> function.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_ALLOCATE_SHARED_MEM_COMPLETE</b>
   type. For more information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportAdapterContext [in]

The handle to a context area allocated by the miniport driver in which the driver maintains state
     information for a NIC. The driver allocates this context area in the 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">
     MiniportInitializeEx</a> function.


### -param VirtualAddress [in]

The base virtual address of the shared memory that the miniport driver allocated by calling 
     <b>NdisMAllocateSharedMemoryAsyncEx</b>. 
     <i>VirtualAddress</i> is <b>NULL</b> if the allocation attempt failed.


### -param PhysicalAddress [in]

The base physical address for the NIC to use that is mapped to the address that the 
     <i>VirtualAddress</i> parameter specifies.


### -param Length [in]

The number of bytes that 
     <b>NdisMAllocateSharedMemoryAsyncEx</b> allocated.


### -param Context [in]

A pointer to a context area that the miniport driver specified in the preceding call to 
     <b>NdisMAllocateSharedMemoryAsyncEx</b>.


## -returns



None




## -remarks



<i>MiniportAllocateSharedMemoryComplete</i> is an optional function for miniport drivers. A miniport
    driver registers a 
    <i>MiniportAllocateSharedMemoryComplete</i> function in the NDIS_SG_DMA_DESCRIPTION structure that the
    driver passed to the 
    <a href="https://msdn.microsoft.com/90ce64a2-9140-4b5f-88aa-b4f01a3d0c6f">
    NdisMRegisterScatterGatherDma</a> function.

Miniport drivers call 
    <a href="https://msdn.microsoft.com/ccbe98ca-7da9-4159-ac1a-c25ec6745ff4">
    NdisMAllocateSharedMemoryAsyncEx</a> to allocate shared memory. If 
    <b>NdisMAllocateSharedMemoryAsyncEx</b> returns NDIS_STATUS_PENDING, NDIS calls 
    <i>MiniportAllocateSharedMemoryComplete</i> to pass the memory to the miniport driver.

NDIS calls 
    <i>MiniportSharedMemoryAllocateComplete</i> at IRQL PASSIVE_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>MiniportSharedMemoryAllocateComplete</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportSharedMemoryAllocateComplete</i> function that is named "MySharedMemoryAllocateComplete", use the <b>MINIPORT_ALLOCATE_SHARED_MEM_COMPLETE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MINIPORT_ALLOCATE_SHARED_MEM_COMPLETE MySharedMemoryAllocateComplete;</pre>
</td>
</tr>
</table></span></div>
Then, implement your function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
 MySharedMemoryAllocateComplete(
    NDIS_HANDLE  MiniportAdapterContext,
    PVOID  VirtualAddress,
    PNDIS_PHYSICAL_ADDRESS  PhysicalAddress,
    ULONG  Length,
    PVOID  Context
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>MINIPORT_ALLOCATE_SHARED_MEM_COMPLETE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_ALLOCATE_SHARED_MEM_COMPLETE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/ccbe98ca-7da9-4159-ac1a-c25ec6745ff4">
   NdisMAllocateSharedMemoryAsyncEx</a>



<a href="https://msdn.microsoft.com/90ce64a2-9140-4b5f-88aa-b4f01a3d0c6f">
   NdisMRegisterScatterGatherDma</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_ALLOCATE_SHARED_MEM_COMPLETE callback function%20 RELEASE:%20(3/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

