---
UID: NC:wdm.PBUILD_SCATTER_GATHER_LIST_EX
title: PBUILD_SCATTER_GATHER_LIST_EX (wdm.h)
description: The BuildScatterGatherListEx routine allocates the resources that are required for a DMA transfer, builds a scatter/gather list, and calls the driver-supplied AdapterListControl routine to initiate the DMA transfer.
old-location: kernel\buildscattergatherlistex.htm
tech.root: kernel
ms.assetid: A1A89D52-5F39-45E4-AFBE-20DAD0E49442
ms.date: 04/30/2018
keywords: ["PBUILD_SCATTER_GATHER_LIST_EX callback function"]
ms.keywords: BuildScatterGatherListEx, BuildScatterGatherListEx callback function [Kernel-Mode Driver Architecture], DMA_SYNCHRONOUS_CALLBACK, PBUILD_SCATTER_GATHER_LIST_EX, PBUILD_SCATTER_GATHER_LIST_EX callback, kernel.buildscattergatherlistex, wdm/BuildScatterGatherListEx
f1_keywords:
 - "wdm/BuildScatterGatherListEx"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdm.h
api_name:
- BuildScatterGatherListEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# PBUILD_SCATTER_GATHER_LIST_EX callback function

## -description

The **BuildScatterGatherListEx** routine allocates the resources that are required for a DMA transfer, builds a scatter/gather list, and calls  the driver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_list_control">AdapterListControl</a> routine to initiate the DMA transfer.
<div class="alert">**Note**  Do not call this routine for a system DMA device.</div><div> </div>

## -parameters




### -param DmaAdapter [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_adapter">DMA_ADAPTER</a> structure. This structure is the adapter object that represents the driver's bus-master DMA device or system DMA channel. The caller obtained this pointer from a previous call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a> routine.


### -param DeviceObject [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure. This structure is the physical device object (PDO) that represents the target device for the requested DMA operation.


### -param DmaTransferContext [in]

A pointer to an initialized DMA transfer context. This context was initialized by a previous call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pinitialize_dma_transfer_context">InitializeDmaTransferContext</a> routine. This context must be unique across all adapter allocation requests. To cancel a pending allocation request, the caller must supply the DMA transfer context for the request to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pcancel_adapter_channel">CancelAdapterChannel</a> routine.


### -param Mdl [in]

A pointer to an MDL chain that describes the physical page layout for a collection of locked-down buffers in virtual memory. The scatter/gather list for the DMA transfer will use the region of this memory that is specified by the *Offset* and *Length* parameters. For more information about MDL chains, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-mdls">Using MDLs</a>.


### -param Offset [in]

The starting offset for the scatter/gather DMA transfer. This parameter is a byte offset from the start of the buffer in the first MDL in the MDL chain. If the MDLs in the MDL chain specify a total of N bytes of buffer space, valid values of *Offset* are in the range 0 to N–1.


### -param Length [in]

The size, in bytes, of the DMA transfer. If the MDL chain specifies a total of N bytes of buffer space, valid values of *Length* are in the range 1 to N–*Offset*.


### -param Flags [in]

The adapter channel allocation flags. The following flag is supported.

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="DMA_SYNCHRONOUS_CALLBACK"></a><a id="dma_synchronous_callback"></a><dl>
<dt><b>DMA_SYNCHRONOUS_CALLBACK**</dt>
</dl>
</td>
<td width="60%">
The <b>BuildScatterGatherListEx</b> routine is called synchronously. If this flag is set, and the required DMA resources are not immediately available, the call fails and returns STATUS_INSUFFICIENT_RESOURCES.

</td>
</tr>
</table>

If the **DMA_SYNCHRONOUS_CALLBACK** flag is set, the *ExecutionRoutine* parameter is optional and can be **NULL**. If this flag is not set, *ExecutionRoutine* must be a valid, non-**NULL** pointer. For more information about this flag, see the Remarks section.


### -param ExecutionRoutine [in, optional]

A pointer to the driver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_list_control">AdapterListControl</a> routine that initiates the DMA transfer for the driver. The I/O manager calls the *AdapterListControl* routine after the required resources are allocated for the adapter object. After the *AdapterListControl* routine returns, the I/O manager automatically frees the adapter object and the resources that were allocated for this object.

If the **DMA_SYNCHRONOUS_CALLBACK** flag is set, *ExecutionRoutine* is optional and can be **NULL**.  If *ExecutionRoutine* is **NULL**, the caller can use the resources allocated by **BuildScatterGatherListEx**. For more information, see the Remarks section.


### -param Context [in, optional]

The driver-determined, adapter-control context. This context is passed to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_list_control">AdapterListControl</a> routine as the *Context* parameter.


### -param WriteToDevice [in]

The direction of the DMA transfer. Set this parameter to **TRUE** for a write operation, which transfers data from memory to the device. Set this parameter to **FALSE** for a read operation, which transfers data from the device to memory.


### -param ScatterGatherBuffer [in]

A pointer to a caller-allocated buffer into which the routine writes the scatter/gather list for the DMA transfer. This list begins with a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_scatter_gather_list">SCATTER_GATHER_LIST</a> structure, which is followed by a **SCATTER_GATHER_ELEMENT** array.


### -param ScatterGatherLength


### -param DmaCompletionRoutine [in, optional]

Not used. Set to **NULL**.


### -param CompletionContext [in, optional]

Not used. Set to **NULL**.


### -param ScatterGatherList [out, optional]

A pointer to a variable into which the routine writes a pointer to the scatter/gather list for the DMA transfer. This list begins with a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_scatter_gather_list">SCATTER_GATHER_LIST</a> structure, which contains a pointer to a **SCATTER_GATHER_ELEMENT** array. This output pointer always matches the *ScatterGatherBuffer* parameter value.

