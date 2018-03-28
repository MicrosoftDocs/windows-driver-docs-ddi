---
UID: NF:ndis.NdisMAllocateSharedMemory
title: NdisMAllocateSharedMemory function
author: windows-driver-content
description: NdisMAllocateSharedMemory allocates and maps a host memory range so that the memory range is simultaneously accessible from both the host system and a DMA NIC.
old-location: netvista\ndismallocatesharedmemory.htm
old-project: netvista
ms.assetid: 8eda6100-598f-405d-a9b3-74424c829a58
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisMAllocateSharedMemory, NdisMAllocateSharedMemory function [Network Drivers Starting with Windows Vista], miniport_memory_shared_ref_c2bf3765-9335-488e-a320-7e955f95eed8.xml, ndis/NdisMAllocateSharedMemory, netvista.ndismallocatesharedmemory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
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
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisMAllocateSharedMemory
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMAllocateSharedMemory function


## -description


<b>NdisMAllocateSharedMemory</b> allocates and maps a host memory range so that the memory range is
  simultaneously accessible from both the host system and a DMA NIC.


## -parameters




### -param MiniportAdapterHandle [in]

Specifies the handle input to 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>.


### -param Length [in]

Specifies the number of bytes to allocate.


### -param Cached [in]

This parameter is ignored (cached memory is always used on x86 and x64 systems).


### -param VirtualAddress [out]

Pointer to a caller-supplied variable in which this function returns the base virtual address of
     the allocation for use by the miniport driver. If 
     <b>NdisMAllocateSharedMemory</b> cannot satisfy its caller, it returns <b>NULL</b> to indicate that no memory
     was allocated.


### -param PhysicalAddress [out]

Pointer to a caller-supplied variable in which this function returns a physical address, suitable
     for use by the NIC, that corresponds to that returned at 
     <i>VirtualAddress</i>, or it returns <b>NULL</b>.


## -returns



None




## -remarks



<div class="alert"><b>Note</b>  A miniport driver must have already called <a href="https://msdn.microsoft.com/library/windows/hardware/ff563659">NdisMRegisterScatterGatherDma</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff563646">NdisMRegisterDmaChannel</a> to initialize a
  scatter/gather DMA channel before calling <b>NdisMAllocateSharedMemory</b>.</div>
<div> </div>
Microsoft Windows Server 2003, Windows XP Service Pack 1, and later versions of Windows allow both
    bus-master DMA NICs and subordinate DMA NICs to call 
    <b>NdisMAllocateSharedMemory</b>. Prior releases allow only bus-master DMA NICs to call 
    <b>NdisMAllocateSharedMemory</b>. In these prior releases, if 
    <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a> did not specify that the NIC is a bus master when it called 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff563672">NdisMSetMiniportAttributes</a>, 
    <b>NdisMAllocateSharedMemory</b> simply returns control without attempting to make an allocation.

<b>NdisMAllocateSharedMemory</b> provides both the mapped virtual address range that the driver uses to
    access the shared memory block and the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff557129">NDIS_PHYSICAL_ADDRESS</a>-type range that the
    NIC uses. A value returned at 
    <i>PhysicalAddress</i> can be doubly mapped by the system. That is, a "physical" address range described
    by the value at 
    <i>PhysicalAddress</i> and 
    <i>Length</i> can be a range of mapped logical addresses that do not match the host physical addresses for
    the allocation in every possible platform.

<b>NdisMAllocateSharedMemory</b> can be called only from 
    <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>. How large
    an allocation to request depends on how the driver writer, knowing the capabilities and features of the
    NIC, decides to make the tradeoff between the following performance versus size dilemma:

<ul>
<li>
In periods of high network traffic, a miniport driver cannot maintain high I/O throughput if it runs
      low on shared memory space for device-accessible data buffers.

For example, the miniport driver could be indicating receive buffers in shared memory faster than
      such buffers are being returned from bound protocol drivers when a flood of receives come in to a NIC.
      If all its shared memory space is consumed by outstanding receive buffers, the miniport driver might
      have to disable receive interrupts on a NIC until it has some shared memory space available for receive
      buffers.

</li>
<li>
On the other hand, calling 
      <b>NdisMAllocateSharedMemory</b> with a 
      <i>Length</i> chosen to anticipate some maximum transfer demand makes the driver's image larger and its
      resource usage quite uneconomical, except for rare periods of very high I/O demand. Moreover, 
      <b>NdisMAllocateSharedMemory</b> might not give the driver such a large block if insufficient system
      memory is available, forcing the driver to fail initialization.

