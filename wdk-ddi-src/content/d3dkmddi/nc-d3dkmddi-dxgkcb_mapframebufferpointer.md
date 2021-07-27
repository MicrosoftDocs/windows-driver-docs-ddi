---
UID: NC:d3dkmddi.DXGKCB_MAPFRAMEBUFFERPOINTER
title: DXGKCB_MAPFRAMEBUFFERPOINTER (d3dkmddi.h)
description: DXGKCB_MAPFRAMEBUFFERPOINTER obtains a pointer to a subregion of the section object that was created for each physical adapter.
ms.date: 07/22/2021
keywords: ["DXGKCB_MAPFRAMEBUFFERPOINTER callback function"]
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
 - DXGKCB_MAPFRAMEBUFFERPOINTER
 - d3dkmddi/DXGKCB_MAPFRAMEBUFFERPOINTER
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKCB_MAPFRAMEBUFFERPOINTER
product:
 - Windows
---

# DXGKCB_MAPFRAMEBUFFERPOINTER callback function

## -description

**DXGKCB_MAPFRAMEBUFFERPOINTER** obtains a pointer to a subregion of the section object that was created for each physical adapter.

## -parameters

### -param hAdapter

[in] A handle to a display adapter. The driver provides this handle for the master/lead device in the LDA chain.

### -param pMapFrameBufferPointer

[in/out] Pointer to [**DXGKARGCB_MAPFRAMEBUFFERPOINTER**](ns-d3dkmddi-_dxgkargcb_mapframebufferpointer.md) structure that contains a pointer to the subregion of the section object.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code.

## -remarks

To use this callback function, the kernel-mode driver sets the appropriate members of [**DXGKARGCB_MAPFRAMEBUFFERPOINTER**](ns-d3dkmddi-_dxgkargcb_mapframebufferpointer.md) and then calls **DXGKCB_MAPFRAMEBUFFERPOINTER** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

See [IOMMU-based GPU isolation](/windows-hardware/drivers/display/iommu-based-gpu-isolation) for more information.

## -see-also

[**DXGKCB_UNMAPFRAMEBUFFERPOINTER**](nc-d3dkmddi-dxgkcb_unmapframebufferpointer.md)
