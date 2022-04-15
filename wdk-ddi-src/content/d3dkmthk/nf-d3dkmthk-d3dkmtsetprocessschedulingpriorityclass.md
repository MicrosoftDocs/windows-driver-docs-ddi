---
UID: NF:d3dkmthk.D3DKMTSetProcessSchedulingPriorityClass
title: D3DKMTSetProcessSchedulingPriorityClass function (d3dkmthk.h)
description: The D3DKMTSetProcessSchedulingPriorityClass function sets the scheduling priority for a process.
old-location: display\d3dkmtsetprocessschedulingpriorityclass.htm
ms.date: 04/14/2022
keywords: ["D3DKMTSetProcessSchedulingPriorityClass function"]
ms.keywords: D3DKMTSetProcessSchedulingPriorityClass, D3DKMTSetProcessSchedulingPriorityClass function [Display Devices], OpenGL_Functions_757bbe38-6623-4438-8af3-a2282bec6c78.xml, d3dkmthk/D3DKMTSetProcessSchedulingPriorityClass, display.d3dkmtsetprocessschedulingpriorityclass
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
 - D3DKMTSetProcessSchedulingPriorityClass
 - d3dkmthk/D3DKMTSetProcessSchedulingPriorityClass
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
 - D3DKMTSetProcessSchedulingPriorityClass
---

# D3DKMTSetProcessSchedulingPriorityClass function

## -description

The **D3DKMTSetProcessSchedulingPriorityClass** function sets the scheduling priority for a process.

## -parameters

### -param unnamedParam1 [in]

A handle to the process that scheduling priority is set for.

### -param unnamedParam2 [in]

A [**D3DKMT_SCHEDULINGPRIORITYCLASS**](ne-d3dkmthk-_d3dkmt_schedulingpriorityclass.md) enum value that indicates the priority level to set for the process.

## -returns

**D3DKMTSetProcessSchedulingPriorityClass** returns one of the following values:

| Return code              | Description |
| -----------              | ----------- |
| STATUS_SUCCESS           | The scheduling priority was successfully set. |
| STATUS_INVALID_PARAMETER | Parameters were validated and determined to be incorrect. |

This function might also return other **NTSTATUS** values.

## -see-also

[**D3DKMTGetProcessSchedulingPriorityClass**](nf-d3dkmthk-d3dkmtgetprocessschedulingpriorityclass.md)

[**D3DKMT_SCHEDULINGPRIORITYCLASS**](ne-d3dkmthk-_d3dkmt_schedulingpriorityclass.md)
