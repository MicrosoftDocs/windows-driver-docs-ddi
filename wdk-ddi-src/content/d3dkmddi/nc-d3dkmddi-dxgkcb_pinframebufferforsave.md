---
UID: NC:d3dkmddi.DXGKCB_PINFRAMEBUFFERFORSAVE
title: DXGKCB_PINFRAMEBUFFERFORSAVE (d3dkmddi.h)
description: DXGKCB_PINFRAMEBUFFERFORSAVE pins down the entire frame buffer at once.
ms.date: 10/13/2021
keywords: ["DXGKCB_PINFRAMEBUFFERFORSAVE callback function"]
req.header: d3dkmddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1803 (WDDM 2.4)
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
---

# DXGKCB_PINFRAMEBUFFERFORSAVE callback function

## -description

A kernel-mode display miniport driver calls **DXGKCB_PINFRAMEBUFFERFORSAVE** to pin down the entire frame buffer at once.

## -parameters

### -param hAdapter [in]

A handle to a display adapter. The driver provides this handle for the master/lead device in the linked display adapter (LDA) chain.

### -param pPinFrameBufferForSave [in/out]

Pointer to a [**DXGKARGCB_PINFRAMEBUFFERFORSAVE**](nc-d3dkmddi-dxgkcb_pinframebufferforsave.md) structure that contains information about the frame buffer to save.

## -returns

**DXGKCB_PINFRAMEBUFFERFORSAVE** returns STATUS_SUCCESS if the operation succeeds. Otherwise, it returns an appropriate NTSTATUS error code.

## -remarks

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, set the appropriate members of [**DXGKARGCB_PINFRAMEBUFFERFORSAVE**](nc-d3dkmddi-dxgkcb_pinframebufferforsave.md) and then call **DxgkCbPinFrameBufferForSave** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

See [IOMMU-based GPU isolation](/windows-hardware/drivers/display/iommu-based-gpu-isolation) for more information.

## -see-also

[**DXGKARGCB_PINFRAMEBUFFERFORSAVE**](nc-d3dkmddi-dxgkcb_pinframebufferforsave.md)

[**DXGKCB_UNPINFRAMEBUFFERFORSAVE**](nc-d3dkmddi-dxgkcb_unpinframebufferforsave.md)

[**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md)
