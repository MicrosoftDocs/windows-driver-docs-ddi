---
UID: NS:wdm._DMA_OPERATIONS
title: "_DMA_OPERATIONS"
author: windows-driver-content
description: The DMA_OPERATIONS structure provides a table of pointers to functions that control the operation of a DMA controller.
old-location: kernel\dma_operations.htm
old-project: kernel
ms.assetid: b4a5d830-252b-410e-be2c-390371af971c
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: "*PDMA_OPERATIONS, kernel.dma_operations, _DMA_OPERATIONS, DMA_OPERATIONS structure [Kernel-Mode Driver Architecture], wdm/DMA_OPERATIONS, wdm/PDMA_OPERATIONS, PDMA_OPERATIONS, DMA_OPERATIONS, kstruct_a_ace4fb72-3208-4f4a-9c36-5a1f5791451a.xml, PDMA_OPERATIONS structure pointer [Kernel-Mode Driver Architecture]"
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	DMA_OPERATIONS
product: Windows
targetos: Windows
req.typenames: DMA_OPERATIONS, *PDMA_OPERATIONS
req.product: Windows 10 or later.
---

# _DMA_OPERATIONS structure


## -description


The <b>DMA_OPERATIONS</b> structure provides a table of pointers to functions that control the operation of a DMA controller.


## -syntax


````
typedef struct _DMA_OPERATIONS {
  ULONG                               Size;
  PPUT_DMA_ADAPTER                    PutDmaAdapter;
  PALLOCATE_COMMON_BUFFER             AllocateCommonBuffer;
  PFREE_COMMON_BUFFER                 FreeCommonBuffer;
  PALLOCATE_ADAPTER_CHANNEL           AllocateAdapterChannel;
  PFLUSH_ADAPTER_BUFFERS              FlushAdapterBuffers;
  PFREE_ADAPTER_CHANNEL               FreeAdapterChannel;
  PFREE_MAP_REGISTERS                 FreeMapRegisters;
  PMAP_TRANSFER                       MapTransfer;
  PGET_DMA_ALIGNMENT                  GetDmaAlignment;
  PREAD_DMA_COUNTER                   ReadDmaCounter;
  PGET_SCATTER_GATHER_LIST            GetScatterGatherList;
  PPUT_SCATTER_GATHER_LIST            PutScatterGatherList;
  PCALCULATE_SCATTER_GATHER_LIST_SIZE CalculateScatterGatherList;
  PBUILD_SCATTER_GATHER_LIST          BuildScatterGatherList;
  PBUILD_MDL_FROM_SCATTER_GATHER_LIST BuildMdlFromScatterGatherList;
  PGET_DMA_ADAPTER_INFO               GetDmaAdapterInfo;
  PGET_DMA_TRANSFER_INFO              GetDmaTransferInfo;
  PINITIALIZE_DMA_TRANSFER_CONTEXT    InitializeDmaTransferContext;
  PALLOCATE_COMMON_BUFFER_EX          AllocateCommonBufferEx;
  PALLOCATE_ADAPTER_CHANNEL_EX        AllocateAdapterChannelEx;
  PCONFIGURE_ADAPTER_CHANNEL          ConfigureAdapterChannel;
  PCANCEL_ADAPTER_CHANNEL             CancelAdapterChannel;
  PMAP_TRANSFER_EX                    MapTransferEx;
  PGET_SCATTER_GATHER_LIST_EX         GetScatterGatherListEx;
  PBUILD_SCATTER_GATHER_LIST_EX       BuildScatterGatherListEx;
  PFLUSH_ADAPTER_BUFFERS_EX           FlushAdapterBuffersEx;
  PFREE_ADAPTER_OBJECT                FreeAdapterObject;
  PCANCEL_MAPPED_TRANSFER             CancelMappedTransfer;
} DMA_OPERATIONS, *PDMA_OPERATIONS;
````


## -struct-fields




### -field Size

The size, in bytes, of this <b>DMA_OPERATIONS</b> structure.


### -field PutDmaAdapter

A pointer to a system-defined routine to free a <a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a> structure. For more information, see <a href="..\wdm\nc-wdm-pput_dma_adapter.md">PutDmaAdapter</a>.


### -field AllocateCommonBuffer

A pointer to a system-defined routine to allocate a physically contiguous DMA buffer. For more information, see <a href="..\wdm\nc-wdm-pallocate_common_buffer.md">AllocateCommonBuffer</a>.


### -field FreeCommonBuffer

