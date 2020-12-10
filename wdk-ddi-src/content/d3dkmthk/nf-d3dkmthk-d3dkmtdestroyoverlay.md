---
UID: NF:d3dkmthk.D3DKMTDestroyOverlay
title: D3DKMTDestroyOverlay function (d3dkmthk.h)
description: The D3DKMTDestroyOverlay function destroys a kernel-mode overlay object.
old-location: display\d3dkmtdestroyoverlay.htm
ms.date: 05/10/2018
keywords: ["D3DKMTDestroyOverlay function"]
ms.keywords: D3DKMTDestroyOverlay, D3DKMTDestroyOverlay function [Display Devices], OpenGL_Functions_57efc2f4-dbbe-4f91-b724-036b5231c058.xml, d3dkmthk/D3DKMTDestroyOverlay, display.d3dkmtdestroyoverlay
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
 - D3DKMTDestroyOverlay
 - d3dkmthk/D3DKMTDestroyOverlay
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
 - D3DKMTDestroyOverlay
---

# D3DKMTDestroyOverlay function


## -description

The <b>D3DKMTDestroyOverlay</b> function destroys a kernel-mode overlay object.

## -parameters

### -param D3DKMT_DESTROYOVERLAY

*pData* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_destroyoverlay">D3DKMT_DESTROYOVERLAY</a> structure that contains the handle to the overlay to destroy.

## -returns

<b>D3DKMTDestroyOverlay</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The kernel-mode overlay object was successfully destroyed.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|

This function might also return other <b>NTSTATUS</b> values.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_destroyoverlay">D3DKMT_DESTROYOVERLAY</a>
