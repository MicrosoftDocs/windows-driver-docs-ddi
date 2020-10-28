---
UID: NC:wdm.PCREATE_COMMON_BUFFER_FROM_MDL
title: PCREATE_COMMON_BUFFER_FROM_MDL (wdm.h)
description: The CreateCommonBufferFromMdl routine will attempt to create a common buffer from an MDL by testing for device access compatibility and potentially mapping the memory to a contiguous logical range depending on the translation type. Like all other common buffer allocation functions, this function does not provide a forward progress guarantee.
ms.assetid: c8ac4c34-2b7a-4fa1-82d5-ac802498dbd9
ms.date: 08/19/2020
keywords: ["PCREATE_COMMON_BUFFER_FROM_MDL callback function"]
f1_keywords:
 - "wdm/PCREATE_COMMON_BUFFER_FROM_MDL"
 - "PCREATE_COMMON_BUFFER_FROM_MDL"
req.header: wdm.h
req.include-header:
req.target-type: Desktop
req.target-min-winverclnt: Windows 10, version [FUTURE]
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library:
topic_type:
- apiref
api_type:
- UserDefined
api_location:
- wdm.h
api_name:
- PCREATE_COMMON_BUFFER_FROM_MDL
- CreateCommonBufferFromMdl
targetos: Windows
---

# TODO: Copy STUB branch once available

# PCREATE_COMMON_BUFFER_FROM_MDL callback function

## -description

The CreateCommonBufferFromMdl routine will attempt to create a common buffer from an MDL by testing for device access compatibility and potentially mapping the memory to a contiguous logical range depending on the translation type. Like all other common buffer allocation functions, this function does not provide a forward progress guarantee.

## -prototype

```cpp

PCREATE_COMMON_BUFFER_FROM_MDL PcreateCommonBufferFromMdl;

NTSTATUS PcreateCommonBufferFromMdl(
    PDMA_ADAPTER DmaAdapter,
    PMDL Mdl,
    PDMA_COMMON_BUFFER_EXTENDED_CONFIGURATION ExtendedConfigs,
    ULONG ExtendedConfigsCount,
    PPHYSICAL_ADDRESS LogicalAddress
)
{...}
```

## -parameters

### -param DmaAdapter
[in] Provides a pointer to the DMA Adapter that is performing the operation.

### -param Mdl
[in] Provides the MDL that will be mapped to a common buffer.

*For an MDL to be able to back a common buffer, the following conditions must be met:*
- The MDL must have pages that are always resident for the lifetime of the common buffer and that are mapped into the system address space. This can be accomplished by the following approaches:

    - The MDL is created from a buffer in the non-paged pool via [*MmBuildMdlForNonPagedPool*](nf-wdm-mmbuildmdlfornonpagedpool.md).

    - The MDL has been locked via [*MmProbeAndLockPages*](nf-wdm-mmprobeandlockselectedpages.md) and mapped to system space via *<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer#mmgetsystemaddressformdlsafe">MmGetSystemAddressForMdlSafe</a>*.

    - The physical pages for the MDL have been allocated via [*MmAllocatePagesForMdlEx*](nf-wdm-mmallocatepagesformdl.md) and mapped to system space via *<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer#mmgetsystemaddressformdlsafe">MmGetSystemAddressForMdlSafe</a>*.

- The MDL must represent a page-aligned region and be a multiple of PAGE_SIZE.

    - If the SubSection extended configuration is being used, then the portion of the MDL being used must be page-aligned and be a multiple of PAGE_SIZE.

- The MDL must not be a chained MDL.

    - If the SubSection extended configuration is being used, then a chained MDL can be provided, but the portion of the MDL being used must be contained in a single MDL in the chain.

- If DMA Remapping is not being used, the MDL must represent physically contiguous memory and be accessible to the device.

### -param ExtendedConfigs
[in] Provides an optional array of [DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION](ns-wdm-_dma_common_buffer_extended_configuration.md) structures to further configure the creation of the MDL backed common buffer.

*Note: If multiple configurations of the same [DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION_TYPE](ne-wdm-_dma_common_buffer_extended_configuration_type.md) are provided in the array, creation will fail.*

### -param ExtendedConfigsCount
[in] Provides the number of extended configurations in the *ExtendedConfigs* array.

### -param LogicalAddress
[out] On success provides the logical address of the resulting common buffer.

## -returns

**CreateCommonBufferFromMdl** return **STATUS_SUCCESS** if the call is successful. Possible error return values include the following status codes.

<table>

<tr>
<th>Return code</th>
<th>Description</th>
</tr>

<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The caller has provided an incompatible MDL or extended configuration.
</td>
</tr>

<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The caller has provided an extended configuration that is not supported on the current system.
</td>
</tr>

<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The system does not have enough memory to create book-keeping and mapping metadata.
</td>
</tr>

</table>

## -remarks

**CreateCommonBufferFromMdl*** is not a system routine that can be called directly by name. This routine can be called only by pointer from the address returned in a [*DMA_OPERATIONS*](ns-wdm-_dma_operations.md) structure. Drivers obtain the address of this routine by calling [IoGetDmaAdapter](nf-wdm-iogetdmaadapter.md) with the **Version** member of the *DeviceDescription* parameter set to DEVICE_DESCRIPTION_VERSION3. If **IoGetDmaAdapter** returns **NULL**, the routine is not available on your platform.

A common buffer created by **CreateCommonBufferFromMdl** will be removed via [FreeCommonBuffer](nc-wdm-pfree_common_buffer.md). The caller must provide the system virtual address as the virtual address to ensure the common buffer is correctly removed from the Adapter’s common buffer bookkeeping structures. The driver is still responsible for unlocking and freeing the MDL and it’s backing pages.

To create a common buffer where the HAL is responsible for maintaining the backing memory, use [AllocateCommonBufferWithBounds](nc-wdm-pallocate_common_buffer_with_bounds.md).

## -see-also

[DMA_ADAPTER](ns-wdm-_dma_adapter.md)

[DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION](ns-wdm-_dma_common_buffer_extended_configuration.md)

[DMA_COMMON_BUFFER_EXTENDED_CONFIGURATION_TYPE](ne-wdm-_dma_common_buffer_extended_configuration_type.md)

[DMA_OPERATIONS](ns-wdm-_dma_operations.md)

[FreeCommonBuffer](nc-wdm-pfree_common_buffer.md)

[IoGetDmaAdapter](nf-wdm-iogetdmaadapter.md)

[PALLOCATE_COMMON_BUFFER_WITH_BOUNDS](nc-wdm-pallocate_common_buffer_with_bounds.md)

