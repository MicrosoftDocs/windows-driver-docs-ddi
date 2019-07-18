---
UID: NC:ndis.MINIPORT_ALLOCATE_SHARED_MEM_COMPLETE
title: MINIPORT_ALLOCATE_SHARED_MEM_COMPLETE (ndis.h)
description: NDIS calls a miniport driver's MiniportSharedMemoryAllocateComplete function to complete a shared memory allocation request that the miniport driver started by calling the NdisMAllocateSharedMemoryAsyncEx function.
old-location: netvista\miniportsharedmemoryallocatecomplete.htm
tech.root: netvista
ms.assetid: d102a001-960c-4fe6-af2d-d740bba744b1
ms.date: 05/02/2018
ms.keywords: MINIPORT_ALLOCATE_SHARED_MEM_COMPLETE, MINIPORT_ALLOCATE_SHARED_MEM_COMPLETE callback, MiniportSharedMemoryAllocateComplete, MiniportSharedMemoryAllocateComplete callback function [Network Drivers Starting with Windows Vista], ndis/MiniportSharedMemoryAllocateComplete, ndis_sgdma_ref_0099c752-42ac-4b2d-9787-98deca358cfc.xml, netvista.miniportsharedmemoryallocatecomplete
ms.topic: callback
f1_keywords:
 - "ndis/MiniportSharedMemoryAllocateComplete"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ndis.h
api_name:
- MiniportSharedMemoryAllocateComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_ALLOCATE_SHARED_MEM_COMPLETE callback function


## -description


NDIS calls a miniport driver's 
   <i>MiniportSharedMemoryAllocateComplete</i> function to complete a shared memory allocation request that
   the miniport driver started by calling the 
   <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismallocatesharedmemoryasyncex">
   NdisMAllocateSharedMemoryAsyncEx</a> function.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_ALLOCATE_SHARED_MEM_COMPLETE</b>
   type. For more information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportAdapterContext [in]

The handle to a context area allocated by the miniport driver in which the driver maintains state
     information for a NIC. The driver allocates this context area in the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_initialize">
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
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismregisterscattergatherdma">
    NdisMRegisterScatterGatherDma</a> function.

Miniport drivers call 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismallocatesharedmemoryasyncex">
    NdisMAllocateSharedMemoryAsyncEx</a> to allocate shared memory. If 
    <b>NdisMAllocateSharedMemoryAsyncEx</b> returns NDIS_STATUS_PENDING, NDIS calls 
    <i>MiniportAllocateSharedMemoryComplete</i> to pass the memory to the miniport driver.

NDIS calls 
    <i>MiniportSharedMemoryAllocateComplete</i> at IRQL PASSIVE_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>MiniportSharedMemoryAllocateComplete</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

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
The <b>MINIPORT_ALLOCATE_SHARED_MEM_COMPLETE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_ALLOCATE_SHARED_MEM_COMPLETE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismallocatesharedmemoryasyncex">
   NdisMAllocateSharedMemoryAsyncEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismregisterscattergatherdma">
   NdisMRegisterScatterGatherDma</a>
 

 