A pointer to a system-defined routine to free a physically contiguous DMA buffer previously allocated by <b>AllocateCommonBuffer</b>. For more information, see <a href="..\wdm\nc-wdm-pfree_common_buffer.md">FreeCommonBuffer</a>.


### -field AllocateAdapterChannel

A pointer to a system-defined routine to allocate a channel for DMA operations. For more information, see <a href="..\wdm\nc-wdm-pallocate_adapter_channel.md">AllocateAdapterChannel</a>.


### -field FlushAdapterBuffers

A pointer to a system-defined routine to flush data from the system or bus-master adapter's internal cache after a DMA operation. For more information, see <a href="..\wdm\nc-wdm-pflush_adapter_buffers.md">FlushAdapterBuffers</a>.


### -field FreeAdapterChannel

A pointer to a system-defined routine to free a channel previously allocated for DMA operations by <b>AllocateAdapterChannel</b>. For more information, see <a href="..\wdm\nc-wdm-pfree_adapter_channel.md">FreeAdapterChannel</a>.


### -field FreeMapRegisters

A pointer to a system-defined routine to free map registers allocated for DMA operations. For more information, see <a href="..\wdm\nc-wdm-pfree_map_registers.md">FreeMapRegisters</a>.


### -field MapTransfer

A pointer to a system-defined routine to begin a DMA operation. For more information, see <a href="..\wdm\nc-wdm-pmap_transfer.md">MapTransfer</a>.


### -field GetDmaAlignment

A pointer to a system-defined routine to obtain the DMA alignment requirements of the controller. For more information, see <a href="..\wdm\nc-wdm-pget_dma_alignment.md">GetDmaAlignment</a>.


### -field ReadDmaCounter

A pointer to a system-defined routine to obtain the current transfer count for a DMA operation. For more information, see <a href="..\wdm\nc-wdm-pread_dma_counter.md">ReadDmaCounter</a>.


### -field GetScatterGatherList

A pointer to a system-defined routine that allocates map registers and creates a scatter/gather list for DMA. For more information, see <a href="..\wdm\nc-wdm-pget_scatter_gather_list.md">GetScatterGatherList</a>.


### -field PutScatterGatherList

A pointer to a system-defined routine that frees map registers and a scatter/gather list after a DMA operation is complete. For more information, see <a href="..\wdm\nc-wdm-pput_scatter_gather_list.md">PutScatterGatherList</a>.


### -field CalculateScatterGatherList

A pointer to a system-defined routine that determines the buffer size needed to hold the scatter/gather list that describes an I/O data  buffer. This member is available only in versions 2 and later of <b>DMA_OPERATIONS</b>. For more information, see <a href="..\wdm\nc-wdm-pcalculate_scatter_gather_list_size.md">CalculateScatterGatherList</a>.


### -field BuildScatterGatherList

A pointer to a system-defined routine that allocates map registers and creates a scatter/gather list for DMA in a driver-supplied buffer. This member is available only in versions 2 and later of <b>DMA_OPERATIONS</b>. For more information, see <a href="..\wdm\nc-wdm-pbuild_scatter_gather_list.md">BuildScatterGatherList</a>.


### -field BuildMdlFromScatterGatherList

A pointer to a system-defined routine that builds an MDL corresponding to a scatter/gather list. This member is available only in versions 2 and later of <b>DMA_OPERATIONS</b>. For more information, see <a href="..\wdm\nc-wdm-pbuild_mdl_from_scatter_gather_list.md">BuildMdlFromScatterGatherList</a>.


### -field GetDmaAdapterInfo

A pointer to a system-defined routine that describes the capabilities of a bus-master DMA device or a system DMA controller. <b>GetDmaAdapterInfo</b> is available only in version 3 of <b>DMA_OPERATIONS</b>. For more information, see <a href="..\wdm\nc-wdm-pget_dma_adapter_info.md">GetDmaAdapterInfo</a>.


### -field GetDmaTransferInfo

A pointer to a system-defined routine that describes the allocation requirements for a scatter/gather list. This routine replaces <a href="..\wdm\nc-wdm-pcalculate_scatter_gather_list_size.md">CalculateScatterGatherList</a>. <b>GetDmaTransferInfo</b> is available only in version 3 of <b>DMA_OPERATIONS</b>. For more information, see <a href="..\wdm\nc-wdm-pget_dma_transfer_info.md">GetDmaTransferInfo</a>.


### -field InitializeDmaTransferContext

A pointer to a system-defined routine that initializes an opaque DMA transfer context. The operating system stores the internal status of a DMA transfer in this context. <b>InitializeDmaTransferContext</b> is available only in version 3 of <b>DMA_OPERATIONS</b>. For more information, see <a href="..\wdm\nc-wdm-pinitialize_dma_transfer_context.md">InitializeDmaTransferContext</a>.


