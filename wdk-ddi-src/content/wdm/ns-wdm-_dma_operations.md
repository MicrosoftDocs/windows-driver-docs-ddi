---
UID: NS:wdm._DMA_OPERATIONS
title: DMA_OPERATIONS (wdm.h)
description: The DMA_OPERATIONS structure provides a table of pointers to functions that control the operation of a DMA controller.
tech.root: kernel
ms.date: 10/07/2025
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Windows 2000
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
targetos: Windows
req.typenames: "*PDMA_OPERATIONS, DMA_OPERATIONS"
f1_keywords:
 - _DMA_OPERATIONS
 - wdm/_DMA_OPERATIONS
 - PDMA_OPERATIONS
 - wdm/PDMA_OPERATIONS
 - DMA_OPERATIONS
 - wdm/DMA_OPERATIONS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - _DMA_OPERATIONS
 - PDMA_OPERATIONS
 - DMA_OPERATIONS
---

## -description

The **DMA_OPERATIONS** structure provides a table of pointers to functions that control the operation of a DMA controller.

## -struct-fields

### -field Size

The size, in bytes, of this **DMA_OPERATIONS** structure.

### -field PutDmaAdapter

A pointer to a system-defined routine to free a [**DMA_ADAPTER**](ns-wdm-_dma_adapter.md) structure. For more information, see [**PutDmaAdapter**](nc-wdm-pput_dma_adapter.md).

### -field AllocateCommonBuffer

A pointer to a system-defined routine to allocate a physically contiguous DMA buffer. For more information, see [**AllocateCommonBuffer**](nc-wdm-pallocate_common_buffer.md).

### -field FreeCommonBuffer

A pointer to a system-defined routine to free a physically contiguous DMA buffer previously allocated by **AllocateCommonBuffer**. For more information, see [**FreeCommonBuffer**](nc-wdm-pfree_common_buffer.md).

### -field AllocateAdapterChannel

A pointer to a system-defined routine to allocate a channel for DMA operations. For more information, see [**AllocateAdapterChannel**](nc-wdm-pallocate_adapter_channel.md).

### -field FlushAdapterBuffers

A pointer to a system-defined routine to flush data from the system or bus-master adapter's internal cache after a DMA operation. For more information, see [**FlushAdapterBuffers**](nc-wdm-pflush_adapter_buffers.md).

### -field FreeAdapterChannel

A pointer to a system-defined routine to free a channel previously allocated for DMA operations by **AllocateAdapterChannel**. For more information, see [**FreeAdapterChannel**](nc-wdm-pfree_adapter_channel.md).

### -field FreeMapRegisters

A pointer to a system-defined routine to free map registers allocated for DMA operations. For more information, see [**FreeMapRegisters**](nc-wdm-pfree_map_registers.md).

### -field MapTransfer

A pointer to a system-defined routine to begin a DMA operation. For more information, see [**MapTransfer**](nc-wdm-pmap_transfer.md).

### -field GetDmaAlignment

A pointer to a system-defined routine to obtain the DMA alignment requirements of the controller. For more information, see [**GetDmaAlignment**](nc-wdm-pget_dma_alignment.md).

### -field ReadDmaCounter

A pointer to a system-defined routine to obtain the current transfer count for a DMA operation. For more information, see [**ReadDmaCounter**](nc-wdm-pread_dma_counter.md).

### -field GetScatterGatherList

A pointer to a system-defined routine that allocates map registers and creates a scatter/gather list for DMA. For more information, see [**GetScatterGatherList**](nc-wdm-pget_scatter_gather_list.md).

### -field PutScatterGatherList

A pointer to a system-defined routine that frees map registers and a scatter/gather list after a DMA operation is complete. For more information, see [**PutScatterGatherList**](nc-wdm-pput_scatter_gather_list.md).

### -field CalculateScatterGatherList

A pointer to a system-defined routine that determines the buffer size needed to hold the scatter/gather list that describes an I/O data  buffer. This member is available only in versions 2 and later of **DMA_OPERATIONS**. For more information, see [**CalculateScatterGatherList**](nc-wdm-pcalculate_scatter_gather_list_size.md).

### -field BuildScatterGatherList

A pointer to a system-defined routine that allocates map registers and creates a scatter/gather list for DMA in a driver-supplied buffer. This member is available only in versions 2 and later of **DMA_OPERATIONS**. For more information, see [**BuildScatterGatherList**](nc-wdm-pbuild_scatter_gather_list.md).

### -field BuildMdlFromScatterGatherList

A pointer to a system-defined routine that builds an MDL corresponding to a scatter/gather list. This member is available only in versions 2 and later of **DMA_OPERATIONS**. For more information, see [**BuildMdlFromScatterGatherList**](nc-wdm-pbuild_mdl_from_scatter_gather_list.md).

### -field GetDmaAdapterInfo

A pointer to a system-defined routine that describes the capabilities of a bus-master DMA device or a system DMA controller. **GetDmaAdapterInfo** is available only in version 3 of **DMA_OPERATIONS**. For more information, see [**GetDmaAdapterInfo**](nc-wdm-pget_dma_adapter_info.md).