If the **DMA_SYNCHRONOUS_CALLBACK** flag is set and the *ExecutionRoutine* parameter is **NULL**, *ScatterGatherList* must be a valid, non-**NULL** pointer. If *ExecutionRoutine* is non-**NULL**, *ScatterGatherList* is optional and can be **NULL** if the calling driver does not require the scatter/gather list. The **BuildScatterGatherListEx** call fails if the **DMA_SYNCHRONOUS_CALLBACK** flag is set and *ScatterGatherList* and *ExecutionRoutine* are both **NULL**, or if the **DMA_SYNCHRONOUS_CALLBACK** flag is not set and *ExecutionRoutine* is **NULL**.


#### - ScatterGatherBufferLength [in]

The size, in bytes, of the buffer passed in the *ScatterGatherBuffer* parameter. The allocated buffer size must be large enough to contain the scatter/gather list, plus internal data that the operating system stores in this buffer. To calculate the required buffer size, call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pget_dma_transfer_info">GetDmaTransferInfo</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pcalculate_scatter_gather_list_size">CalculateScatterGatherList</a> routine.

## -returns

**BuildScatterGatherListEx** returns STATUS_SUCCESS if the call is successful. Possible error return values include the following status codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETERS</b></dt>
</dl>
</td>
<td width="60%">
The routine failed due to invalid parameter values passed by the caller.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The caller-supplied buffer in <i>ScatterGatherBuffer</i> is too small to contain the scatter/gather list.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The routine failed to allocate resources required for the DMA transfer.

</td>
</tr>
</table>

## -remarks

**BuildScatterGatherListEx*** is not a system routine that can be called directly by name. This routine can be called only by pointer from the address returned in a *<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_operations">DMA_OPERATIONS</a>* structure. Drivers obtain the address of this routine by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdmaadapter">IoGetDmaAdapter</a> with the **Version** member of the *DeviceDescription* parameter set to DEVICE_DESCRIPTION_VERSION3. If **IoGetDmaAdapter** returns **NULL**, the routine is not available on your platform.

Use **BuildScatterGatherListEx** only for bus-master adapters. Do not use this routine for a system DMA adapter.

**BuildScatterGatherListEx** is similar to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pget_scatter_gather_list_ex">GetScatterGatherListEx</a> routine, except that it requires the caller to allocate the buffer for the scatter/gather list.

For example, a driver might preallocate one or more scatter/gather buffers during device initialization. Later, a **BuildScatterGatherListEx** call that uses such a buffer can succeed in conditions of low memory availability that might cause a **GetScatterGatherListEx** call to fail.

By default, **BuildScatterGatherListEx** returns asynchronously, without waiting for the requested resource allocation to complete. After this return, the caller can, if necessary, cancel the pending allocation request by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pcancel_adapter_channel">CancelAdapterChannel</a> routine.

If the calling driver sets the **DMA_SYNCHRONOUS_CALLBACK** flag, the **BuildScatterGatherListEx** routine behaves as follows:

<ul>
<li>
If the requested resources are not immediately available, <b>BuildScatterGatherListEx</b> does not wait for resources, does not build a scatter/gather list, and does not call the <i>AdapterListControl</i> routine. Instead,  <b>BuildScatterGatherListEx</b> fails and returns STATUS_INSUFFICIENT_RESOURCES.

</li>
<li>
The driver is not required to supply an <i>AdapterListControl</i> routine if the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag is set.

</li>
<li>
If the driver supplies an <i>AdapterListControl</i> routine, the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag indicates that this routine is to be called in the context of the calling thread, before <b>BuildScatterGatherListEx</b> returns.

</li>
<li>
If the driver does not supply an <i>AdapterListControl</i> routine, the driver can use the allocated resources and scatter/gather list after <b>BuildScatterGatherListEx</b> returns. In this case, the driver must supply a valid, non-<b>NULL</b> <i>ScatterGatherList</i> pointer. In addition, after the driver-initiated DMA transfer completes, the driver must call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pfree_adapter_object">FreeAdapterObject</a> routine to free the resources that <b>BuildScatterGatherListEx</b> allocated for the adapter object.

</li>
</ul>
<b>BuildScatterGatherListEx</b> is an extended version of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pbuild_scatter_gather_list">BuildScatterGatherList</a> routine. The following list summarizes the features that are available only in the extended version:

|Feature|Description|
|----|----|
|Starting offset|The calling driver can specify a starting offset for a scatter/gather DMA transfer instead of starting the transfer at the first buffer address at the start of the MDL chain.|
|Allocation request cancellation|The driver can call [CancelAdapterChannel](nc-wdm-pcancel_adapter_channel.md) to cancel a pending allocation request when the DMA adapter is queued to wait for DMA resources.|
|Synchronous callback|The driver can set the **DMA_SYNCHRONOUS_CALLBACK** flag to request that the driver-supplied *AdapterListControl* routine be called in the calling thread, before **BuildScatterGatherListEx** returns.|

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_list_control">AdapterListControl</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pallocate_adapter_channel_ex">AllocateAdapterChannelEx</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pcalculate_scatter_gather_list_size">CalculateScatterGatherList</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_dma_operations">DMA_OPERATIONS</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-dma_completion_routine">DmaCompletionRoutine</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pfree_adapter_object">FreeAdapterObject</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pget_scatter_gather_list">GetScatterGatherList</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pget_scatter_gather_list_ex">GetScatterGatherListEx</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pmap_transfer_ex">MapTransferEx</a>
