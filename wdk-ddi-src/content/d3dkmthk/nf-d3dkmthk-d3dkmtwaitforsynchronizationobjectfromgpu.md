---
UID: NF:d3dkmthk.D3DKMTWaitForSynchronizationObjectFromGpu
title: D3DKMTWaitForSynchronizationObjectFromGpu function (d3dkmthk.h)
description: D3DKMTWaitForSynchronizationObjectFromGpu waits for a monitored fence to reach a certain value before processing subsequent context commands.
old-location: display\d3dkmtwaitforsynchronizationobjectfromgpu.htm
ms.assetid: 93705446-8B87-46DD-9CFE-DD0473DEE6B6
ms.date: 05/10/2018
keywords: ["D3DKMTWaitForSynchronizationObjectFromGpu function"]
ms.keywords: D3DKMTWaitForSynchronizationObjectFromGpu, D3DKMTWaitForSynchronizationObjectFromGpu function [Display Devices], d3dkmthk/D3DKMTWaitForSynchronizationObjectFromGpu, display.d3dkmtwaitforsynchronizationobjectfromgpu
f1_keywords:
 - "d3dkmthk/D3DKMTWaitForSynchronizationObjectFromGpu"
 - "D3DKMTWaitForSynchronizationObjectFromGpu"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
- API-MS-Win-DX-D3DKMT-L1-1-1.dll
- GDI32.dll
- API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
- D3DKMTWaitForSynchronizationObjectFromGpu
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTWaitForSynchronizationObjectFromGpu function

## -description

<b>D3DKMTWaitForSynchronizationObjectFromGpu</b> waits for a monitored fence to reach a certain value before processing subsequent context commands.
<div class="alert"><b>Note</b>  For Windows Display Driver Model (WDDM) v2 drivers, existing <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtwaitforsynchronizationobject">D3DKMTWaitForSynchronizationObject</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtwaitforsynchronizationobject2">D3DKMTWaitForSynchronizationObject2</a> callbacks are deprecated and will eventually be removed. </div><div> </div>

## -parameters

### -param D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_waitforsynchronizationobjectfromgpu">D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU</a> structure that describes the operation.

## -returns

Returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The operation was performed successfully.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|
 
This function might also return other <b>NTSTATUS</b> values.

## -remarks

This function semantics are similar to existing <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtwaitforsynchronizationobject2">D3DKMTWaitForSynchronizationObject2</a> call, except that this function also supports monitored fence objects and an array of monitored fence values to wait for.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtwaitforsynchronizationobject">D3DKMTWaitForSynchronizationObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtwaitforsynchronizationobject2">D3DKMTWaitForSynchronizationObject2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_waitforsynchronizationobjectfromgpu">D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU</a>
 

 

