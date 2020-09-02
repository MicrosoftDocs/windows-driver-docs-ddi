---
UID: NF:ndis.NdisMAllocateSharedMemoryAsyncEx
title: NdisMAllocateSharedMemoryAsyncEx function (ndis.h)
description: Miniport drivers call the NdisMAllocateSharedMemoryAsyncEx function to allocate additional memory shared between the driver and its bus-master DMA NIC, usually when the miniport driver is running low on available NIC receive buffers.
old-location: netvista\ndismallocatesharedmemoryasyncex.htm
tech.root: netvista
ms.assetid: ccbe98ca-7da9-4159-ac1a-c25ec6745ff4
ms.date: 05/02/2018
keywords: ["NdisMAllocateSharedMemoryAsyncEx function"]
ms.keywords: NdisMAllocateSharedMemoryAsyncEx, NdisMAllocateSharedMemoryAsyncEx function [Network Drivers Starting with Windows Vista], ndis/NdisMAllocateSharedMemoryAsyncEx, ndis_sgdma_ref_73efae25-05b5-496f-8c7a-83a6d9f091cc.xml, netvista.ndismallocatesharedmemoryasyncex
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Gather_DMA_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisMAllocateSharedMemoryAsyncEx
 - ndis/NdisMAllocateSharedMemoryAsyncEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NdisMAllocateSharedMemoryAsyncEx
---

# NdisMAllocateSharedMemoryAsyncEx function


## -description

> [!CAUTION]
> For ARM and ARM64 processors, we strongly recommend that NDIS driver writers use WDF DMA or WDM DMA instead of NDIS Scatter/Gather DMA. 
>
> For more information about WDF DMA, see [Handling DMA Operations in KMDF Drivers](https://docs.microsoft.com/windows-hardware/drivers/wdf/handling-dma-operations-in-kmdf-drivers).
>
> For more information about WDM DMA, see the DMA-related child topics of [Managing Input/Output for Drivers](https://docs.microsoft.com/windows-hardware/drivers/kernel/managing-input-output-for-drivers).

Miniport drivers call the 
  <b>NdisMAllocateSharedMemoryAsyncEx</b> function to allocate additional memory shared between the driver and
  its bus-master DMA NIC, usually when the miniport driver is running low on available NIC receive
  buffers.

## -parameters

### -param MiniportDmaHandle 

[in]
A handle to a context area that NDIS uses to manage a DMA resource. The caller obtained this
     handle by calling the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterscattergatherdma">
     NdisMRegisterScatterGatherDma</a> function.

### -param Length 

[in]
The number of bytes to allocate.

### -param Cached 

[in]
This parameter is ignored (cached memory is always used on x86 and x64 systems).

### -param Context 

[in]
A pointer to driver-determined context to be passed to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_allocate_shared_mem_complete">MiniportSharedMemoryAllocateComplete</a> function when it is called.

## -returns

<b>NdisMAllocateSharedMemoryAsyncEx</b> can return one of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
NDIS will call the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_allocate_shared_mem_complete">MiniportSharedMemoryAllocateComplete</a> function and provide information that describes the
       allocated shared memory. If the attempt to allocate shared memory fails, NDIS calls 
       <i>MiniportSharedMemoryAllocateComplete</i> and passes <b>NULL</b> pointers.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
The requested memory could not be allocated at this time. If 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismallocatesharedmemoryasyncex">NdisMAllocateSharedMemoryAsyncEx</a> returns this status, a subsequent call with the same parameters
       might succeed, depending on whether system resources have become available.

</td>
</tr>
</table>

## -remarks

<div class="alert"><b>Note</b>  A miniport driver must have already called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterscattergatherdma">NdisMRegisterScatterGatherDma</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterdmachannel">NdisMRegisterDmaChannel</a> to initialize a
  scatter/gather DMA channel before calling <b>NdisMAllocateSharedMemoryAsyncEx</b>.</div>
<div> </div>
Drivers of bus-master DMA NICs call 
    <b>NdisMAllocateSharedMemoryAsyncEx</b> to dynamically allocate shared memory. Such drivers also allocate
    shared memory space during initialization. These drivers use the dynamically allocated shared memory for
    transfer operations when high network traffic places excessive demands on the existing shared memory
    space.

Such a miniport driver usually maintains one or more state variables to track the number of shared
    memory buffers available for incoming transfers. When the number of available buffers reaches a
    driver-determined low, the miniport driver calls 
    <b>NdisMAllocateSharedMemoryAsyncEx</b> to allocate more buffer space in shared memory. When the number of
    available buffers climbs to a driver-determined high, the miniport driver calls 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismfreesharedmemory">NdisMFreeSharedMemory</a> one or more
    times to release its preceding dynamic allocations.

Usually, such a miniport driver retains the block of shared memory that its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function
    allocated with 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismallocatesharedmemory">NdisMAllocateSharedMemory</a> until
    a NIC is removed. When the NIC is removed, NDIS calls the miniport driver's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a> function. This allocation
    is sufficient to handle an average demand for transfers through the NIC.

A miniport driver should set a limit on how much shared memory it can allocate. This limit is
    driver-specific and should be high enough so that the driver does not run out of buffers. Do not et a
    limit that is excessively high, as this could result in a wasteful consumption of shared memory that
    could reduce system performance.

Any miniport driver that calls 
    <b>NdisMAllocateSharedMemoryAsyncEx</b> or 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismallocatesharedmemory">NdisMAllocateSharedMemory</a> must release all outstanding allocations with one or more calls to 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismfreesharedmemory">NdisMFreeSharedMemory</a> when its NIC is removed.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_allocate_shared_mem_complete">
   MiniportSharedMemoryAllocateComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismallocatesharedmemory">NdisMAllocateSharedMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismfreesharedmemory">NdisMFreeSharedMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterdmachannel">NdisMRegisterDmaChannel</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterscattergatherdma">
   NdisMRegisterScatterGatherDma</a>

