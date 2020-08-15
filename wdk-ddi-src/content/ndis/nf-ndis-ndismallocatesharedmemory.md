---
UID: NF:ndis.NdisMAllocateSharedMemory
title: NdisMAllocateSharedMemory function (ndis.h)
description: NdisMAllocateSharedMemory allocates and maps a host memory range so that the memory range is simultaneously accessible from both the host system and a DMA NIC.
old-location: netvista\ndismallocatesharedmemory.htm
tech.root: netvista
ms.assetid: 8eda6100-598f-405d-a9b3-74424c829a58
ms.date: 05/02/2018
keywords: ["NdisMAllocateSharedMemory function"]
ms.keywords: NdisMAllocateSharedMemory, NdisMAllocateSharedMemory function [Network Drivers Starting with Windows Vista], miniport_memory_shared_ref_c2bf3765-9335-488e-a320-7e955f95eed8.xml, ndis/NdisMAllocateSharedMemory, netvista.ndismallocatesharedmemory
f1_keywords:
 - "ndis/NdisMAllocateSharedMemory"
 - "NdisMAllocateSharedMemory"
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisMAllocateSharedMemory
targetos: Windows
req.typenames: 
---

# NdisMAllocateSharedMemory function


## -description

> [!CAUTION]
> For ARM and ARM64 processors, we strongly recommend that NDIS driver writers use WDF DMA or WDM DMA instead of NDIS Scatter/Gather DMA. 
>
> For more information about WDF DMA, see [Handling DMA Operations in KMDF Drivers](https://docs.microsoft.com/windows-hardware/drivers/wdf/handling-dma-operations-in-kmdf-drivers).
>
> For more information about WDM DMA, see the DMA-related child topics of [Managing Input/Output for Drivers](https://docs.microsoft.com/windows-hardware/drivers/kernel/managing-input-output-for-drivers).

<b>NdisMAllocateSharedMemory</b> allocates and maps a host memory range so that the memory range is
  simultaneously accessible from both the host system and a DMA NIC.


## -parameters




### -param MiniportAdapterHandle 
[in]
Specifies the handle input to 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>.


### -param Length 
[in]
Specifies the number of bytes to allocate.


### -param Cached 
[in]
This parameter is ignored (cached memory is always used on x86 and x64 systems).


### -param VirtualAddress 
[out]
Pointer to a caller-supplied variable in which this function returns the base virtual address of
     the allocation for use by the miniport driver. If 
     <b>NdisMAllocateSharedMemory</b> cannot satisfy its caller, it returns <b>NULL</b> to indicate that no memory
     was allocated.


### -param PhysicalAddress 
[out]
Pointer to a caller-supplied variable in which this function returns a physical address, suitable
     for use by the NIC, that corresponds to that returned at 
     <i>VirtualAddress</i>, or it returns <b>NULL</b>.


## -remarks



<div class="alert"><b>Note</b>  A miniport driver must have already called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterscattergatherdma">NdisMRegisterScatterGatherDma</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterdmachannel">NdisMRegisterDmaChannel</a> to initialize a
  scatter/gather DMA channel before calling <b>NdisMAllocateSharedMemory</b>.</div>
<div> </div>
Microsoft Windows Server 2003, Windows XP Service Pack 1, and later versions of Windows allow both
    bus-master DMA NICs and subordinate DMA NICs to call 
    <b>NdisMAllocateSharedMemory</b>. Prior releases allow only bus-master DMA NICs to call 
    <b>NdisMAllocateSharedMemory</b>. In these prior releases, if 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> did not specify that the NIC is a bus master when it called 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">NdisMSetMiniportAttributes</a>, 
    <b>NdisMAllocateSharedMemory</b> simply returns control without attempting to make an allocation.

<b>NdisMAllocateSharedMemory</b> provides both the mapped virtual address range that the driver uses to
    access the shared memory block and the 
    <a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff557129(v=vs.85)">NDIS_PHYSICAL_ADDRESS</a>-type range that the
    NIC uses. A value returned at 
    <i>PhysicalAddress</i> can be doubly mapped by the system. That is, a "physical" address range described
    by the value at 
    <i>PhysicalAddress</i> and 
    <i>Length</i> can be a range of mapped logical addresses that do not match the host physical addresses for
    the allocation in every possible platform.

<b>NdisMAllocateSharedMemory</b> can be called only from 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>. How large
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
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_allocate_shared_mem_complete">
    MiniportSharedMemoryAllocateComplete</a> function has considerably more flexibility in resolving the
    preceding performance versus size dilemma. 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> should allocate only enough shared memory with 
    <b>NdisMAllocateSharedMemory</b> for a moderate demand for network transfer operations through the NIC if
    the driver has a 
    <i>MiniportSharedMemoryAllocateComplete</i> function. Such a miniport driver can call 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismallocatesharedmemoryasyncex">
    NdisMAllocateSharedMemoryAsyncEx</a> dynamically to allocate more shared memory in periods of heavier
    transfer demand on a NIC. When the high demand for transfers subsides, such a driver calls 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismfreesharedmemory">NdisMFreeSharedMemory</a> to release the
    additional memory it allocated. Note that only bus-master DMA NICs can call 
    <b>NdisMAllocateSharedMemoryAsyncEx</b> and export 
    <i>MiniportSharedMemoryAllocateComplete</i>. This functionality is not supported for subordinate DMA
    NICs.

<b>NdisMAllocateSharedMemory</b> and 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismallocatesharedmemoryasyncex">NdisMAllocateSharedMemoryAsyncEx</a> are the only 
    <b>Ndis<i>Xxx</i></b> functions that can be called to allocate host memory that is shared between the driver, which
    uses virtual addresses, and a NIC, which uses the corresponding logical addresses.

A miniport driver should align the buffers it allocates from shared cached memory on an integral of
    the host data-cache-line boundary to prevent cache-line tearing during DMA. Cache-line tearing can cause
    data-integrity problems in the driver or degrade the driver's (and the system's) I/O performance by
    requiring excessive data-cache flushing to maintain data integrity. 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> can call 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismgetdmaalignment">NdisMGetDmaAlignment</a> to determine the
    alignment boundary in the current platform for device-accessible buffers that the driver will set up
    within an allocated range of shared memory.

A miniport driver should set a limit on how much shared memory it can allocate. This limit is
    driver-specific and should be high enough so that the driver does not run out of buffers. Do not set a
    limit that is excessively high, as this could result in a wasteful consumption of shared memory that
    could reduce system performance.


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> also might call 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissystemprocessorcount">NdisSystemProcessorCount</a> before
    it calls 
    <b>NdisMAllocateSharedMemory</b> if the driver writer decides to allocate a larger shared memory block in
    multiprocessor machines on the assumption that any SMP machine is likely to be a network server with
    higher network-transfer demands on the NIC than a workstation.

If its call to 
    <b>NdisMAllocateSharedMemory</b> fails, 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> can call again requesting a smaller allocation. However, if 
    <i>MiniportInitializeEx</i> cannot allocate sufficient shared memory for the NIC, it must release all
    resources it has already allocated and fail initialization.

If the miniport driver subsequently indicates receives with 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismindicatereceivenetbufferlists">
    NdisMIndicateReceiveNetBufferLists</a>, it must allocate some number of buffer descriptors from buffer
    pool that map the NIC's receive buffers in the shared memory block.

If the allocated memory is cached and, therefore, needs to be flushed on transfers, the miniport
    driver must call 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatemdl">NdisAllocateMdl</a> to allocate an
    NDIS_BUFFER-type descriptor for the shared memory range. The miniport driver must call 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keflushiobuffers">KeFlushIoBuffers</a> with this buffer descriptor
    to perform such a flush.

If a miniport driver calls 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismallocatesharedmemoryasyncex">
    NdisMAllocateSharedMemoryAsyncEx</a> or 
    <b>NdisMAllocateSharedMemory</b>, it must release all outstanding allocations with one or more calls to 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismfreesharedmemory">NdisMFreeSharedMemory</a> when a NIC is
    removed, that is, when its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a> function is called.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keflushiobuffers">KeFlushIoBuffers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_allocate_shared_mem_complete">
   MiniportSharedMemoryAllocateComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatemdl">NdisAllocateMdl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismallocatenetbuffersglist">NdisMAllocateNetBufferSGList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismallocatesharedmemoryasyncex">
   NdisMAllocateSharedMemoryAsyncEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismfreesharedmemory">NdisMFreeSharedMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismgetdmaalignment">NdisMGetDmaAlignment</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismindicatereceivenetbufferlists">
   NdisMIndicateReceiveNetBufferLists</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">NdisMSetMiniportAttributes</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissystemprocessorcount">NdisSystemProcessorCount</a>
 

 

