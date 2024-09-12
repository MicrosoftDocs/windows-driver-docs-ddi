---
UID: NS:d3dkmddi._DXGK_BUILDPAGINGBUFFER_NOTIFYALLOC
tech.root: display
title: DXGK_BUILDPAGINGBUFFER_NOTIFYALLOC
ms.date: 08/19/2024
targetos: Windows
description: Learn more about the DXGK_BUILDPAGINGBUFFER_NOTIFYALLOC structure.
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGK_BUILDPAGINGBUFFER_NOTIFYALLOC
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_BUILDPAGINGBUFFER_NOTIFYALLOC
 - DXGK_BUILDPAGINGBUFFER_NOTIFYALLOC
f1_keywords:
 - _DXGK_BUILDPAGINGBUFFER_NOTIFYALLOC
 - d3dkmddi/_DXGK_BUILDPAGINGBUFFER_NOTIFYALLOC
 - DXGK_BUILDPAGINGBUFFER_NOTIFYALLOC
 - d3dkmddi/DXGK_BUILDPAGINGBUFFER_NOTIFYALLOC
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGK_BUILDPAGINGBUFFER_NOTIFYALLOC
---

## -description

The **DXGK_BUILDPAGINGBUFFER_NOTIFYALLOC** structure is used to notify the kernel-mode driver (KMD) of an allocation that is about to be used in a [**DXGK_OPERATION_NOTIFY_ALLOC**](ne-d3dkmddi-_dxgk_buildpagingbuffer_operation.md) paging operation.

## -struct-fields

### -field hAllocation

The driver allocation handle returned from [**DxgkDdiCreateAllocation**](nc-d3dkmddi-dxgkddi_createallocation.md).

### -field hKmdProcessHandle

The driver process object handle returned from [**DxgkDdiCreateProcess**](nc-d3dkmddi-dxgkddi_createprocess.md). This handle is zero when the **Eviction** flag is set.

### -field Flags

A [**DXGK_NOTIFYALLOCFLAGS**](ns-d3dkmddi-dxgk_notifyallocflags.md) structure specifying the flags related to the operation.

### -field OffsetInBytes

Offset from the start of the allocation, in bytes. This value is used when an operation is performed on part of an allocation.

### -field SizeInBytes

Size of the operation, in bytes.

### -field GpuVirtualAddressAtOffset

The GPU virtual address corresponding to the allocation offset. When the **Eviction** flag is set, the GPU VA address is in the paging process context. When the **IoMmuUnmap** flag is set, the GPU VA address is in the context of the process defined by **hKmdProcessHandle**.

## -remarks

For more information, see [Allocation Notification](/windows-hardware/drivers/display/allocation-notification).

## -see-also

[**DXGK_ALLOCATIONINFOFLAGS2**](ns-d3dkmddi-dxgk_allocationinfoflags2.md)

[**DXGK_BUILDPAGINGBUFFER_OPERATION**](ne-d3dkmddi-_dxgk_buildpagingbuffer_operation.md)

[**DXGK_NOTIFYALLOCFLAGS**](ns-d3dkmddi-dxgk_notifyallocflags.md)

[**DXGKARG_BUILDPAGINGBUFFER**](ns-d3dkmddi-_dxgkarg_buildpagingbuffer.md)

[**DxgkDdiBuildPagingBuffer**](nc-d3dkmddi-dxgkddi_buildpagingbuffer.md)
