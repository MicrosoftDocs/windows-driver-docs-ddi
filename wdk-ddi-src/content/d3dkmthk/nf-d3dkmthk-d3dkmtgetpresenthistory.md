---
UID: NF:d3dkmthk.D3DKMTGetPresentHistory
title: D3DKMTGetPresentHistory function (d3dkmthk.h)
description: The D3DKMTGetPresentHistory function retrieves copying history.
old-location: display\d3dkmtgetpresenthistory.htm
ms.date: 05/10/2018
keywords: ["D3DKMTGetPresentHistory function"]
ms.keywords: D3DKMTGetPresentHistory, D3DKMTGetPresentHistory function [Display Devices], OpenGL_Functions_9070e169-207c-478d-8eab-b0bcfad65362.xml, d3dkmthk/D3DKMTGetPresentHistory, display.d3dkmtgetpresenthistory
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
 - D3DKMTGetPresentHistory
 - d3dkmthk/D3DKMTGetPresentHistory
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
 - D3DKMTGetPresentHistory
---

# D3DKMTGetPresentHistory function


## -description

The <b>D3DKMTGetPresentHistory</b> function retrieves copying history.

## -parameters

### -param unnamedParam1

*pData* [in, out]

Supplies a pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_getpresenthistory">D3DKMT_GETPRESENTHISTORY</a> structure that describes the copying history.

## -returns

Returns <b>STATUS_SUCCESS</b> if copying history is successfully retrieved; otherwise an appropriate error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_getpresenthistory">D3DKMT_GETPRESENTHISTORY</a>