### -field GetDmaTransferInfo

A pointer to a system-defined routine that describes the allocation requirements for a scatter/gather list. This routine replaces [**CalculateScatterGatherList**](nc-wdm-pcalculate_scatter_gather_list_size.md). **GetDmaTransferInfo** is available only in version 3 of **DMA_OPERATIONS**. For more information, see [**GetDmaTransferInfo**](nc-wdm-pget_dma_transfer_info.md).

### -field InitializeDmaTransferContext

A pointer to a system-defined routine that initializes an opaque DMA transfer context. The operating system stores the internal status of a DMA transfer in this context. **InitializeDmaTransferContext** is available only in version 3 of **DMA_OPERATIONS**. For more information, see [**InitializeDmaTransferContext**](nc-wdm-pinitialize_dma_transfer_context.md).

### -field AllocateCommonBufferEx

A pointer to a system-defined routine that allocates memory for a common buffer and maps this memory so that it can accessed both by the processor and by a DMA device. **AllocateCommonBufferEx** is available only in version 3 of **DMA_OPERATIONS**. For more information, see [**AllocateCommonBufferEx**](nc-wdm-pallocate_common_buffer_ex.md).

### -field AllocateAdapterChannelEx

A pointer to a system-defined routine that allocates the resources required for a DMA transfer and then calls the driver-supplied **AdapterControl** routine to initiate the DMA transfer. **AllocateAdapterChannelEx** is available only in version 3 of **DMA_OPERATIONS**. For more information, see [**AllocateAdapterChannelEx**](nc-wdm-pallocate_adapter_channel_ex.md).

### -field ConfigureAdapterChannel

A pointer to a system-defined routine enables a custom function that is implemented by the DMA controller. **ConfigureAdapterChannel** is available only in version 3 of **DMA_OPERATIONS**. For more information, see [**ConfigureAdapterChannel**](nc-wdm-pconfigure_adapter_channel.md).

### -field CancelAdapterChannel

A pointer to a system-defined routine that tries to cancel a pending request to allocate a DMA channel. **CancelAdapterChannel** is available only in version 3 of **DMA_OPERATIONS**. For more information, see [**CancelAdapterChannel**](nc-wdm-pcancel_adapter_channel.md).

### -field MapTransferEx

A pointer to a system-defined routine that sets up map registers to map the physical addresses in a scatter/gather list to the logical addresses that are required to do a DMA transfer. **MapTransferEx** is available only in version 3 of **DMA_OPERATIONS**. For more information, see [**MapTransferEx**](nc-wdm-pmap_transfer_ex.md).

### -field GetScatterGatherListEx

A pointer to a system-defined routine that   allocates resources required for a DMA transfer, builds a scatter/gather list, and then calls the driver-supplied [**AdapterListControl**](nc-wdm-driver_list_control.md) routine to initiate the DMA transfer. **GetScatterGatherListEx** is available only in version 3 of **DMA_OPERATIONS**. For more information, see [**GetScatterGatherListEx**](nc-wdm-pget_scatter_gather_list_ex.md). This routine is a wrapper of **AllocateAdapterChannelEx** and **MapTransferEx**.

### -field BuildScatterGatherListEx

A pointer to a system-defined routine that   builds a scatter/gather list in a caller-allocated buffer, and then calls the driver-supplied **AdapterListControl** routine to initiate the DMA transfer. **BuildScatterGatherListEx** is available only in version 3 of **DMA_OPERATIONS**. For more information, see [**BuildScatterGatherListEx**](nc-wdm-pbuild_scatter_gather_list_ex.md).

### -field FlushAdapterBuffersEx

A pointer to a system-defined routine that  flushes any data that remains in the system DMA controller's internal cache or in a bus-master adapter's internal cache at the end of a DMA transfer. For a device that uses a system DMA controller, this routine cancels the current DMA transfer on the controller if the transfer is not complete. **FlushAdapterBuffersEx** is available only in version 3 of **DMA_OPERATIONS**. For more information, see [**FlushAdapterBuffersEx**](nc-wdm-pflush_adapter_buffers_ex.md).

### -field FreeAdapterObject

A pointer to a system-defined routine that releases the specified adapter object after a driver has completed all DMA operations. **FreeAdapterObject** is available only in version 3 of **DMA_OPERATIONS**. For more information, see [**FreeAdapterObject**](nc-wdm-pfree_adapter_object.md).

### -field CancelMappedTransfer

A pointer to a system-defined routine that cancels a mapped transfer. **CancelMappedTransfer** is available only in version 3 of **DMA_OPERATIONS**. For more information, see [**CancelMappedTransfer**](nc-wdm-pcancel_mapped_transfer.md).

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

### -field AllocateCommonBufferVector

A pointer to a [*PALLOCATE_COMMON_BUFFER_VECTOR*](nc-wdm-pallocate_common_buffer_vector.md) callback function that allocates multiple common buffers as a vector, allowing for efficient batch allocation of DMA-accessible memory regions.

