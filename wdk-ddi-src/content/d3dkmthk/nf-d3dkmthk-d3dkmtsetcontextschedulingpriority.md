---
UID: NF:d3dkmthk.D3DKMTSetContextSchedulingPriority
title: D3DKMTSetContextSchedulingPriority function (d3dkmthk.h)
description: The D3DKMTSetContextSchedulingPriority function sets the scheduling priority for a device context.
old-location: display\d3dkmtsetcontextschedulingpriority.htm
ms.assetid: 781d5a78-a3e2-4cac-868d-c4ae8b39b2fc
ms.date: 05/10/2018
keywords: ["D3DKMTSetContextSchedulingPriority function"]
ms.keywords: D3DKMTSetContextSchedulingPriority, D3DKMTSetContextSchedulingPriority function [Display Devices], OpenGL_Functions_f9314ed6-8aad-4c55-b42a-f1223dada5bc.xml, d3dkmthk/D3DKMTSetContextSchedulingPriority, display.d3dkmtsetcontextschedulingpriority
f1_keywords:
 - "d3dkmthk/D3DKMTSetContextSchedulingPriority"
 - "D3DKMTSetContextSchedulingPriority"
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
- D3DKMTSetContextSchedulingPriority
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTSetContextSchedulingPriority function


## -description


The <b>D3DKMTSetContextSchedulingPriority</b> function sets the scheduling priority for a device context.


## -parameters


### -param D3DKMT_SETCONTEXTSCHEDULINGPRIORITY

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_setcontextschedulingpriority">D3DKMT_SETCONTEXTSCHEDULINGPRIORITY</a> structure that describes parameters for setting the scheduling priority for a device context.

## -returns

<b>D3DKMTSetContextSchedulingPriority</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The scheduling priority was successfully set.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|
 
This function might also return other NTSTATUS values.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_setcontextschedulingpriority">D3DKMT_SETCONTEXTSCHEDULINGPRIORITY</a>
 

 

