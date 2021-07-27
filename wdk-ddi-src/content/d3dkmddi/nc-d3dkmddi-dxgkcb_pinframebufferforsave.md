---
UID: NC:d3dkmddi.DXGKCB_PINFRAMEBUFFERFORSAVE
title: DXGKCB_PINFRAMEBUFFERFORSAVE (d3dkmddi.h)
description: DXGKCB_PINFRAMEBUFFERFORSAVE pins down the entire frame buffer at once.
ms.date: 07/22/2021
keywords: ["DXGKCB_PINFRAMEBUFFERFORSAVE callback function"]
req.header: d3dkmddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1803
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
targetos: Windows
tech.root: display
f1_keywords:
 - DXGKCB_PINFRAMEBUFFERFORSAVE
 - d3dkmddi/DXGKCB_PINFRAMEBUFFERFORSAVE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKCB_PINFRAMEBUFFERFORSAVE
product:
 - Windows
---

# DXGKCB_PINFRAMEBUFFERFORSAVE callback function

## -description

**DXGKCB_PINFRAMEBUFFERFORSAVE** pins down the entire frame buffer at once.

## -parameters

### -param hAdapter

[in] A handle to a display adapter. The driver provides this handle for the master/lead device in the LDA chain.

### -param pPinFrameBufferForSave

[in/out] Pointer to a [**DXGKARGCB_PINFRAMEBUFFERFORSAVE**](nc-d3dkmddi-dxgkcb_pinframebufferforsave.md) structure that contains information about the frame buffer to save.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code.

## -remarks

To use this callback function, the kernel-mode driver sets the appropriate members of [**DXGKARGCB_PINFRAMEBUFFERFORSAVE**](nc-d3dkmddi-dxgkcb_pinframebufferforsave.md) and then calls **DXGKCB_PINFRAMEBUFFERFORSAVE** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

See [IOMMU-based GPU isolation](/windows-hardware/drivers/display/iommu-based-gpu-isolation) for more information.

## -see-also

[**DXGKCB_UNPINFRAMEBUFFERFORSAVE**](nc-d3dkmddi-dxgkcb_unpinframebufferforsave.md)
