---
UID: NC:wdm.PGET_DMA_TRANSFER_INFO
title: PGET_DMA_TRANSFER_INFO
author: windows-driver-content
description: The GetDmaTransferInfo routine calculates the allocation requirements for a scatter/gather DMA transfer.
old-location: kernel\getdmatransferinfo.htm
old-project: kernel
ms.assetid: 27D1FAAE-6DEF-4485-AA29-32CC85A01000
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _WDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GetDmaTransferInfo
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# PGET_DMA_TRANSFER_INFO callback



## -description
The <b>GetDmaTransferInfo</b> routine calculates the allocation requirements for a scatter/gather DMA transfer.



## -prototype

````
PGET_DMA_TRANSFER_INFO GetDmaTransferInfo;

NTSTATUS GetDmaTransferInfo(
  _In_    PDMA_ADAPTER       DmaAdapter,
  _In_    PMDL               Mdl,
  _In_    ULONGLONG          Offset,
  _In_    ULONG              Length,
  _In_    BOOLEAN            WriteOnly,
  _Inout_ PDMA_TRANSFER_INFO TransferInfo
)
{ ... }
````


## -parameters

### -param DmaAdapter [in]

A pointer to a <a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a> structure. This structure is the adapter object that represents the driver's bus-master DMA device or system DMA channel. The caller obtained this pointer from a previous call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> routine.


### -param Mdl [in]

A pointer to the MDL chain that describes the pages of memory that are to be transferred. For more information, see the Remarks section.


### -param Offset [in]

The starting offset for the scatter/gather DMA transfer. This parameter is a byte offset from the start of the buffer in the first MDL in the MDL chain. If the MDLs in the MDL chain specify a total of N bytes of buffer space, valid values of <i>Offset</i> are in the range 0 to N–1.


### -param Length [in]

The length, in bytes, of the DMA transfer. If the MDL chain specifies a total of N bytes of buffer space, valid values of <i>Length</i> are in the range 1 to N–<i>Offset</i>.


### -param WriteOnly [in]

Indicates whether the transfer is a write-only operation (that is, a transfer to the device from memory). If <i>WriteOnly</i> is TRUE, information returned about the transfer might not be valid for a read transaction. This parameter might indicate that additional cache control operations are required at buffer boundaries to enforce cache coherency.


### -param TransferInfo [in, out]

A pointer to a caller-allocated <a href="..\wdm\ns-wdm-_dma_transfer_info.md">DMA_TRANSFER_INFO</a> structure. The caller must set the <b>Version</b> member of the structure to DMA_TRANSFER_INFO_VERSION1 before calling <b>GetDmaTransferInfo</b>.


## -returns
<b>GetDmaTransferInfo</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following status codes.
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>The routine does not support the specified version of the <b>DMA_TRANSFER_INFO_<i>XXX</i></b> structure.
       

 


## -remarks
<b>GetDmaTransferInfo</b><i> is not a system routine that can be called directly by name. This routine can be called only by pointer from the address returned in a </i><a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a><i> structure. </i>Drivers obtain the address of this routine by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> with the <b>Version</b> member of the <i>DeviceDescription</i> parameter set to DEVICE_DESCRIPTION_VERSION3. If <b>IoGetDmaAdapter</b> returns <b>NULL</b>, the routine is not available on your platform.

Use <b>GetDmaTransferInfo</b> to calculate the size of the scatter/gather buffer to allocate for the <a href="..\wdm\nc-wdm-pbuild_scatter_gather_list_ex.md">BuildScatterGatherListEx</a> and <a href="..\wdm\nc-wdm-pmap_transfer_ex.md">MapTransferEx</a> routines.

<b>GetDmaTransferInfo</b> replaces the <a href="..\wdm\nc-wdm-pcalculate_scatter_gather_list_size.md">CalculateScatterGatherList</a> routine and is more convenient to use with <b>BuildScatterGatherListEx</b>.

The <i>Mdl</i>, <i>Offset</i>, and <i>Length</i> parameters together specify a collection of physical memory regions to use as a buffer for a scatter/gather DMA transfer. Each physical memory region is typically a page or part of a page. <b>GetDmaTransferInfo</b> determines the allocation requirements for this transfer. These requirements include the following:

The number of elements in the scatter/gather list. Each element is a <b>SCATTER_GATHER_ELEMENT</b> structure that describes a physically contiguous block of memory.

The amount of memory to allocate to hold the specified scatter/gather list. (This memory allocation includes the space required for the scatter/gather list that describes the I/O buffer but not for the I/O buffer itself.)

The number of map registers required to translate the physical addresses in the scatter/gather list to logical addresses.

For information about the DMA transfer information that is provided by version 1 of the <b>DMA_TRANSFER_INFO_<i>XXX</i></b> structure, see <a href="..\wdm\ns-wdm-_dma_transfer_info_v1.md">DMA_TRANSFER_INFO_V1</a>.

An MDL describes the physical memory pages that underlie a locked-down, contiguous block of virtual memory. Typically, these physical memory pages are non-contiguous. An MDL chain is an ordered collection of MDLs that describes memory that can be used to buffer I/O data. Typically, the virtual memory regions described by the MDLs in the chain are non-contiguous. For more information about MDLs and MDL chains, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565421">Using MDLs</a>.


## -see-also
<dl>
<dt>
<a href="..\wdm\nc-wdm-pbuild_scatter_gather_list_ex.md">BuildScatterGatherListEx</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-pcalculate_scatter_gather_list_size.md">CalculateScatterGatherList</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_dma_transfer_info.md">DMA_TRANSFER_INFO</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_dma_transfer_info_v1.md">DMA_TRANSFER_INFO_V1</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-pmap_transfer_ex.md">MapTransferEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PGET_DMA_TRANSFER_INFO callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

