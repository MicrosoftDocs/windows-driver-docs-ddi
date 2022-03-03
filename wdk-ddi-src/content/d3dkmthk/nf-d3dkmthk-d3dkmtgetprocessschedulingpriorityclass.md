---
UID: NF:d3dkmthk.D3DKMTGetProcessSchedulingPriorityClass
title: D3DKMTGetProcessSchedulingPriorityClass function (d3dkmthk.h)
description: The D3DKMTGetProcessSchedulingPriorityClass function retrieves the scheduling priority for a process.
old-location: display\d3dkmtgetprocessschedulingpriorityclass.htm
ms.date: 02/25/2022
keywords: ["D3DKMTGetProcessSchedulingPriorityClass function"]
ms.keywords: D3DKMTGetProcessSchedulingPriorityClass, D3DKMTGetProcessSchedulingPriorityClass function [Display Devices], OpenGL_Functions_7af39e72-516e-440a-b4be-f0b3f82156d0.xml, d3dkmthk/D3DKMTGetProcessSchedulingPriorityClass, display.d3dkmtgetprocessschedulingpriorityclass
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
 - D3DKMTGetProcessSchedulingPriorityClass
 - d3dkmthk/D3DKMTGetProcessSchedulingPriorityClass
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
 - D3DKMTGetProcessSchedulingPriorityClass
---

# D3DKMTGetProcessSchedulingPriorityClass function

## -description

The **D3DKMTGetProcessSchedulingPriorityClass** function retrieves the scheduling priority for a process.

## -parameters

## -param unnamedParam1 [in]

A handle to the process for which scheduling priority is set.

## -param unnamedParam2 [out]

A pointer to a variable that receives a [D3DKMT_SCHEDULINGPRIORITYCLASS](ne-d3dkmthk-_d3dkmt_schedulingpriorityclass.md) enum value that indicates the priority level for the process.

## -returns

**D3DKMTGetProcessSchedulingPriorityClass** returns one of the following values:

| Return code | Description |
|--|--|
| STATUS_SUCCESS | The scheduling priority was successfully retrieved. |
| STATUS_INVALID_PARAMETER | Parameters were validated and determined to be incorrect. |

This function might also return other **NTSTATUS** values.

## -see-also

[D3DKMTSetProcessSchedulingPriorityClass](nf-d3dkmthk-d3dkmtsetprocessschedulingpriorityclass.md)

[D3DKMT_SCHEDULINGPRIORITYCLASS](ne-d3dkmthk-_d3dkmt_schedulingpriorityclass.md)