### -field AllocateCommonBufferEx

A pointer to a system-defined routine that allocates memory for a common buffer and maps this memory so that it can accessed both by the processor and by a DMA device. <b>AllocateCommonBufferEx</b> is available only in version 3 of <b>DMA_OPERATIONS</b>. For more information, see <a href="..\wdm\nc-wdm-pallocate_common_buffer_ex.md">AllocateCommonBufferEx</a>.


### -field AllocateAdapterChannelEx

A pointer to a system-defined routine that allocates the resources required for a DMA transfer and then calls the driver-supplied <i>AdapterControl</i> routine to initiate the DMA transfer. <b>AllocateAdapterChannelEx</b> is available only in version 3 of <b>DMA_OPERATIONS</b>. For more information, see <a href="..\wdm\nc-wdm-pallocate_adapter_channel_ex.md">AllocateAdapterChannelEx</a>.


### -field ConfigureAdapterChannel

A pointer to a system-defined routine enables a custom function that is implemented by the DMA controller. <b>ConfigureAdapterChannel</b> is available only in version 3 of <b>DMA_OPERATIONS</b>. For more information, see <a href="..\wdm\nc-wdm-pconfigure_adapter_channel.md">ConfigureAdapterChannel</a>.


### -field CancelAdapterChannel

A pointer to a system-defined routine that tries to cancel a pending request to allocate a DMA channel. <b>CancelAdapterChannel</b> is available only in version 3 of <b>DMA_OPERATIONS</b>. For more information, see <a href="..\wdm\nc-wdm-pcancel_adapter_channel.md">CancelAdapterChannel</a>.


### -field MapTransferEx

A pointer to a system-defined routine that sets up map registers to map the physical addresses in a scatter/gather list to the logical addresses that are required to do a DMA transfer. <b>MapTransferEx</b> is available only in version 3 of <b>DMA_OPERATIONS</b>. For more information, see <a href="..\wdm\nc-wdm-pmap_transfer_ex.md">MapTransferEx</a>.


### -field GetScatterGatherListEx

A pointer to a system-defined routine that   allocates resources required for a DMA transfer, builds a scatter/gather list, and then calls the driver-supplied <a href="..\wdm\nc-wdm-driver_list_control.md">AdapterListControl</a> routine to initiate the DMA transfer. <b>GetScatterGatherListEx</b> is available only in version 3 of <b>DMA_OPERATIONS</b>. For more information, see <a href="..\wdm\nc-wdm-pget_scatter_gather_list_ex.md">GetScatterGatherListEx</a>. This routine is a wrapper of <b>AllocateAdapterChannelEx</b> and <b>MapTransferEx</b>.


### -field BuildScatterGatherListEx

A pointer to a system-defined routine that   builds a scatter/gather list in a caller-allocated buffer, and then calls the driver-supplied <i>AdapterListControl</i> routine to initiate the DMA transfer. <b>BuildScatterGatherListEx</b> is available only in version 3 of <b>DMA_OPERATIONS</b>. For more information, see <a href="..\wdm\nc-wdm-pbuild_scatter_gather_list_ex.md">BuildScatterGatherListEx</a>.


### -field FlushAdapterBuffersEx

A pointer to a system-defined routine that  flushes any data that remains in the system DMA controller's internal cache or in a bus-master adapter's internal cache at the end of a DMA transfer. For a device that uses a system DMA controller, this routine cancels the current DMA transfer on the controller if the transfer is not complete. <b>FlushAdapterBuffersEx</b> is available only in version 3 of <b>DMA_OPERATIONS</b>. For more information, see <a href="..\wdm\nc-wdm-pflush_adapter_buffers_ex.md">FlushAdapterBuffersEx</a>.


### -field FreeAdapterObject

A pointer to a system-defined routine that releases the specified adapter object after a driver has completed all DMA operations. <b>FreeAdapterObject</b> is available only in version 3 of <b>DMA_OPERATIONS</b>. For more information, see <a href="..\wdm\nc-wdm-pfree_adapter_object.md">FreeAdapterObject</a>.


### -field CancelMappedTransfer

A pointer to a system-defined routine that cancels a mapped transfer. <b>CancelMappedTransfer</b> is available only in version 3 of <b>DMA_OPERATIONS</b>. For more information, see <a href="..\wdm\nc-wdm-pcancel_mapped_transfer.md">CancelMappedTransfer</a>.


### -field AllocateDomainCommonBuffer

 


