---
UID: NC:wdm.PGET_DMA_TRANSFER_INFO
title: PGET_DMA_TRANSFER_INFO
author: windows-driver-content
description: The GetDmaTransferInfo routine calculates the allocation requirements for a scatter/gather DMA transfer.
old-location: kernel\getdmatransferinfo.htm
tech.root: kernel
ms.assetid: 27D1FAAE-6DEF-4485-AA29-32CC85A01000
ms.date: 04/30/2018
ms.keywords: GetDmaTransferInfo, GetDmaTransferInfo callback function [Kernel-Mode Driver Architecture], PGET_DMA_TRANSFER_INFO, PGET_DMA_TRANSFER_INFO callback, kernel.getdmatransferinfo, wdm/GetDmaTransferInfo
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
-	GetDmaTransferInfo
product:
- Windows
targetos: Windows
req.typenames: 
---

# PGET_DMA_TRANSFER_INFO callback function


## -description


The <b>GetDmaTransferInfo</b> routine calculates the allocation requirements for a scatter/gather DMA transfer.


## -parameters




### -param DmaAdapter [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544062">DMA_ADAPTER</a> structure. This structure is the adapter object that represents the driver's bus-master DMA device or system DMA channel. The caller obtained this pointer from a previous call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> routine.


### -param Mdl [in]

A pointer to the MDL chain that describes the pages of memory that are to be transferred. For more information, see the Remarks section.


### -param Offset [in]

The starting offset for the scatter/gather DMA transfer. This parameter is a byte offset from the start of the buffer in the first MDL in the MDL chain. If the MDLs in the MDL chain specify a total of N bytes of buffer space, valid values of <i>Offset</i> are in the range 0 to N–1.


### -param Length [in]

The length, in bytes, of the DMA transfer. If the MDL chain specifies a total of N bytes of buffer space, valid values of <i>Length</i> are in the range 1 to N–<i>Offset</i>.


### -param WriteOnly [in]

Indicates whether the transfer is a write-only operation (that is, a transfer to the device from memory). If <i>WriteOnly</i> is TRUE, information returned about the transfer might not be valid for a read transaction. This parameter might indicate that additional cache control operations are required at buffer boundaries to enforce cache coherency.


### -param TransferInfo [in, out]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/hh451001">DMA_TRANSFER_INFO</a> structure. The caller must set the <b>Version</b> member of the structure to DMA_TRANSFER_INFO_VERSION1 before calling <b>GetDmaTransferInfo</b>.


## -returns



<b>GetDmaTransferInfo</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following status codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The routine does not support the specified version of the <b>DMA_TRANSFER_INFO_<i>XXX</i></b> structure.
       

</td>
</tr>
</table>
 




## -remarks



<b>GetDmaTransferInfo</b><i> is not a system routine that can be called directly by name. This routine can be called only by pointer from the address returned in a </i><a href="https://msdn.microsoft.com/library/windows/hardware/ff544071">DMA_OPERATIONS</a><i> structure. </i>Drivers obtain the address of this routine by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> with the <b>Version</b> member of the <i>DeviceDescription</i> parameter set to DEVICE_DESCRIPTION_VERSION3. If <b>IoGetDmaAdapter</b> returns <b>NULL</b>, the routine is not available on your platform.

Use <b>GetDmaTransferInfo</b> to calculate the size of the scatter/gather buffer to allocate for the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406371">BuildScatterGatherListEx</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/hh406521">MapTransferEx</a> routines.

<b>GetDmaTransferInfo</b> replaces the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540716">CalculateScatterGatherList</a> routine and is more convenient to use with <b>BuildScatterGatherListEx</b>.

The <i>Mdl</i>, <i>Offset</i>, and <i>Length</i> parameters together specify a collection of physical memory regions to use as a buffer for a scatter/gather DMA transfer. Each physical memory region is typically a page or part of a page. <b>GetDmaTransferInfo</b> determines the allocation requirements for this transfer. These requirements include the following:

<ul>
<li>
The number of elements in the scatter/gather list. Each element is a <b>SCATTER_GATHER_ELEMENT</b> structure that describes a physically contiguous block of memory.

</li>
<li>
The amount of memory to allocate to hold the specified scatter/gather list. (This memory allocation includes the space required for the scatter/gather list that describes the I/O buffer but not for the I/O buffer itself.)

</li>
<li>
The number of map registers required to translate the physical addresses in the scatter/gather list to logical addresses.

</li>
</ul>
For information about the DMA transfer information that is provided by version 1 of the <b>DMA_TRANSFER_INFO_<i>XXX</i></b> structure, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh451003">DMA_TRANSFER_INFO_V1</a>.

An MDL describes the physical memory pages that underlie a locked-down, contiguous block of virtual memory. Typically, these physical memory pages are non-contiguous. An MDL chain is an ordered collection of MDLs that describes memory that can be used to buffer I/O data. Typically, the virtual memory regions described by the MDLs in the chain are non-contiguous. For more information about MDLs and MDL chains, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565421">Using MDLs</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406371">BuildScatterGatherListEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540716">CalculateScatterGatherList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544071">DMA_OPERATIONS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451001">DMA_TRANSFER_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451003">DMA_TRANSFER_INFO_V1</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406521">MapTransferEx</a>
 

 

