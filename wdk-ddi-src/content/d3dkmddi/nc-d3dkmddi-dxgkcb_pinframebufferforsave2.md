---
UID: NC:d3dkmddi.DXGKCB_PINFRAMEBUFFERFORSAVE2
tech.root: display
title: DXGKCB_PINFRAMEBUFFERFORSAVE2
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: The DxgkCbPinFrameBufferForSave2 callback function pins an entire frame buffer at once.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGKCB_PINFRAMEBUFFERFORSAVE2
f1_keywords:
 - DXGKCB_PINFRAMEBUFFERFORSAVE2
 - d3dkmddi/DXGKCB_PINFRAMEBUFFERFORSAVE2
dev_langs:
 - c++
---

## -description

The **DxgkCbPinFrameBufferForSave2** callback function pins an entire frame buffer at once.

## -parameters

### -param hAdapter

A handle to a display adapter. The driver provides this handle for the main/lead device in the linked display adapter (LDA) chain.

### -param pPinFrameBufferForSave2

Pointer to a [**DXGKARGCB_PINFRAMEBUFFERFORSAVE2**](ns-d3dkmddi-dxgkargcb_open_physical_memory_object.md) structure that contains information about the frame buffer to save.

## -returns

Returns STATUS_SUCCESS if the operation succeeds. Otherwise, returns an appropriate NTSTATUS error code.

## -prototype

```cpp
//Declaration

DXGKCB_PINFRAMEBUFFERFORSAVE2 DxgkCbPinFrameBufferForSave2;

// Definition
NTSTATUS
DxgkCbPinFrameBufferForSave2(
    HANDLE hAdapter,
    DXGKARGCB_PINFRAMEBUFFERFORSAVE2 *pArgs
    );
```

## -remarks

The original IOMMU specification included a pair of callback functions to query memory needed to save the frame buffer. The frame buffer save area was created as a section object during initialization, and the driver used these callbacks to obtain an IOMMU mapped region when needed.

Drivers that use address descriptor lists (ADLs) to support logical DMA remapping implement **DxgkCbPinFrameBufferForSave2** instead of [**DxgkCbPinFrameBufferForSave**](nc-d3dkmddi-dxgkcb_pinframebufferforsave.md).

The memory pinned using **DxgkCbPinFrameBufferForSave2** can be unpinned using the original [**DxgkCbUnpinFrameBufferForSave**](nc-d3dkmddi-dxgkcb_unpinframebufferforsave.md) callback.

## -see-also

[**DXGKARGCB_PINFRAMEBUFFERFORSAVE2**](ns-d3dkmddi-dxgkargcb_open_physical_memory_object.md)

[**DxgkCbPinFrameBufferForSave**](nc-d3dkmddi-dxgkcb_pinframebufferforsave.md)

[**DxgkCbUnpinFrameBufferForSave**](nc-d3dkmddi-dxgkcb_unpinframebufferforsave.md)
