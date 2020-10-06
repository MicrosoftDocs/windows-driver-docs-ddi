---
UID: NF:d3dkmthk.D3DKMTGetOverlayState
title: D3DKMTGetOverlayState function (d3dkmthk.h)
description: The D3DKMTGetOverlayState function retrieves the status about an overlay.
old-location: display\d3dkmtgetoverlaystate.htm
ms.assetid: 6e3db876-c9f9-4de9-a0e2-5911132b72be
ms.date: 05/10/2018
keywords: ["D3DKMTGetOverlayState function"]
ms.keywords: D3DKMTGetOverlayState, D3DKMTGetOverlayState function [Display Devices], OpenGL_Functions_f2301345-c6d8-42bf-82f9-f8f97d29674f.xml, d3dkmthk/D3DKMTGetOverlayState, display.d3dkmtgetoverlaystate
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: D3DKMTGetOverlayState is supported beginning with the Windows 7 operating system.
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
 - D3DKMTGetOverlayState
 - d3dkmthk/D3DKMTGetOverlayState
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
 - D3DKMTGetOverlayState
---

# D3DKMTGetOverlayState function


## -description

The <b>D3DKMTGetOverlayState</b> function retrieves the status about an overlay.

## -parameters

### -param Arg1

*pData* [in, out]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_getoverlaystate">D3DKMT_GETOVERLAYSTATE</a> structure that describes parameters to retrieve status about an overlay.

## -returns

<b>D3DKMTGetOverlayState</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The status about an overlay was successfully retrieved.|
|STATUS_DEVICE_REMOVED|The graphics adapter was stopped or the display device was reset.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|

This function might also return other <b>NTSTATUS</b> values.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_getoverlaystate">D3DKMT_GETOVERLAYSTATE</a>