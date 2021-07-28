---
UID: NC:d3dkmddi.DXGKCB_UNPINFRAMEBUFFERFORSAVE
title: DXGKCB_UNPINFRAMEBUFFERFORSAVE (d3dkmddi.h)
description: DXGKCB_UNPINFRAMEBUFFERFORSAVE releases the mapping that was set by DXGKCB_PINFRAMEBUFFERFORSAVE.
ms.date: 07/22/2021
keywords: ["DXGKCB_UNPINFRAMEBUFFERFORSAVE callback function"]
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
product:
 - Windows
---

# DXGKCB_UNPINFRAMEBUFFERFORSAVE callback function

## -description

**DXGKCB_UNPINFRAMEBUFFERFORSAVE** releases the mapping that was set by [**DXGKCB_PINFRAMEBUFFERFORSAVE**](nc-d3dkmddi-dxgkcb_pinframebufferforsave.md).

## -parameters

### -param hAdapter

[in] A handle to a display adapter. The driver provides this handle for the master/lead device in the LDA chain.

### -param pUnpinFrameBufferForSave

[in] A pointer to the [**DXGKARGCB_UNPINFRAMEBUFFERFORSAVE**](ns-d3dkmddi-_dxgkargcb_unpinframebufferforsave.md) structure that contains a handle to the memory to be unmapped.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code.

## -remarks

To use this callback function, the kernel-mode driver sets the appropriate members of [**DXGKARGCB_UNPINFRAMEBUFFERFORSAVE**](nc-d3dkmddi-dxgkcb_unpinframebufferforsave.md) and then calls **DXGKCB_UNPINFRAMEBUFFERFORSAVE** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

See [IOMMU-based GPU isolation](/windows-hardware/drivers/display/iommu-based-gpu-isolation) for more information.

## -see-also

[**DXGKCB_PINFRAMEBUFFERFORSAVE**](nc-d3dkmddi-dxgkcb_pinframebufferforsave.md)
