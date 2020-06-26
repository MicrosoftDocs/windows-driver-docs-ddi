---
UID: NC:wdm.PALLOCATE_DOMAIN_COMMON_BUFFER
title: PALLOCATE_DOMAIN_COMMON_BUFFER (wdm.h)
description: 
ms.assetid: 29fca9d8-ddc6-40b5-92c0-079441f965b3
ms.date: 10/19/2018
keywords: ["PALLOCATE_DOMAIN_COMMON_BUFFER callback function"]
f1_keywords:
 - "wdm/PALLOCATE_DOMAIN_COMMON_BUFFER"
req.header: wdm.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10
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
- PALLOCATE_DOMAIN_COMMON_BUFFER
- AllocateDomainCommonBuffer
product:
- Windows
targetos: Windows
---

# PALLOCATE_DOMAIN_COMMON_BUFFER callback function

## -description

This callback function allocates the memory for a domain common buffer.

## -prototype

```cpp
//Declaration

PALLOCATE_DOMAIN_COMMON_BUFFER PallocateDomainCommonBuffer; 

// Definition

NTSTATUS PallocateDomainCommonBuffer 
(
	PDMA_ADAPTER DmaAdapter
	HANDLE DomainHandle
	PPHYSICAL_ADDRESS MaximumAddress
	ULONG Length
	ULONG Flags
	MEMORY_CACHING_TYPE *CacheType
	NODE_REQUIREMENT PreferredNode
	PPHYSICAL_ADDRESS LogicalAddress
	PVOID *VirtualAddress
)
{...}


```

## -parameters

### -param DmaAdapter
[in] A pointer to a DMA_ADAPTER structure. This structure is the adapter object that represents the driver's bus-master DMA device or system DMA channel. The caller obtained this pointer from a previous call to the [**IoGetDmaAdapter**](nf-wdm-iogetdmaadapter.md) routine.
 
### -param DomainHandle
[in] The handle to the DMA domain that the caller obtained from a previous call to [*PGET_DMA_DOMAIN*](nc-wdm-pget_dma_domain.md). 

### -param MaximumAddress
[in, optional] A pointer to a variable that contains the maximum logical address for the common buffer. This parameter indicates that the buffer should be allocated from memory below this address. This parameter is optional and can be specified as NULL to indicate that there is no maximum address.

[in] The size, in bytes, of the common buffer that is to be allocated for the DMA operation.

### -param Flags
[in] The size, in bytes, of the common buffer that is to be allocated for the DMA operation.
| Flag                            | Meaning                                                                                                                                                              |
| ------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| DOMAIN_COMMON_BUFFER_LARGE_PAGE | The common buffer will be allocated using a larger page granularity of PAGE_SIZE * 512. Note that this can increase the chance of the allocation being unsuccessful. |

### -param CacheType
[in, optional] A pointer to a [**MEMORY_CACHING_TYPE**](ne-wdm-_memory_caching_type.md) enumeration indicating whether the routine must enable or disable cached memory in the common buffer that is to be allocated. Only values of **MmNonCached** and **MmCached** are supported. The parameter is optional and can be specified as NULL to specify the caching will be dependent upon the hardware platform default.
 
### -param PreferredNode
[in] The preferred NUMA node from which the memory is to be allocated. If N is the number of NUMA nodes in a multiprocessor system, *PreferredNode* is a number in the range 0 to N–1. For a one-processor system or a non-NUMA multiprocessor system, set *PreferredNode* to zero.

### -param LogicalAddress 
[out] A pointer to a variable into which this routine writes the logical address that the device can use to access the common buffer. The DMA device should use this logical address instead of the physical address that is returned by a routine such as [**MmGetPhysicalAddress**](../ntddk/nf-ntddk-mmgetphysicaladdress.md).

### -param VirtualAddress: 
[out] A pointer to a variable into which this routine writes the corresponding virtual address of the allocated buffer.


## -returns

Returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate [NTSTATUS value](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).


## -remarks



## -see-also
