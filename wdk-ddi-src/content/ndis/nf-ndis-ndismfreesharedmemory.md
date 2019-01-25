---
UID: NF:ndis.NdisMFreeSharedMemory
title: NdisMFreeSharedMemory function (ndis.h)
description: NdisMFreeSharedMemory frees memory that was previously allocated by NdisMAllocateSharedMemory or NdisMAllocateSharedMemoryAsyncEx by the driver of a DMA NIC.
old-location: netvista\ndismfreesharedmemory.htm
tech.root: netvista
ms.assetid: 6ab11b97-e422-4ce9-b98b-51496974cb47
ms.date: 05/02/2018
ms.keywords: NdisMFreeSharedMemory, NdisMFreeSharedMemory function [Network Drivers Starting with Windows Vista], miniport_memory_shared_ref_1aab9bae-ae02-40ba-83ec-1dd880e207cf.xml, ndis/NdisMFreeSharedMemory, netvista.ndismfreesharedmemory
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMFreeSharedMemory (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMFreeSharedMemory (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miniport_Driver_Function, NdisMFreeSharedMemory
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisMFreeSharedMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMFreeSharedMemory function


## -description


<b>NdisMFreeSharedMemory</b> frees memory that was previously allocated by 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff562782">NdisMAllocateSharedMemory</a> or 
  <a href="https://msdn.microsoft.com/ccbe98ca-7da9-4159-ac1a-c25ec6745ff4">
  NdisMAllocateSharedMemoryAsyncEx</a> by the driver of a DMA NIC.


## -parameters




### -param MiniportAdapterHandle [in]

Specifies the handle originally input to 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>.


### -param Length [in]

Specifies the number of bytes originally allocated.


### -param Cached [in]

Specifies <b>TRUE</b> if the original allocation was cacheable.


### -param VirtualAddress [in]

Specifies the base virtual address returned by 
     <b>NdisMAllocateSharedMemory</b> or 
     <b>NdisMAllocateSharedMemoryAsyncEx</b>.


### -param PhysicalAddress [in]

Specifies the corresponding physical address returned by 
     <b>NdisMAllocateSharedMemory</b> or 
     <b>NdisMAllocateSharedMemoryAsyncEx</b>.


## -returns



None




## -remarks



If it has already made a successful call to 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff562782">NdisMAllocateSharedMemory</a> or 
    <a href="https://msdn.microsoft.com/ccbe98ca-7da9-4159-ac1a-c25ec6745ff4">
    NdisMAllocateSharedMemoryAsyncEx</a>, the miniport driver of a DMA device calls 
    <b>NdisMFreeSharedMemory</b> if any of the following occurs:

<ul>
<li>
Its 
      <i>MiniportInitializeEx</i> function is unable to initialize the NIC, so this function must release all
      existing claims on hardware resources for that NIC before it returns control.

</li>
<li>
The NIC for which the miniport driver allocated the memory is being removed.

</li>
<li>
The driver is being unloaded, whether because the system is shutting down or because the user
      reconfigured the network components used in the machine.

</li>
<li>
The driver allocated additional shared memory with 
      <b>NdisMAllocateSharedMemoryAsyncEx</b> when I/O demand on a NIC was high but network traffic has now
      subsided to an average level.

</li>
</ul>
A miniport driver cannot call 
    <b>NdisMFreeSharedMemory</b> to free a subrange within an allocated shared memory range. The parameters
    passed to 
    <b>NdisMFreeSharedMemory</b> must match exactly those that were passed to 
    <b>NdisMAllocateSharedMemory</b> or 
    <b>NdisMAllocateSharedMemoryAsyncEx</b>.

<b>NdisMFreeSharedMemory</b> cannot be called from a 
    <a href="https://msdn.microsoft.com/7c88ff02-e791-4642-ad40-78f2ef2cba7d">MiniportShutdownEx</a> function.

Microsoft Windows Server 2003, Windows XP Service Pack 1, and later versions of Windows allow both
    bus-master DMA NICs and subordinate DMA NICs to call 
    <b>NdisMFreeSharedMemory</b>. Prior releases allow only bus-master DMA NICs to call 
    <b>NdisMFreeSharedMemory</b>.




## -see-also




<a href="https://msdn.microsoft.com/b8d452b4-bef3-4991-87cf-fac15bedfde4">MiniportHaltEx</a>



<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/d102a001-960c-4fe6-af2d-d740bba744b1">
   MiniportSharedMemoryAllocateComplete</a>



<a href="https://msdn.microsoft.com/7c88ff02-e791-4642-ad40-78f2ef2cba7d">MiniportShutdownEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562782">NdisMAllocateSharedMemory</a>



<a href="https://msdn.microsoft.com/ccbe98ca-7da9-4159-ac1a-c25ec6745ff4">
   NdisMAllocateSharedMemoryAsyncEx</a>
 

 

