---
UID: NF:d3dkmthk.D3DKMTSetDisplayPrivateDriverFormat
title: D3DKMTSetDisplayPrivateDriverFormat function (d3dkmthk.h)
description: The D3DKMTSetDisplayPrivateDriverFormat function changes the private-format attribute of a video present source.
old-location: display\d3dkmtsetdisplayprivatedriverformat.htm
ms.assetid: 4b720076-161f-47b4-b410-f9554e502a53
ms.date: 05/10/2018
keywords: ["D3DKMTSetDisplayPrivateDriverFormat function"]
ms.keywords: D3DKMTSetDisplayPrivateDriverFormat, D3DKMTSetDisplayPrivateDriverFormat function [Display Devices], OpenGL_Functions_742fb584-0b9d-4650-a0a6-64f3e3f55dff.xml, d3dkmthk/D3DKMTSetDisplayPrivateDriverFormat, display.d3dkmtsetdisplayprivatedriverformat
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - D3DKMTSetDisplayPrivateDriverFormat
 - d3dkmthk/D3DKMTSetDisplayPrivateDriverFormat
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
 - D3DKMTSetDisplayPrivateDriverFormat
---

# D3DKMTSetDisplayPrivateDriverFormat function


## -description

The <b>D3DKMTSetDisplayPrivateDriverFormat</b> function changes the private-format attribute of a video present source.

## -parameters

### -param D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_setdisplayprivatedriverformat">D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT</a> structure that describes how to format a video present source.

## -returns

<b>D3DKMTSetDisplayPrivateDriverFormat</b> returns one of the following values:

| **Return code** | **Description** |
|:--|:--|
| **STATUS_SUCCESS** | The video present source was successfully changed. |
| **STATUS_DEVICE_REMOVED** | The graphics adapter was stopped or the display device was reset. |
| **STATUS_INVALID_PARAMETER** | Parameters were validated and determined to be incorrect. |
| **STATUS_GRAPHICS_NOT_EXCLUSIVE_MODE_OWNER** | Before the call to [D3DKMTSetDisplayPrivateDriverFormat](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtsetdisplayprivatedriverformat), the device did not acquire exclusive ownership of the view. Therefore, the device could not change the private-format attribute of the video present source. |
| **STATUS_NOT_SUPPORTED** | The display miniport driver does not support the [DxgkDdiSetDisplayPrivateDriverFormat](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_setdisplayprivatedriverformat) function. |
| **STATUS_UNSUCCESSFUL** | The display miniport driver could not change the private-format attribute of the view for the video present source. |

This function might also return other NTSTATUS values.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_setdisplayprivatedriverformat">D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_setdisplayprivatedriverformat">DxgkDdiSetDisplayPrivateDriverFormat</a>

