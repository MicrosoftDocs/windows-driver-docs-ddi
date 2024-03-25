---
UID: NF:d3dkmthk.D3DKMTSetVidPnSourceOwner
title: D3DKMTSetVidPnSourceOwner function (d3dkmthk.h)
description: The D3DKMTSetVidPnSourceOwner function sets and releases the video present source in the path of a video present network (VidPN) topology that owns the VidPN.
old-location: display\d3dkmtsetvidpnsourceowner.htm
ms.date: 03/01/2022
keywords: ["D3DKMTSetVidPnSourceOwner function"]
ms.keywords: D3DKMTSetVidPnSourceOwner, D3DKMTSetVidPnSourceOwner function [Display Devices], OpenGL_Functions_3c0b89d9-b3d6-4668-a227-3bc7d0ed2f2f.xml, d3dkmthk/D3DKMTSetVidPnSourceOwner, display.d3dkmtsetvidpnsourceowner
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows Vista
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - D3DKMTSetVidPnSourceOwner
 - d3dkmthk/D3DKMTSetVidPnSourceOwner
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Gdi32.dll
 - API-MS-Win-dx-d3dkmt-l1-1-0.dll
 - API-MS-Win-dx-d3dkmt-l1-1-1.dll
 - API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
 - D3DKMTSetVidPnSourceOwner
---

# D3DKMTSetVidPnSourceOwner function

## -description

The **D3DKMTSetVidPnSourceOwner** function sets and releases the video present source in the path of a video present network (VidPN) topology that owns the VidPN.

## -parameters

### -param unnamedParam1 [in]

A pointer to a [D3DKMT_SETVIDPNSOURCEOWNER](ns-d3dkmthk-_d3dkmt_setvidpnsourceowner.md) structure that describes the parameters for setting or releasing.

## -returns

**D3DKMTSetVidPnSourceOwner** returns one of the following values:

| Return code | Description |
|--|--|
| STATUS_SUCCESS | The video present source was successfully set or released. |
| STATUS_DEVICE_REMOVED | The graphics adapter was stopped or the display device was reset. |
| STATUS_GRAPHICS_VIDPN_SOURCE_IN_USE | The video present source that is specified by an element in the array that the pVidPnSourceId member of [D3DKMT_SETVIDPNSOURCEOWNER](ns-d3dkmthk-_d3dkmt_setvidpnsourceowner.md) specifies is already owned by a display mode manager (DMM) client and cannot be used until the client releases the video present source. |
| STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_SOURCE | The video present source that is specified by an element in the array that the pVidPnSourceId member of [D3DKMT_SETVIDPNSOURCEOWNER](ns-d3dkmthk-_d3dkmt_setvidpnsourceowner.md) specifies is invalid. |
| STATUS_INVALID_PARAMETER | Parameters were validated and determined to be incorrect. |

This function might also return other **NTSTATUS** values.

## -remarks

To set ownership of video present sources, the OpenGL installable client driver (ICD) sets values in the array that the *pType* member of the [D3DKMT_SETVIDPNSOURCEOWNER](ns-d3dkmthk-_d3dkmt_setvidpnsourceowner.md) structure specifies, identifiers of the video present sources in the array that the *pVidPnSourceId* member of **D3DKMT_SETVIDPNSOURCEOWNER** specifies, and the number of video present sources in the *VidPnSourceCount* member of **D3DKMT_SETVIDPNSOURCEOWNER**.

To release ownership of any video present sources, the ICD sets *pType* and *pVidPnSourceId* to NULL and *VidPnSourceCount* to zero in **D3DKMT_SETVIDPNSOURCEOWNER**.

The ICD passes a pointer to [D3DKMT_SETVIDPNSOURCEOWNER](ns-d3dkmthk-_d3dkmt_setvidpnsourceowner.md) in the *pData* parameter in a call to **D3DKMTSetVidPnSourceOwner**.

## -see-also

[D3DKMT_SETVIDPNSOURCEOWNER](ns-d3dkmthk-_d3dkmt_setvidpnsourceowner.md)
