---
UID: NC:d3dkmddi.DXGKCB_FREEPAGESFROMMDL
title: DXGKCB_FREEPAGESFROMMDL (d3dkmddi.h)
description: DXGKCB_FREEPAGESFROMMDL frees all the physical pages described by a memory descriptor list (MDL) and allocated by the DXGKCB_ALLOCATEPAGESFORMDL routine.
ms.date: 10/13/2021
keywords: ["DXGKCB_FREEPAGESFROMMDL callback function"]
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
 - DXGKCB_FREEPAGESFROMMDL
 - d3dkmddi/DXGKCB_FREEPAGESFROMMDL
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKCB_FREEPAGESFROMMDL
---

# DXGKCB_FREEPAGESFROMMDL callback function

## -description

**DXGKCB_FREEPAGESFROMMDL** frees all the physical pages described by a memory descriptor list (MDL) and allocated by the [**DXGKCB_ALLOCATEPAGESFORMDL**](nc-d3dkmddi-dxgkcb_allocatepagesformdl.md) routine.

## -parameters

### -param hAdapter [in]

Handle to a display adapter.

### -param pFreePagesFromMdl [in]

Pointer to a [**DXGKARGCB_FREEPAGESFROMMDL**](ns-d3dkmddi-_dxgkargcb_freepagesfrommdl.md) structure that contains a handle to the pages for the MDL.

## -returns

Returns STATUS_SUCCESS if the operation succeeds. Otherwise, returns an appropriate NTSTATUS error code.

## -remarks

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, set the members of [**DXGKARGCB_FREEPAGESFROMMDL**](ns-d3dkmddi-_dxgkargcb_freepagesfrommdl.md) and then calls **DxgkCbFreePagesFromMdl** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

See [IOMMU-based GPU isolation](/windows-hardware/drivers/display/iommu-based-gpu-isolation) for more information.

## -see-also

[**DXGKARGCB_FREEPAGESFROMMDL**](ns-d3dkmddi-_dxgkargcb_freepagesfrommdl.md)

[**DXGKCB_ALLOCATEPAGESFORMDL**](nc-d3dkmddi-dxgkcb_allocatepagesformdl.md)

[**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md)
