---
UID: NF:d3dkmthk.D3DKMTCheckOcclusion
title: D3DKMTCheckOcclusion function (d3dkmthk.h)
description: The D3DKMTCheckOcclusion function verifies whether the client area of a window is occluded.
old-location: display\d3dkmtcheckocclusion.htm
ms.assetid: ce889a72-5f42-4bcf-aa15-6ec9b0423781
ms.date: 05/10/2018
ms.keywords: D3DKMTCheckOcclusion, D3DKMTCheckOcclusion callback function [Display Devices], OpenGL_Functions_a73b8485-971d-47a7-bc42-77bd709c5a74.xml, PFND3DKMT_CHECKOCCLUSION, PFND3DKMT_CHECKOCCLUSION callback, d3dkmthk/D3DKMTCheckOcclusion, display.d3dkmtcheckocclusion
ms.topic: function
f1_keywords:
 - "d3dkmthk/D3DKMTCheckOcclusion"
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
req.lib: Gdi32.lib 
req.dll: Gdi32.dll 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Gdi32.dll
api_name:
- D3DKMTCheckOcclusion
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTCheckOcclusion function

## -description

The <b>D3DKMTCheckOcclusion</b> function verifies whether the client area of a window is occluded.

## -parameters

### -param D3DKMT_CHECKOCCLUSION

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/ns-d3dkmthk-_d3dkmt_checkocclusion">D3DKMT_CHECKOCCLUSION</a> structure that describes parameters for checking occlusion.

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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/ns-d3dkmthk-_d3dkmt_checkocclusion">D3DKMT_CHECKOCCLUSION</a>

