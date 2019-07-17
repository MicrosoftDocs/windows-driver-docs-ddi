---
UID: NF:d3dkmthk.D3DKMTGetPresentHistory
title: D3DKMTGetPresentHistory function (d3dkmthk.h)
description: The D3DKMTGetPresentHistory function retrieves copying history.
old-location: display\d3dkmtgetpresenthistory.htm
ms.assetid: e00af04e-4770-4505-a06c-c44405dcaab5
ms.date: 05/10/2018
ms.keywords: D3DKMTGetPresentHistory, D3DKMTGetPresentHistory function [Display Devices], OpenGL_Functions_9070e169-207c-478d-8eab-b0bcfad65362.xml, d3dkmthk/D3DKMTGetPresentHistory, display.d3dkmtgetpresenthistory
ms.topic: function
f1_keywords:
 - "d3dkmthk/D3DKMTGetPresentHistory"
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
- D3DKMTGetPresentHistory
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTGetPresentHistory function


## -description


The <b>D3DKMTGetPresentHistory</b> function retrieves copying history.


## -parameters




### -param Arg1






*pData* [in, out]

Supplies a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/ns-d3dkmthk-_d3dkmt_getpresenthistory">D3DKMT_GETPRESENTHISTORY</a> structure that describes the copying history.


## -returns



Returns <b>STATUS_SUCCESS</b> if copying history is successfully retrieved; otherwise an appropriate error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/ns-d3dkmthk-_d3dkmt_getpresenthistory">D3DKMT_GETPRESENTHISTORY</a>
 

 

