---
UID: NS:wdm._DMA_OPERATIONS
title: "_DMA_OPERATIONS"
author: windows-driver-content
description: The DMA_OPERATIONS structure provides a table of pointers to functions that control the operation of a DMA controller.
old-location: kernel\dma_operations.htm
tech.root: kernel
ms.assetid: b4a5d830-252b-410e-be2c-390371af971c
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: "*PDMA_OPERATIONS, DMA_OPERATIONS, DMA_OPERATIONS structure [Kernel-Mode Driver Architecture], PDMA_OPERATIONS, PDMA_OPERATIONS structure pointer [Kernel-Mode Driver Architecture], _DMA_OPERATIONS, kernel.dma_operations, kstruct_a_ace4fb72-3208-4f4a-9c36-5a1f5791451a.xml, wdm/DMA_OPERATIONS, wdm/PDMA_OPERATIONS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 2000.
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	DMA_OPERATIONS
product:
- Windows
targetos: Windows
req.typenames: "*PDMA_OPERATIONS, DMA_OPERATIONS"
---

# _DMA_OPERATIONS structure


## -description


The <b>DMA_OPERATIONS</b> structure provides a table of pointers to functions that control the operation of a DMA controller.


## -struct-fields


### -field Size

The size, in bytes, of this <b>DMA_OPERATIONS</b> structure.


### -field PutDmaAdapter

A pointer to a system-defined routine to free a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544062">DMA_ADAPTER</a> structure. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff559965">PutDmaAdapter</a>.


### -field AllocateCommonBuffer

A pointer to a system-defined routine to allocate a physically contiguous DMA buffer. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540575">AllocateCommonBuffer</a>.


### -field FreeCommonBuffer

A pointer to a system-defined routine to free a physically contiguous DMA buffer previously allocated by <b>AllocateCommonBuffer</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546511">FreeCommonBuffer</a>.


### -field AllocateAdapterChannel

A pointer to a system-defined routine to allocate a channel for DMA operations. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540573">AllocateAdapterChannel</a>.


### -field FlushAdapterBuffers

A pointer to a system-defined routine to flush data from the system or bus-master adapter's internal cache after a DMA operation. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545917">FlushAdapterBuffers</a>.


### -field FreeAdapterChannel

A pointer to a system-defined routine to free a channel previously allocated for DMA operations by <b>AllocateAdapterChannel</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546507">FreeAdapterChannel</a>.


### -field FreeMapRegisters

A pointer to a system-defined routine to free map registers allocated for DMA operations. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546513">FreeMapRegisters</a>.


### -field MapTransfer

A pointer to a system-defined routine to begin a DMA operation. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554402">MapTransfer</a>.


### -field GetDmaAlignment

A pointer to a system-defined routine to obtain the DMA alignment requirements of the controller. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546530">GetDmaAlignment</a>.


### -field ReadDmaCounter

A pointer to a system-defined routine to obtain the current transfer count for a DMA operation. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560782">ReadDmaCounter</a>.


### -field GetScatterGatherList

A pointer to a system-defined routine that allocates map registers and creates a scatter/gather list for DMA. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546531">GetScatterGatherList</a>.


### -field PutScatterGatherList

A pointer to a system-defined routine that frees map registers and a scatter/gather list after a DMA operation is complete. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff559967">PutScatterGatherList</a>.


### -field CalculateScatterGatherList

A pointer to a system-defined routine that determines the buffer size needed to hold the scatter/gather list that describes an I/O data  buffer. This member is available only in versions 2 and later of <b>DMA_OPERATIONS</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540716">CalculateScatterGatherList</a>.


### -field BuildScatterGatherList

A pointer to a system-defined routine that allocates map registers and creates a scatter/gather list for DMA in a driver-supplied buffer. This member is available only in versions 2 and later of <b>DMA_OPERATIONS</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540689">BuildScatterGatherList</a>.


### -field BuildMdlFromScatterGatherList

A pointer to a system-defined routine that builds an MDL corresponding to a scatter/gather list. This member is available only in versions 2 and later of <b>DMA_OPERATIONS</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540686">BuildMdlFromScatterGatherList</a>.