</li>
</ul>
A miniport driver that supplies a 
    <a href="https://msdn.microsoft.com/d102a001-960c-4fe6-af2d-d740bba744b1">
    MiniportSharedMemoryAllocateComplete</a> function has considerably more flexibility in resolving the
    preceding performance versus size dilemma. 
    <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a> should allocate only enough shared memory with 
    <b>NdisMAllocateSharedMemory</b> for a moderate demand for network transfer operations through the NIC if
    the driver has a 
    <i>MiniportSharedMemoryAllocateComplete</i> function. Such a miniport driver can call 
    <a href="https://msdn.microsoft.com/ccbe98ca-7da9-4159-ac1a-c25ec6745ff4">
    NdisMAllocateSharedMemoryAsyncEx</a> dynamically to allocate more shared memory in periods of heavier
    transfer demand on a NIC. When the high demand for transfers subsides, such a driver calls 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff563589">NdisMFreeSharedMemory</a> to release the
    additional memory it allocated. Note that only bus-master DMA NICs can call 
    <b>NdisMAllocateSharedMemoryAsyncEx</b> and export 
    <i>MiniportSharedMemoryAllocateComplete</i>. This functionality is not supported for subordinate DMA
    NICs.

<b>NdisMAllocateSharedMemory</b> and 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff562784">NdisMAllocateSharedMemoryAsyncEx</a> are the only 
    <b>Ndis<i>Xxx</i></b> functions that can be called to allocate host memory that is shared between the driver, which
    uses virtual addresses, and a NIC, which uses the corresponding logical addresses.

A miniport driver should align the buffers it allocates from shared cached memory on an integral of
    the host data-cache-line boundary to prevent cache-line tearing during DMA. Cache-line tearing can cause
    data-integrity problems in the driver or degrade the driver's (and the system's) I/O performance by
    requiring excessive data-cache flushing to maintain data integrity. 
    <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a> can call 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff563593">NdisMGetDmaAlignment</a> to determine the
    alignment boundary in the current platform for device-accessible buffers that the driver will set up
    within an allocated range of shared memory.

A miniport driver should set a limit on how much shared memory it can allocate. This limit is
    driver-specific and should be high enough so that the driver does not run out of buffers. Do not set a
    limit that is excessively high, as this could result in a wasteful consumption of shared memory that
    could reduce system performance.


<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a> also might call 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564579">NdisSystemProcessorCount</a> before
    it calls 
    <b>NdisMAllocateSharedMemory</b> if the driver writer decides to allocate a larger shared memory block in
    multiprocessor machines on the assumption that any SMP machine is likely to be a network server with
    higher network-transfer demands on the NIC than a workstation.

If its call to 
    <b>NdisMAllocateSharedMemory</b> fails, 
    <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a> can call again requesting a smaller allocation. However, if 
    <i>MiniportInitializeEx</i> cannot allocate sufficient shared memory for the NIC, it must release all
    resources it has already allocated and fail initialization.

If the miniport driver subsequently indicates receives with 
    <a href="https://msdn.microsoft.com/b87dba3e-c18f-4ea2-8bd5-ec3cdafc534b">
    NdisMIndicateReceiveNetBufferLists</a>, it must allocate some number of buffer descriptors from buffer
    pool that map the NIC's receive buffers in the shared memory block.

If the allocated memory is cached and, therefore, needs to be flushed on transfers, the miniport
    driver must call 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561605">NdisAllocateMdl</a> to allocate an
    NDIS_BUFFER-type descriptor for the shared memory range. The miniport driver must call 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff552041">KeFlushIoBuffers</a> with this buffer descriptor
    to perform such a flush.

If a miniport driver calls 
    <a href="https://msdn.microsoft.com/ccbe98ca-7da9-4159-ac1a-c25ec6745ff4">
    NdisMAllocateSharedMemoryAsyncEx</a> or 
    <b>NdisMAllocateSharedMemory</b>, it must release all outstanding allocations with one or more calls to 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff563589">NdisMFreeSharedMemory</a> when a NIC is
    removed, that is, when its 
    <a href="https://msdn.microsoft.com/b8d452b4-bef3-4991-87cf-fac15bedfde4">MiniportHaltEx</a> function is called.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552041">KeFlushIoBuffers</a>



<a href="https://msdn.microsoft.com/b8d452b4-bef3-4991-87cf-fac15bedfde4">MiniportHaltEx</a>



<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/d102a001-960c-4fe6-af2d-d740bba744b1">
   MiniportSharedMemoryAllocateComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561605">NdisAllocateMdl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562776">NdisMAllocateNetBufferSGList</a>



<a href="https://msdn.microsoft.com/ccbe98ca-7da9-4159-ac1a-c25ec6745ff4">
   NdisMAllocateSharedMemoryAsyncEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563589">NdisMFreeSharedMemory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563593">NdisMGetDmaAlignment</a>



<a href="https://msdn.microsoft.com/b87dba3e-c18f-4ea2-8bd5-ec3cdafc534b">
   NdisMIndicateReceiveNetBufferLists</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563672">NdisMSetMiniportAttributes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564579">NdisSystemProcessorCount</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMAllocateSharedMemory function%20 RELEASE:%20(3/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

