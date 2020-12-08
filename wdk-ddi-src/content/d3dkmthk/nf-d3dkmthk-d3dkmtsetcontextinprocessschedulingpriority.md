---
UID: NF:d3dkmthk.D3DKMTSetContextInProcessSchedulingPriority
title: D3DKMTSetContextInProcessSchedulingPriority function (d3dkmthk.h)
description: Called by an in-process (in-proc) Microsoft Direct3D composition device to set the scheduling priority for a device context that is in the same process as other device contexts.
old-location: display\d3dkmtsetcontextinprocessschedulingpriority.htm
ms.date: 05/10/2018
keywords: ["D3DKMTSetContextInProcessSchedulingPriority function"]
ms.keywords: D3DKMTSetContextInProcessSchedulingPriority, D3DKMTSetContextInProcessSchedulingPriority function [Display Devices], d3dkmthk/D3DKMTSetContextInProcessSchedulingPriority, display.d3dkmtsetcontextinprocessschedulingpriority
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
 - D3DKMTSetContextInProcessSchedulingPriority
 - d3dkmthk/D3DKMTSetContextInProcessSchedulingPriority
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Gdi32.dll
api_name:
 - D3DKMTSetContextInProcessSchedulingPriority
---

# D3DKMTSetContextInProcessSchedulingPriority function


## -description

Called by an in-process (in-proc) Microsoft Direct3D composition device to set the scheduling priority for a device context that is in the same process as other device contexts.

## -parameters

### -param D3DKMT_SETCONTEXTINPROCESSSCHEDULINGPRIORITY

[in] A pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_setcontextinprocessschedulingpriority">D3DKMT_SETCONTEXTINPROCESSSCHEDULINGPRIORITY</a> structure that describes parameters for setting the scheduling priority for a device context.

## -returns

Returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The scheduling priority was successfully set.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtgetcontextinprocessschedulingpriority">D3DKMTGetContextInProcessSchedulingPriority</a>

<a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_setcontextinprocessschedulingpriority">D3DKMT_SETCONTEXTINPROCESSSCHEDULINGPRIORITY</a>
