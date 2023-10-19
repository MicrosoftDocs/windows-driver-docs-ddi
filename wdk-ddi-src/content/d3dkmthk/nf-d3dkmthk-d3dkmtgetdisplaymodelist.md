---
UID: NF:d3dkmthk.D3DKMTGetDisplayModeList
title: D3DKMTGetDisplayModeList function (d3dkmthk.h)
description: Learn more about the D3DKMTGetDisplayModeList function.
ms.date: 10/19/2023
keywords: ["D3DKMTGetDisplayModeList function"]
ms.keywords: D3DKMTGetDisplayModeList, D3DKMTGetDisplayModeList function [Display Devices], OpenGL_Functions_a132bdb6-955b-4af3-a928-f834f5fdf440.xml, d3dkmthk/D3DKMTGetDisplayModeList, display.d3dkmtgetdisplaymodelist
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
 - D3DKMTGetDisplayModeList
 - d3dkmthk/D3DKMTGetDisplayModeList
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
 - D3DKMTGetDisplayModeList
---

# D3DKMTGetDisplayModeList function

## -description

The **D3DKMTGetDisplayModeList** function retrieves a list of available display modes, including modes with extended format.

## -parameters

### -param unnamedParam1

[in/out] **pData** is a pointer to a [**D3DKMT_GETDISPLAYMODELIST**](ns-d3dkmthk-_d3dkmt_getdisplaymodelist.md) structure that contains the arguments for this function.

## -returns

**D3DKMTGetDisplayModeList** returns an **NTSTATUS** value such as one of the following.

| **Return code** | **Description** |
|:--|:--|
| STATUS_SUCCESS                            | The list of available display modes was successfully retrieved, or the number of display modes was returned in **pData->ModeCount** if **pData->pModeList** was NULL and **pData->ModeCount** was zero on input. |
| STATUS_DEVICE_REMOVED                     | The graphics adapter was stopped. |
| STATUS_BUFFER_TOO_SMALL                   | The buffer that the client driver supplied in [**pData->pModeList**](ns-d3dkmthk-_d3dkmt_getdisplaymodelist.md) is not large enough to contain the requested display mode list. |
| STATUS_GRAPHICS_NO_AVAILABLE_VIDPN_TARGET | No video present target is available for use with the video present source that is identified by **pData->VidPnSourceId**. Therefore, no display modes are available for this source. |
| STATUS_INVALID_PARAMETER**                | Parameters were validated and determined to be incorrect. |

## -remarks

To get the number of the display modes for the specified VidPn source (**pData->VidPnSourceId**) on the graphics adapter (**pData->hAdapter**), a client driver can call **D3DKMTGetDisplayModeList** with **pData->pModeList** set to NULL and **pData->ModeCount** as 0. If this call returns STATUS_SUCCESS, the returned **pData->ModeCount** is the total number of the display modes. The client driver can then allocate an array of **ModeCount** [**D3DKMT_DISPLAYMODE**](ns-d3dkmthk-_d3dkmt_displaymode.md) structures, set **pModeList** to point to this array, and call **D3DKMTGetDisplayModeList** again to retrieve the display mode list.

The display attributes on the specified VidPn source can be changed between these two calls, causing the display mode list to be changed. In this case, if the caller-supplied [**D3DKMT_DISPLAYMODE**](ns-d3dkmthk-_d3dkmt_displaymode.md) array isn't big enough to hold the new display mode list, this function will return STATUS_BUFFER_TOO_SMALL with the number of the new display modes in the returned **ModeCount**. The caller can free the previous **D3DKMT_DISPLAYMODE** array, allocate a new **D3DKMT_DISPLAYMODE** array based on the new returned number, and call this function again with the new number and new **D3DKMT_DISPLAYMODE** array to get the new display mode list.

## -see-also

[**D3DKMT_DISPLAYMODE**](ns-d3dkmthk-_d3dkmt_displaymode.md)

[**D3DKMT_GETDISPLAYMODELIST**](ns-d3dkmthk-_d3dkmt_getdisplaymodelist.md)
