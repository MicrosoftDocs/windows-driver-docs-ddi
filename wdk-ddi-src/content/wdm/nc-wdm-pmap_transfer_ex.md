---
UID: NC:wdm.PMAP_TRANSFER_EX
title: PMAP_TRANSFER_EX (wdm.h)
description: The MapTransferEx routine sets up map registers to map the physical addresses in a scatter/gather list to the logical addresses that are required to do a DMA transfer.
old-location: kernel\maptransferex.htm
tech.root: kernel
ms.assetid: 9F6A20F0-94B1-4DA2-9FEA-F44D6AFDD16D
ms.date: 04/30/2018
ms.keywords: MapTransferEx, MapTransferEx callback function [Kernel-Mode Driver Architecture], PMAP_TRANSFER_EX, PMAP_TRANSFER_EX callback, kernel.maptransferex, wdm/MapTransferEx
ms.topic: callback
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdm.h
api_name:
-	MapTransferEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# PMAP_TRANSFER_EX callback function


## -description


The <b>MapTransferEx</b> routine sets up map registers to map the physical addresses in a scatter/gather list to the logical addresses that are required to do a DMA transfer.


## -parameters




### -param DmaAdapter [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544062">DMA_ADAPTER</a> structure. This structure is the adapter object that represents the driver's bus-master DMA device or system DMA channel. The caller obtained this pointer from a previous call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> routine.


### -param Mdl [in]

A pointer to an MDL chain that describes the physical page layout for a collection of locked-down buffers in virtual memory. The scatter/gather list for the DMA transfer will use the region of this memory that is specified by the <i>Offset</i> and <i>Length</i> parameters. For more information about MDL chains, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565421">Using MDLs</a>.


### -param MapRegisterBase [in]

A handle to the map registers that are allocated for the adapter object. The caller previously obtained this handle from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406340">AllocateAdapterChannelEx</a> routine.


### -param Offset [in]

A byte offset from the start of the memory that is described by the MDL chain. This offset specifies the start of the I/O data buffer that is used for the DMA transfer. If a scatter/gather list is supplied to the caller, this offset determines the starting address of the first buffer fragment in the list. If the MDLs in the MDL chain describe a total of N bytes of memory, valid values of <i>Offset</i> are in the range 0 to N–1. For more information, see Remarks.


### -param DeviceOffset [in]

The byte offset of the target device's data register or FIFO from the device's base address.  This parameter applies to devices that have multiple FIFOs that can be accessed by a system DMA controller. This parameter is used only for system DMA transfers. For bus-master transfers, set this parameter to zero.


### -param Length [in, out]

A pointer to a variable that contains the length, in bytes, of the I/O data buffer that is used for the DMA transfer. On entry, this variable contains the length requested by the calling driver. Before returning, the routine writes the actual length of the mapped buffer to this variable. The value of *<i>Length</i> on return from <b>MapTransferEx</b> indicates how many bytes were mapped. If the number of map registers and the scatter/gather buffer size are sufficient to map the entire length requested by the caller, the input and output values of *<i>Length</i> are identical. If the MDLs in the MDL chain describe a total of N bytes of memory, valid values of *<i>Length</i> are in the range 0 to N–<i>Offset</i>.


### -param WriteToDevice [in]

The direction of the DMA transfer. Set this parameter to <b>TRUE</b> for a write operation, which transfers data to the device from memory. Set this parameter to <b>FALSE</b> for a read operation, which transfers data from the device to memory.


### -param ScatterGatherBuffer [out, optional]

A pointer to a caller-allocated buffer into which the routine writes the scatter/gather list for the DMA transfer. This list begins with a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563664">SCATTER_GATHER_LIST</a> structure, which is immediately followed by a <b>SCATTER_GATHER_ELEMENT</b> array. For a driver that uses a bus-master DMA device, <i>ScatterGatherBuffer</i> is a required parameter. For a driver that uses a system DMA controller, the <i>ScatterGatherBuffer</i> parameter is optional and can be <b>NULL</b>. For more information, see Remarks.


### -param ScatterGatherBufferLength [in]

The size, in bytes, of the buffer that the <i>ScatterGatherBuffer</i> parameter points to. The allocated buffer size must be large enough to contain the scatter/gather list, plus internal data that the operating system stores in this buffer. To determine the required buffer size, call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451125">GetDmaTransferInfo</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff540716">CalculateScatterGatherList</a> routine. If <i>ScatterGatherBuffer</i> is <b>NULL</b>, set <i>ScatterGatherBufferLength</i> to zero.


### -param DmaCompletionRoutine [in, optional]

A pointer to a caller-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/hh450991">DmaCompletionRoutine</a> routine to be called when the DMA transfer completes. This routine is called if the target device uses a system DMA controller that generates a DMA-completion interrupt. The <i>DmaCompletionRoutine</i> routine is called at DISPATCH_LEVEL after the DMA transfer completes. For a system DMA adapter, this parameter is optional and can be <b>NULL</b>. For a bus-master adapter, set this parameter to <b>NULL</b>.


### -param CompletionContext [in, optional]

The driver-determined context for the <i>DmaCompletionRoutine</i> routine. This context is supplied as the  <i>CompletionContext</i> parameter to the <i>DmaCompletionRoutine</i> routine. If the <i>DmaCompletionRoutine</i> parameter is <b>NULL</b>, set <i>CompletionContext</i> to <b>NULL</b>.


## -returns



<b>MapTransferEx</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following status codes.

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
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_CANCELLED</b></dt>
</dl>
</td>
<td width="60%">
This transfer was canceled.

</td>
</tr>
</table>
 




## -remarks