### -field GetDmaAdapterInfo

A pointer to a system-defined routine that describes the capabilities of a bus-master DMA device or a system DMA controller. <b>GetDmaAdapterInfo</b> is available only in version 3 of <b>DMA_OPERATIONS</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh451121">GetDmaAdapterInfo</a>.


### -field GetDmaTransferInfo

A pointer to a system-defined routine that describes the allocation requirements for a scatter/gather list. This routine replaces <a href="https://msdn.microsoft.com/library/windows/hardware/ff540716">CalculateScatterGatherList</a>. <b>GetDmaTransferInfo</b> is available only in version 3 of <b>DMA_OPERATIONS</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh451125">GetDmaTransferInfo</a>.


### -field InitializeDmaTransferContext

A pointer to a system-defined routine that initializes an opaque DMA transfer context. The operating system stores the internal status of a DMA transfer in this context. <b>InitializeDmaTransferContext</b> is available only in version 3 of <b>DMA_OPERATIONS</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh451191">InitializeDmaTransferContext</a>.


### -field AllocateCommonBufferEx

A pointer to a system-defined routine that allocates memory for a common buffer and maps this memory so that it can accessed both by the processor and by a DMA device. <b>AllocateCommonBufferEx</b> is available only in version 3 of <b>DMA_OPERATIONS</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406344">AllocateCommonBufferEx</a>.


### -field AllocateAdapterChannelEx

A pointer to a system-defined routine that allocates the resources required for a DMA transfer and then calls the driver-supplied <i>AdapterControl</i> routine to initiate the DMA transfer. <b>AllocateAdapterChannelEx</b> is available only in version 3 of <b>DMA_OPERATIONS</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406340">AllocateAdapterChannelEx</a>.


### -field ConfigureAdapterChannel

A pointer to a system-defined routine enables a custom function that is implemented by the DMA controller. <b>ConfigureAdapterChannel</b> is available only in version 3 of <b>DMA_OPERATIONS</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh450939">ConfigureAdapterChannel</a>.


### -field CancelAdapterChannel

A pointer to a system-defined routine that tries to cancel a pending request to allocate a DMA channel. <b>CancelAdapterChannel</b> is available only in version 3 of <b>DMA_OPERATIONS</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406374">CancelAdapterChannel</a>.


### -field MapTransferEx

A pointer to a system-defined routine that sets up map registers to map the physical addresses in a scatter/gather list to the logical addresses that are required to do a DMA transfer. <b>MapTransferEx</b> is available only in version 3 of <b>DMA_OPERATIONS</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406521">MapTransferEx</a>.


### -field GetScatterGatherListEx

A pointer to a system-defined routine that   allocates resources required for a DMA transfer, builds a scatter/gather list, and then calls the driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff540513">AdapterListControl</a> routine to initiate the DMA transfer. <b>GetScatterGatherListEx</b> is available only in version 3 of <b>DMA_OPERATIONS</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh451134">GetScatterGatherListEx</a>. This routine is a wrapper of <b>AllocateAdapterChannelEx</b> and <b>MapTransferEx</b>.


### -field BuildScatterGatherListEx

A pointer to a system-defined routine that   builds a scatter/gather list in a caller-allocated buffer, and then calls the driver-supplied <i>AdapterListControl</i> routine to initiate the DMA transfer. <b>BuildScatterGatherListEx</b> is available only in version 3 of <b>DMA_OPERATIONS</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406371">BuildScatterGatherListEx</a>.


### -field FlushAdapterBuffersEx

A pointer to a system-defined routine that  flushes any data that remains in the system DMA controller's internal cache or in a bus-master adapter's internal cache at the end of a DMA transfer. For a device that uses a system DMA controller, this routine cancels the current DMA transfer on the controller if the transfer is not complete. <b>FlushAdapterBuffersEx</b> is available only in version 3 of <b>DMA_OPERATIONS</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh451102">FlushAdapterBuffersEx</a>.


### -field FreeAdapterObject

