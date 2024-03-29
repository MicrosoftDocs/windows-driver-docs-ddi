---
UID: NF:storport.StorPortAllocateHostMemoryBuffer
title: StorPortAllocateHostMemoryBuffer function (storport.h)
description: This function allocates one or more ranges of physically contiguous memory to be used as a Host Memory Buffer (HMB).
old-location: storage\storportallocatehostmemorybuffer.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["StorPortAllocateHostMemoryBuffer function"]
ms.keywords: StorPortAllocateHostMemoryBuffer, StorPortAllocateHostMemoryBuffer routine [Storage Devices], storage.storportallocatehostmemorybuffer, storport/StorPortAllocateHostMemoryBuffer
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.typenames: 
f1_keywords:
 - StorPortAllocateHostMemoryBuffer
 - storport/StorPortAllocateHostMemoryBuffer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - StorPortAllocateHostMemoryBuffer
---

# StorPortAllocateHostMemoryBuffer function

## -description

**StorPortAllocateHostMemoryBuffer** allocates one or more ranges of physically contiguous memory to be used as a Host Memory Buffer (HMB).

## -parameters

### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).

### -param MinimumBytes [in]

The minimum amount of memory that will be useful to the device, in bytes. A value of 0 indicates that any size of memory up to the preferred size is acceptable.

### -param PreferredBytes [in]

The amount of memory the device prefers, in bytes.  This must be a multiple of the page size.

### -param UtilizationBytes [in]

The total number of blocks allocated on the device, in bytes.

### -param AlignmentBytes [in]

The Host Memory Buffer alignment requirement from the device.

### -param LowestAcceptableAddress [in]

The lowest physical address that is valid for the allocation. For example, if the device can only reference physical memory in the 8 MB to 16 MB range, this value would be set to 0x800000 (8 MB).

### -param HighestAcceptableAddress [in]

The highest physical address that is valid for the allocation. For example, if the device can only reference physical memory below 16 MB, this value would be set to 0xFFFFFF (16 MB - 1).

### -param BoundaryAddressMultiple [in, optional]

The physical address multiple that this allocation must not cross. This parameter is currently not used and must be set to 0.

### -param PhysicalAddressRanges [in, out]

An array of physical address ranges that make up the Host Memory Buffer. The caller should provide a pre-allocated array. **StorPortAllocateHostMemoryBuffer** will fill in the array with one or more physical address ranges.

### -param PhysicalAddressRangeCount [in, out]

The number of entries in **PhysicalAddressRanges**. This function will update this parameter to indicate how many physical address ranges it filled in.

## -returns

**StorPortAllocateHostMemoryBuffer** returns one of the following status codes:

| Return code | Description |
| ----------- | ----------- |
| STOR_STATUS_SUCCESS | The **PhysicalAddressRanges** array contains one or more valid physical address ranges that represent the host memory buffer. |
| STOR_STATUS_INVALID_PARAMETER | This could indicate a minimum value that is greater than a maximum value, a non-page-aligned size, or that **PhysicalAddressRanges** is empty. |
| STOR_STATUS_INSUFFICIENT_RESOURCES | The host memory buffer could not be allocated. |

## -remarks

HMB is memory that the device may use directly and exclusively. The device may use this memory however it sees fit, but it must ensure that there is no data loss or data corruption in the event of a surprise removal or unexpected power loss.

Depending on the allocation policy, this function may allocate as much as the device's preferred size, as little as the device's minimum size, or no memory at all.

This function will attempt to allocate as few physically contiguous address ranges as possible, but it may have to use multiple physical address ranges to satisfy the desired HMB size.

The caller should subsequently call [**StorPortFreeHostMemoryBuffer**](nf-storport-storportfreehostmemorybuffer.md) when it is done with the host memory buffer.

## -see-also

[**StorPortFreeHostMemoryBuffer**](nf-storport-storportfreehostmemorybuffer.md)