### -field GetCommonBufferFromVectorByIndex

A pointer to a [*PGET_COMMON_BUFFER_FROM_VECTOR_BY_INDEX*](nc-wdm-pget_common_buffer_from_vector_by_index.md) callback function that retrieves the virtual and logical addresses of a specific common buffer from a previously allocated vector by its index.

### -field FreeCommonBufferFromVector

A pointer to a [*PFREE_COMMON_BUFFER_FROM_VECTOR*](nc-wdm-pfree_common_buffer_from_vector.md) callback function that frees a specific common buffer from a vector by its index, allowing for individual buffer deallocation within the vector.

### -field FreeCommonBufferVector

A pointer to a [*PFREE_COMMON_BUFFER_VECTOR*](nc-wdm-pfree_common_buffer_vector.md) callback function that frees an entire common buffer vector and all its associated buffers that were previously allocated by **AllocateCommonBufferVector**.

### -field CreateCommonBufferFromMdl

A pointer to a [*PCREATE_COMMON_BUFFER_FROM_MDL*](nc-wdm-pcreate-common-buffer-from-mdl.md) callback function that will create a DMA common buffer from an MDL and maps the backing memory so that it can be accessed by a bus-mastering device and the CPU. This optional callback is available starting in Windows Server 2022.

## -remarks

All members of this structure, with the exception of **Size**, are pointers to functions that drivers use to perform DMA operations for their devices. Drivers obtain these pointers by calling the [**IoGetDmaAdapter**](nf-wdm-iogetdmaadapter.md) routine. The version of the **DMA_OPERATIONS** structure that this routine returns depends on the **Version** member of the [**DEVICE_DESCRIPTION**](wdm/ns-wdm-_device_description.md) structure that is passed to **IoGetDmaAdapter** as an input parameter. If **Version** is DEVICE_DESCRIPTION_VERSION or DEVICE_DESCRIPTION_VERSION1, version 1 of this structure is returned. If **Version** is DEVICE_DESCRIPTION_VERSION2, version 2 of this structure is returned. Version 2 of **DMA_OPERATIONS** is available starting with  Windows XP. If **Version** is DEVICE_DESCRIPTION_VERSION3, version 3 of this structure is returned. Version 3 of **DMA_OPERATIONS** is available starting with  Windows 8.

## -see-also

[**AllocateAdapterChannel**](nc-wdm-pallocate_adapter_channel.md)

[**AllocateAdapterChannelEx**](nc-wdm-pallocate_adapter_channel_ex.md)

[**AllocateCommonBuffer**](nc-wdm-pallocate_common_buffer.md)

[**AllocateCommonBufferEx**](nc-wdm-pallocate_common_buffer_ex.md)

[**BuildMdlFromScatterGatherList**](nc-wdm-pbuild_mdl_from_scatter_gather_list.md)

[**BuildScatterGatherList**](nc-wdm-pbuild_scatter_gather_list.md)

[**BuildScatterGatherListEx**](nc-wdm-pbuild_scatter_gather_list_ex.md)

[**CalculateScatterGatherList**](nc-wdm-pcalculate_scatter_gather_list_size.md)

[**CancelAdapterChannel**](nc-wdm-pcancel_adapter_channel.md)

[**CancelMappedTransfer**](nc-wdm-pcancel_mapped_transfer.md)

[**ConfigureAdapterChannel**](nc-wdm-pconfigure_adapter_channel.md)

[**DEVICE_DESCRIPTION**](nc-wdm-_device_description.md)

[**FlushAdapterBuffers**](nc-wdm-pflush_adapter_buffers.md)

[**FlushAdapterBuffersEx**](nc-wdm-pflush_adapter_buffers_ex.md)

[**FreeAdapterChannel**](nc-wdm-pfree_adapter_channel.md)

[**FreeAdapterObject**](nc-wdm-pfree_adapter_object.md)

[**FreeCommonBuffer**](nc-wdm-pfree_common_buffer.md)

[**FreeMapRegisters**](nc-wdm-pfree_map_registers.md)

[**GetDmaAdapterInfo**](nc-wdm-pget_dma_adapter_info.md)

[**GetDmaAlignment**](nc-wdm-pget_dma_alignment.md)

[**GetDmaTransferInfo**](nc-wdm-pget_dma_transfer_info.md)

[**GetScatterGatherList**](nc-wdm-pget_scatter_gather_list.md)

[**GetScatterGatherListEx**](nc-wdm-pget_scatter_gather_list_ex.md)

[**InitializeDmaTransferContext**](nc-wdm-pinitialize_dma_transfer_context.md)

[**IoGetDmaAdapter**](nf-wdm-iogetdmaadapter.md)

[**MapTransfer**](nc-wdm-pmap_transfer.md)

[**MapTransferEx**](nc-wdm-pmap_transfer_ex.md)

[**PutDmaAdapter**](nc-wdm-pput_dma_adapter.md)

[**PutScatterGatherList**](nc-wdm-pput_scatter_gather_list.md)

[**ReadDmaCounter**](nc-wdm-pread_dma_counter.md)
