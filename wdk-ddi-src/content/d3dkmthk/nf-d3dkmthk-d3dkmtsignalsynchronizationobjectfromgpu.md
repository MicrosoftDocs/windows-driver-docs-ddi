---
UID: NF:d3dkmthk.D3DKMTSignalSynchronizationObjectFromGpu
title: D3DKMTSignalSynchronizationObjectFromGpu function (d3dkmthk.h)
description: D3DKMTSignalSynchronizationObjectFromGpu is used to signal a monitored fence.
old-location: display\d3dkmtsignalsynchronizationobjectfromgpu.htm
ms.date: 03/02/2022
keywords: ["D3DKMTSignalSynchronizationObjectFromGpu function"]
ms.keywords: D3DKMTSignalSynchronizationObjectFromGpu, D3DKMTSignalSynchronizationObjectFromGpu function [Display Devices], d3dkmthk/D3DKMTSignalSynchronizationObjectFromGpu, display.d3dkmtsignalsynchronizationobjectfromgpu
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
 - D3DKMTSignalSynchronizationObjectFromGpu
 - d3dkmthk/D3DKMTSignalSynchronizationObjectFromGpu
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
 - D3DKMTSignalSynchronizationObjectFromGpu
---

# D3DKMTSignalSynchronizationObjectFromGpu function

## -description

**D3DKMTSignalSynchronizationObjectFromGpu** is used to signal a monitored fence. When a particular graphics processing unit (GPU) engine is not capable of writing a new monitored fence value directly using its GPU virtual address, the driver needs to flush its command buffer and issue a signal from GPU packet using [D3DKMTSignalSynchronizationObjectFromGpu2](nf-d3dkmthk-d3dkmtsignalsynchronizationobjectfromgpu2.md). For Windows Display Driver Model (WDDM) v2 drivers, existing [D3DKMTSignalSynchronizationObject](nf-d3dkmthk-d3dkmtsignalsynchronizationobject.md) and [D3DKMTSignalSynchronizationObject2](nf-d3dkmthk-d3dkmtsignalsynchronizationobject2.md) callbacks are deprecated and will eventually be removed.

## -parameters

### -param unnamedParam1 [in]

A [D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU](ns-d3dkmthk-_d3dkmt_signalsynchronizationobjectfromgpu.md) structure that provides the details of the requested operation.

## -returns

Returns one of the following values:

| Return code | Description |
|--|--|
| STATUS_SUCCESS | The operation was performed successfully. |
| STATUS_INVALID_PARAMETER | Parameters were validated and determined to be incorrect. |

This function might also return other **NTSTATUS** values.

## -see-also

[D3DKMTSignalSynchronizationObject](nf-d3dkmthk-d3dkmtsignalsynchronizationobject.md)

[D3DKMTSignalSynchronizationObject2](nf-d3dkmthk-d3dkmtsignalsynchronizationobject2.md)

[D3DKMTSignalSynchronizationObjectFromGpu2](nf-d3dkmthk-d3dkmtsignalsynchronizationobjectfromgpu2.md)

[D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU](ns-d3dkmthk-_d3dkmt_signalsynchronizationobjectfromgpu.md)