A pointer to a system-defined routine that releases the specified adapter object after a driver has completed all DMA operations. <b>FreeAdapterObject</b> is available only in version 3 of <b>DMA_OPERATIONS</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh451107">FreeAdapterObject</a>.


### -field CancelMappedTransfer

A pointer to a system-defined routine that cancels a mapped transfer. <b>CancelMappedTransfer</b> is available only in version 3 of <b>DMA_OPERATIONS</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406377">CancelMappedTransfer</a>.


### -field AllocateDomainCommonBuffer

A pointer to a [*PALLOCATE_DOMAIN_COMMON_BUFFER*](nc-wdm-pallocate_domain_common_buffer.md) callback routine to allocate a domain common buffer. This option is available in Windows 10 and later versions.
 

### -field FlushDmaBuffer

A pointer to a [*PFLUSH_DMA_BUFFER*](nc-wdm-pflush_dma_buffer.md) callback function that flushes any data remaining in the cache. This option is available in Windows 10 and later versions.


### -field JoinDmaDomain
A pointer to a [*PJOIN_DMA_DOMAIN*](nc-wdm-pjoin_dma_domain.md) callback function that joins the specified DMA domain. This option is available in Windows 10 and later versions.


### -field LeaveDmaDomain

A pointer to a [*PLEAVE_DMA_DOMAIN*](nc-wdm-pleave_dma_domain.md) callback function that leaves the specified DMA domain. This option is available in Windows 10 and later versions. 


### -field GetDmaDomain

A pointer to the [*PGET_DMA_DOMAIN*](nc-wdm-pget_dma_domain.md) callback function that gets a handle to the DMA domain. This option is available in Windows 10 and later versions.
 
### -field AllocateCommonBufferWithBounds

A pointer to a [*PALLOCATE_COMMON_BUFFER_WITH_BOUNDS*](nc-wdm-pallocate_common_buffer_with_bounds.md) callback function that allocates the memory for a common buffer and maps it so that it can be accessed by a master device and the CPU. The common buffer can be bound by an optional minimum and maximum logical address. This option is available starting in Windows 10, version 1803.

## -remarks



All members of this structure, with the exception of <b>Size</b>, are pointers to functions that drivers use to perform DMA operations for their devices. Drivers obtain these pointers by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> routine. The version of the <b>DMA_OPERATIONS</b> structure that this routine returns depends on the <b>Version</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543107">DEVICE_DESCRIPTION</a> structure that is passed to <b>IoGetDmaAdapter</b> as an input parameter. If <b>Version</b> is DEVICE_DESCRIPTION_VERSION or DEVICE_DESCRIPTION_VERSION1, version 1 of this structure is returned. If <b>Version</b> is DEVICE_DESCRIPTION_VERSION2, version 2 of this structure is returned. Version 2 of <b>DMA_OPERATIONS</b> is available starting with  Windows XP. If <b>Version</b> is DEVICE_DESCRIPTION_VERSION3, version 3 of this structure is returned. Version 3 of <b>DMA_OPERATIONS</b> is available starting with  Windows 8.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540573">AllocateAdapterChannel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406340">AllocateAdapterChannelEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540575">AllocateCommonBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406344">AllocateCommonBufferEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540686">BuildMdlFromScatterGatherList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540689">BuildScatterGatherList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406371">BuildScatterGatherListEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540716">CalculateScatterGatherList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406374">CancelAdapterChannel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406377">CancelMappedTransfer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450939">ConfigureAdapterChannel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543107">DEVICE_DESCRIPTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545917">FlushAdapterBuffers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451102">FlushAdapterBuffersEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546507">FreeAdapterChannel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451107">FreeAdapterObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546511">FreeCommonBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546513">FreeMapRegisters</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451121">GetDmaAdapterInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546530">GetDmaAlignment</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451125">GetDmaTransferInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546531">GetScatterGatherList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451134">GetScatterGatherListEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451191">InitializeDmaTransferContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554402">MapTransfer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406521">MapTransferEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559965">PutDmaAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559967">PutScatterGatherList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560782">ReadDmaCounter</a>
 

 

