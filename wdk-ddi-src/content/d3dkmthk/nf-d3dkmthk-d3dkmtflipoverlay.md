---
UID: NF:d3dkmthk.D3DKMTFlipOverlay
title: D3DKMTFlipOverlay function (d3dkmthk.h)
description: The D3DKMTFlipOverlay function changes the allocation to display on the overlay.
old-location: display\d3dkmtflipoverlay.htm
ms.assetid: 09424b92-bf55-4348-8b6a-f632a0dc9b2f
ms.date: 05/10/2018
keywords: ["D3DKMTFlipOverlay function"]
ms.keywords: D3DKMTFlipOverlay, D3DKMTFlipOverlay function [Display Devices], OpenGL_Functions_37a9811c-26a3-46f3-aba1-39dc9526f282.xml, d3dkmthk/D3DKMTFlipOverlay, display.d3dkmtflipoverlay
f1_keywords:
 - "d3dkmthk/D3DKMTFlipOverlay"
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
- API-MS-Win-dx-d3dkmt-l1-1-0.dll
- API-MS-Win-dx-d3dkmt-l1-1-1.dll
- API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
- D3DKMTFlipOverlay
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTFlipOverlay function

## -description

The <b>D3DKMTFlipOverlay</b> function changes the allocation to display on the overlay.

## -parameters

### -param D3DKMT_FLIPOVERLAY

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_flipoverlay">D3DKMT_FLIPOVERLAY</a> structure that describes how to change the display on the overlay.

## -returns

<b>D3DKMTFlipOverlay</b> returns one of the following values:

| **Return code** | **Description** |
|:--|:--|
| **STATUS_SUCCESS** | The kernel-mode overlay object was successfully flipped. |
| **STATUS_DEVICE_REMOVED** | The graphics adapter was stopped or the display device was reset. |
| **STATUS_INVALID_PARAMETER** | Parameters were validated and determined to be incorrect. |
| **STATUS_NO_MEMORY** | [D3DKMTFlipOverlay](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtflipoverlay)  could not complete because of insufficient memory. |

This function might also return other <b>NTSTATUS</b> values.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_flipoverlay">D3DKMT_FLIPOVERLAY</a>
 

 

