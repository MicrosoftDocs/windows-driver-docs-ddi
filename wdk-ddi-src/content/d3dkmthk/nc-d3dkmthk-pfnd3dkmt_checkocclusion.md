---
UID: NC:d3dkmthk.PFND3DKMT_CHECKOCCLUSION
title: PFND3DKMT_CHECKOCCLUSION (d3dkmthk.h)
description: The D3DKMTCheckOcclusion function verifies whether the client area of a window is occluded.
old-location: display\d3dkmtcheckocclusion.htm
ms.date: 05/10/2018
keywords: ["PFND3DKMT_CHECKOCCLUSION callback function"]
ms.keywords: D3DKMTCheckOcclusion, D3DKMTCheckOcclusion callback function [Display Devices], OpenGL_Functions_a73b8485-971d-47a7-bc42-77bd709c5a74.xml, PFND3DKMT_CHECKOCCLUSION, PFND3DKMT_CHECKOCCLUSION callback, d3dkmthk/D3DKMTCheckOcclusion, display.d3dkmtcheckocclusion
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3DKMT_CHECKOCCLUSION
 - d3dkmthk/PFND3DKMT_CHECKOCCLUSION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_CHECKOCCLUSION
---

# PFND3DKMT_CHECKOCCLUSION callback function


## -description

The <b>D3DKMTCheckOcclusion</b> function verifies whether the client area of a window is occluded.

## -parameters

### -param Arg1

*pData* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_checkocclusion">D3DKMT_CHECKOCCLUSION</a> structure that describes parameters for checking occlusion.

## -returns

<b>D3DKMTCheckOcclusion</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The client area of the window is not occluded.|
|STATUS_GRAPHICS_PRESENT_OCCLUDED|The client area of the window is occluded.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|


This function might also return other <b>NTSTATUS</b> values.

## -remarks

The handle to the window that is checked for occlusion must be valid. A window is not occluded if a part of its client area lies on a unowned video present network (VidPn) source, if its client area is an empty rectangular area (RECT), or if desktop composition is running.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_checkocclusion">D3DKMT_CHECKOCCLUSION</a>