<b>MapTransferEx</b><i> is not a system routine that can be called directly by name. This routine can be called only by pointer from the address returned in a </i><a href="https://msdn.microsoft.com/library/windows/hardware/ff544071">DMA_OPERATIONS</a><i> structure. </i>Drivers obtain the address of this routine by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> with the <b>Version</b> member of the <i>DeviceDescription</i> parameter set to DEVICE_DESCRIPTION_VERSION3. If <b>IoGetDmaAdapter</b> returns <b>NULL</b>, the routine is not available on your platform.

For a transfer that uses a system DMA controller, the caller can, as an option, supply a <a href="https://msdn.microsoft.com/library/windows/hardware/hh450991">DmaCompletionRoutine</a> callback routine that is called when the transfer finishes. The operating system schedules this callback in response to the DMA completion interrupt from the system DMA controller.

The number of map registers that can be set up by <b>MapTransferEx</b> cannot exceed the maximum that the driver obtained from <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>.

The <i>Mdl</i>, <i>Offset</i>, and <i>Length</i> parameters describe the I/O data buffer for the requested DMA transfer. The number of allocated map registers might not be sufficient to map all of the memory in this buffer, or the scatter/gather buffer pointed to by <i>ScatterGatherBuffer</i> might not be large enough to describe the entire buffer. <b>MapTransferEx</b> writes an output value to *<i>Length</i> to tell the driver how much of the buffer memory for the requested DMA transfer was mapped by the routine. The routine writes a scatter/gather list to the buffer pointed to by <i>ScatterGatherBuffer</i>. This list describes the buffer fragments that were successfully mapped by the routine.

If a call to <b>MapTransferEx</b> is successful, <b>MapTransferEx</b> writes the *<i>Length</i> output value before it returns. If the caller specifies a <i>DmaCompletionRoutine</i>, the updated *<i>Length</i> output value is always written before the <i>DmaCompletionRoutine</i> runs. For more information, see <a href="https://msdn.microsoft.com/79D3DDB2-B134-43B2-A6CC-94035C793047">Multiple calls to MapTransferEx</a>.

The <i>Offset</i> parameter specifies the starting offset in the MDL chain that describes the memory in the I/O data buffer. For example, assume that the MDL chain contains two MDLs, MDL₁ and MDL₂, and that MDL₁ describes N₁ bytes of memory, and MDL₂ describes N₂ bytes. If <i>Offset</i> = N, where N₁ &lt; N &lt; N₁ + N₂, the buffer contains none of the memory described by MDL₁, and starts at an offset of N - N₁ bytes in the memory described by MDL₂.

If the transfer uses a system DMA controller, the caller can set <i>ScatterGatherBuffer</i> = NULL, in which case <b>MapTransferEx</b> uses an internally allocated, default buffer to hold the scatter/gather list. The default buffer is guaranteed to be large enough to contain a scatter/gather list of at least one element. If the default buffer is used for a scatter/gather transfer of many elements, many calls to <b>MapTransferEx</b> might be required complete the transfer. If the DMA controller hardware supports scatter/gather transfers, the use of the default buffer might degrade performance.

If <i>ScatterGatherBuffer</i> is non-NULL and <i>ScatterGatherBufferSize</i> specifies a size that is too small to contain a scatter/gather list of at least one element, <b>MapTransferEx</b> fails and returns STATUS_INVALID_PARAMETER.

<b>MapTransferEx</b> is an extended version of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554402">MapTransfer</a> routine. The extended version has these advantages:

<ul>
<li>
<b>MapTransferEx</b> can process all of the buffer fragments in an MDL chain in one call, but <b>MapTransfer</b> can process only one physically contiguous buffer fragment per call.

</li>
<li>
<b>MapTransferEx</b> can generate an entire scatter/gather list in one call, but <b>MapTransfer</b> can generate only one scatter/gather list element per call.

</li>
<li>
<b>MapTransferEx</b> can map all of the buffer fragments in a scatter/gather list in one call, but <b>MapTransfer</b> can map only one physically contiguous buffer fragment per call.

</li>
<li>
<b>MapTransferEx</b> requires only the starting offset for the entire scatter/gather list, but <b>MapTransfer</b> requires a starting virtual address for each physically contiguous buffer fragment.

</li>
<li>
A <b>MapTransferEx</b> call can map a buffer that extends through one or more MDLs, but a <b>MapTransfer</b> call can map only one physically contiguous buffer fragment in the memory that is described by an MDL.

</li>
<li>
For a system DMA transfer, <b>MapTransferEx</b> enables the caller to supply a <i>DmaCompletionRoutine</i> callback routine to receive notification after the transfer completes, but <b>MapTransfer</b> does not provide a way to notify the caller when a DMA transfer completes.

</li>
</ul>
Each successful call to <b>MapTransferEx</b> must be followed by a corresponding call to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451102">FlushAdapterBuffersEx</a> routine. The <b>FlushAdapterBuffersEx</b> call that follows a <b>MapTransferEx</b> call must occur before the next <b>MapTransferEx</b> call occurs. The <b>FlushAdapterBuffersEx</b> call is required even if a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406377">CancelMappedTransfer</a> routine succeeds in canceling the mapped transfer requested by the preceding <b>MapTransferEx</b> call.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh825928">Using the MapTransferEx Routine</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406340">AllocateAdapterChannelEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540716">CalculateScatterGatherList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406377">CancelMappedTransfer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544062">DMA_ADAPTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544071">DMA_OPERATIONS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450991">DmaCompletionRoutine</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451102">FlushAdapterBuffersEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451125">GetDmaTransferInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563664">SCATTER_GATHER_LIST</a>
 

 