### -field FlushDmaBuffer

 


### -field JoinDmaDomain

 


### -field LeaveDmaDomain

 


### -field GetDmaDomain

 



## -remarks


All members of this structure, with the exception of <b>Size</b>, are pointers to functions that drivers use to perform DMA operations for their devices. Drivers obtain these pointers by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> routine. The version of the <b>DMA_OPERATIONS</b> structure that this routine returns depends on the <b>Version</b> member of the <a href="..\wdm\ns-wdm-_device_description.md">DEVICE_DESCRIPTION</a> structure that is passed to <b>IoGetDmaAdapter</b> as an input parameter. If <b>Version</b> is DEVICE_DESCRIPTION_VERSION or DEVICE_DESCRIPTION_VERSION1, version 1 of this structure is returned. If <b>Version</b> is DEVICE_DESCRIPTION_VERSION2, version 2 of this structure is returned. Version 2 of <b>DMA_OPERATIONS</b> is available starting with  Windows XP. If <b>Version</b> is DEVICE_DESCRIPTION_VERSION3, version 3 of this structure is returned. Version 3 of <b>DMA_OPERATIONS</b> is available starting with  Windows 8.



## -see-also

<a href="..\wdm\nc-wdm-pmap_transfer.md">MapTransfer</a>

<a href="..\wdm\nc-wdm-pfree_adapter_channel.md">FreeAdapterChannel</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>

<a href="..\wdm\nc-wdm-pput_scatter_gather_list.md">PutScatterGatherList</a>

<a href="..\wdm\nc-wdm-pflush_adapter_buffers.md">FlushAdapterBuffers</a>

<a href="..\wdm\nc-wdm-pbuild_mdl_from_scatter_gather_list.md">BuildMdlFromScatterGatherList</a>

<a href="..\wdm\ns-wdm-_device_description.md">DEVICE_DESCRIPTION</a>

<a href="..\wdm\nc-wdm-pconfigure_adapter_channel.md">ConfigureAdapterChannel</a>

<a href="..\wdm\nc-wdm-pfree_map_registers.md">FreeMapRegisters</a>

<a href="..\wdm\nc-wdm-pallocate_common_buffer_ex.md">AllocateCommonBufferEx</a>

<a href="..\wdm\nc-wdm-pcalculate_scatter_gather_list_size.md">CalculateScatterGatherList</a>

<a href="..\wdm\nc-wdm-pcancel_mapped_transfer.md">CancelMappedTransfer</a>

<a href="..\wdm\nc-wdm-pget_scatter_gather_list_ex.md">GetScatterGatherListEx</a>

<a href="..\wdm\nc-wdm-pflush_adapter_buffers_ex.md">FlushAdapterBuffersEx</a>

<a href="..\wdm\nc-wdm-pput_dma_adapter.md">PutDmaAdapter</a>

<a href="..\wdm\nc-wdm-pcancel_adapter_channel.md">CancelAdapterChannel</a>

<a href="..\wdm\nc-wdm-pget_dma_adapter_info.md">GetDmaAdapterInfo</a>

<a href="..\wdm\nc-wdm-pbuild_scatter_gather_list.md">BuildScatterGatherList</a>

<a href="..\wdm\nc-wdm-pget_dma_alignment.md">GetDmaAlignment</a>

<a href="..\wdm\nc-wdm-pget_dma_transfer_info.md">GetDmaTransferInfo</a>

<a href="..\wdm\nc-wdm-pallocate_adapter_channel.md">AllocateAdapterChannel</a>

<a href="..\wdm\nc-wdm-pmap_transfer_ex.md">MapTransferEx</a>

<a href="..\wdm\nc-wdm-pfree_common_buffer.md">FreeCommonBuffer</a>

<a href="..\wdm\nc-wdm-pfree_adapter_object.md">FreeAdapterObject</a>

<a href="..\wdm\nc-wdm-pbuild_scatter_gather_list_ex.md">BuildScatterGatherListEx</a>

<a href="..\wdm\nc-wdm-pread_dma_counter.md">ReadDmaCounter</a>

<a href="..\wdm\nc-wdm-pinitialize_dma_transfer_context.md">InitializeDmaTransferContext</a>

<a href="..\wdm\nc-wdm-pallocate_common_buffer.md">AllocateCommonBuffer</a>

<a href="..\wdm\nc-wdm-pget_scatter_gather_list.md">GetScatterGatherList</a>

<a href="..\wdm\nc-wdm-pallocate_adapter_channel_ex.md">AllocateAdapterChannelEx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20DMA_OPERATIONS structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

