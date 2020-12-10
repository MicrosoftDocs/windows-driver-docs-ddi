---
UID: NF:d3dkmthk.D3DKMTSignalSynchronizationObjectFromGpu2
title: D3DKMTSignalSynchronizationObjectFromGpu2 function (d3dkmthk.h)
description: D3DKMTSignalSynchronizationObjectFromGpu2 is used to signal a monitored fence.
old-location: display\d3dkmtsignalsynchronizationobjectfromgpu2.htm
ms.date: 05/10/2018
keywords: ["D3DKMTSignalSynchronizationObjectFromGpu2 function"]
ms.keywords: D3DKMTSignalSynchronizationObjectFromGpu2, D3DKMTSignalSynchronizationObjectFromGpu2 function [Display Devices], d3dkmthk/D3DKMTSignalSynchronizationObjectFromGpu2, display.d3dkmtsignalsynchronizationobjectfromgpu2
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - D3DKMTSignalSynchronizationObjectFromGpu2
 - d3dkmthk/D3DKMTSignalSynchronizationObjectFromGpu2
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
 - D3DKMTSignalSynchronizationObjectFromGpu2
---

# D3DKMTSignalSynchronizationObjectFromGpu2 function


## -description

<b>D3DKMTSignalSynchronizationObjectFromGpu2</b> is used to signal a monitored fence.When a particular graphics processing unit (GPU) engine is not capable of writing a new monitored fence value directly using its GPU virtual address, the driver needs to flush its command buffer and issue a signal from GPU packet using <b>D3DKMTSignalSynchronizationObjectFromGpu2</b>. For Windows Display Driver Model (WDDM) v2 drivers, existing <a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtsignalsynchronizationobject">D3DKMTSignalSynchronizationObject</a> and <a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtsignalsynchronizationobject2">D3DKMTSignalSynchronizationObject2</a> callbacks are deprecated and will eventually be removed.

## -parameters

### -param D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2

*pData* [in]

A <a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_signalsynchronizationobjectfromgpu2">D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2</a> structure that provides the details of the requested operation.

## -returns

Returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The operation was performed successfully.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|

This function might also return other <b>NTSTATUS</b> values.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtsignalsynchronizationobject">D3DKMTSignalSynchronizationObject</a>



<a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtsignalsynchronizationobject2">D3DKMTSignalSynchronizationObject2</a>



<a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtsignalsynchronizationobjectfromgpu">D3DKMTSignalSynchronizationObjectFromGpu</a>



<a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_signalsynchronizationobjectfromgpu2">D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2</a>
