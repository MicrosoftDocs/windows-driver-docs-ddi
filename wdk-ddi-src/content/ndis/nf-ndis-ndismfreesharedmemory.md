---
UID: NF:ndis.NdisMFreeSharedMemory
title: NdisMFreeSharedMemory function
author: windows-driver-content
description: NdisMFreeSharedMemory frees memory that was previously allocated by NdisMAllocateSharedMemory or NdisMAllocateSharedMemoryAsyncEx by the driver of a DMA NIC.
old-location: netvista\ndismfreesharedmemory.htm
old-project: netvista
ms.assetid: 6ab11b97-e422-4ce9-b98b-51496974cb47
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NdisMFreeSharedMemory function [Network Drivers Starting with Windows Vista], netvista.ndismfreesharedmemory, miniport_memory_shared_ref_1aab9bae-ae02-40ba-83ec-1dd880e207cf.xml, ndis/NdisMFreeSharedMemory, NdisMFreeSharedMemory
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisMFreeSharedMemory
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---

# NdisMFreeSharedMemory function


## -description


<b>NdisMFreeSharedMemory</b> frees memory that was previously allocated by 
  <a href="..\ndis\nf-ndis-ndismallocatesharedmemory.md">NdisMAllocateSharedMemory</a> or 
  <a href="..\ndis\nf-ndis-ndismallocatesharedmemoryasyncex.md">
  NdisMAllocateSharedMemoryAsyncEx</a> by the driver of a DMA NIC.


## -syntax


````
VOID NdisMFreeSharedMemory(
  _In_ NDIS_HANDLE           MiniportAdapterHandle,
  _In_ ULONG                 Length,
  _In_ BOOLEAN               Cached,
  _In_ PVOID                 VirtualAddress,
  _In_ NDIS_PHYSICAL_ADDRESS PhysicalAddress
);
````


## -parameters




### -param MiniportAdapterHandle [in]

Specifies the handle originally input to 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>.


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
    <a href="..\ndis\nf-ndis-ndismallocatesharedmemory.md">NdisMAllocateSharedMemory</a> or 
    <a href="..\ndis\nf-ndis-ndismallocatesharedmemoryasyncex.md">
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
    <a href="..\ndis\nc-ndis-miniport_shutdown.md">MiniportShutdownEx</a> function.

Microsoft Windows Server 2003, Windows XP Service Pack 1, and later versions of Windows allow both
    bus-master DMA NICs and subordinate DMA NICs to call 
    <b>NdisMFreeSharedMemory</b>. Prior releases allow only bus-master DMA NICs to call 
    <b>NdisMFreeSharedMemory</b>.




## -see-also

<a href="..\ndis\nc-ndis-miniport_allocate_shared_mem_complete.md">
   MiniportSharedMemoryAllocateComplete</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a>



<a href="..\ndis\nf-ndis-ndismallocatesharedmemoryasyncex.md">
   NdisMAllocateSharedMemoryAsyncEx</a>



<a href="..\ndis\nc-ndis-miniport_shutdown.md">MiniportShutdownEx</a>



<a href="..\ndis\nf-ndis-ndismallocatesharedmemory.md">NdisMAllocateSharedMemory</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMFreeSharedMemory function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

