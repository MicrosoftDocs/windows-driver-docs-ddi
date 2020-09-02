---
UID: NF:d3dkmthk.D3DKMTGetProcessSchedulingPriorityClass
title: D3DKMTGetProcessSchedulingPriorityClass function (d3dkmthk.h)
description: The D3DKMTGetProcessSchedulingPriorityClass function retrieves the scheduling priority for a process.
old-location: display\d3dkmtgetprocessschedulingpriorityclass.htm
ms.assetid: 994df4be-d0ce-4f64-91f5-b5516ce947ec
ms.date: 05/10/2018
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

The <b>D3DKMTGetProcessSchedulingPriorityClass</b> function retrieves the scheduling priority for a process.

## -parameters

## -param

*hProcess*

[in] A handle to the process for which scheduling priority is set.

*pPriority* 

[out] A pointer to a variable that receives a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ne-d3dkmthk-_d3dkmt_schedulingpriorityclass">D3DKMT_SCHEDULINGPRIORITYCLASS</a>-typed value that indicates the priority level for the process.

## -returns

<b>D3DKMTGetProcessSchedulingPriorityClass</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The scheduling priority was successfully retrieved.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|
 
This function might also return other <b>NTSTATUS</b> values.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtsetprocessschedulingpriorityclass">D3DKMTSetProcessSchedulingPriorityClass</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ne-d3dkmthk-_d3dkmt_schedulingpriorityclass">D3DKMT_SCHEDULINGPRIORITYCLASS</a>

