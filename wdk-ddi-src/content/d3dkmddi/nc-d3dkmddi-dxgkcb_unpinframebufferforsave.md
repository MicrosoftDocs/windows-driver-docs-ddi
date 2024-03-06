---
UID: NC:d3dkmddi.DXGKCB_UNPINFRAMEBUFFERFORSAVE
title: DXGKCB_UNPINFRAMEBUFFERFORSAVE (d3dkmddi.h)
description: DXGKCB_UNPINFRAMEBUFFERFORSAVE releases the mapping that was set by DXGKCB_PINFRAMEBUFFERFORSAVE.
ms.date: 10/13/2021
keywords: ["DXGKCB_UNPINFRAMEBUFFERFORSAVE callback function"]
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
 - DXGKCB_UNPINFRAMEBUFFERFORSAVE
 - d3dkmddi/DXGKCB_UNPINFRAMEBUFFERFORSAVE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKCB_UNPINFRAMEBUFFERFORSAVE
---

# DXGKCB_UNPINFRAMEBUFFERFORSAVE callback function

## -description

A kernel-mode display miniport driver calls **DXGKCB_UNPINFRAMEBUFFERFORSAVE** to release the mapping that was set in a prior call to [**DXGKCB_PINFRAMEBUFFERFORSAVE2**](nc-d3dkmddi-dxgkcb_pinframebufferforsave2.md) or [**DXGKCB_PINFRAMEBUFFERFORSAVE**](nc-d3dkmddi-dxgkcb_pinframebufferforsave.md).

## -parameters

### -param hAdapter [in]

A handle to a display adapter. The driver provides this handle for the master/lead device in the LDA chain.

### -param pUnpinFrameBufferForSave [in]

A pointer to the [**DXGKARGCB_UNPINFRAMEBUFFERFORSAVE**](ns-d3dkmddi-_dxgkargcb_unpinframebufferforsave.md) structure that contains a handle to the memory to be unmapped.

## -returns

**DXGKCB_UNPINFRAMEBUFFERFORSAVE** returns STATUS_SUCCESS if the operation succeeds. Otherwise, it returns one of the error codes defined in *Ntstatus.h*.

## -remarks

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, set the members of [**DXGKARGCB_UNPINFRAMEBUFFERFORSAVE**](nc-d3dkmddi-dxgkcb_unpinframebufferforsave.md) and then call **DxgkCbUnpinFrameBufferForSave** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

See [IOMMU-based GPU isolation](/windows-hardware/drivers/display/iommu-based-gpu-isolation) for more information.

## -see-also

[**DXGKARGCB_UNPINFRAMEBUFFERFORSAVE**](nc-d3dkmddi-dxgkcb_unpinframebufferforsave.md)

[**DXGKCB_PINFRAMEBUFFERFORSAVE**](nc-d3dkmddi-dxgkcb_pinframebufferforsave.md)

[**DXGKCB_PINFRAMEBUFFERFORSAVE2**](nc-d3dkmddi-dxgkcb_pinframebufferforsave2.md)

[**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md)
