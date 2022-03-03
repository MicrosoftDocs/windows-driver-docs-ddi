---
UID: NF:d3dkmthk.D3DKMTWaitForSynchronizationObjectFromGpu
title: D3DKMTWaitForSynchronizationObjectFromGpu function (d3dkmthk.h)
description: D3DKMTWaitForSynchronizationObjectFromGpu waits for a monitored fence to reach a certain value before processing subsequent context commands.
old-location: display\d3dkmtwaitforsynchronizationobjectfromgpu.htm
ms.date: 03/02/2022
keywords: ["D3DKMTWaitForSynchronizationObjectFromGpu function"]
ms.keywords: D3DKMTWaitForSynchronizationObjectFromGpu, D3DKMTWaitForSynchronizationObjectFromGpu function [Display Devices], d3dkmthk/D3DKMTWaitForSynchronizationObjectFromGpu, display.d3dkmtwaitforsynchronizationobjectfromgpu
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
 - D3DKMTWaitForSynchronizationObjectFromGpu
 - d3dkmthk/D3DKMTWaitForSynchronizationObjectFromGpu
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
---

# D3DKMTWaitForSynchronizationObjectFromGpu function

## -description

**D3DKMTWaitForSynchronizationObjectFromGpu** waits for a monitored fence to reach a certain value before processing subsequent context commands.

> [!NOTE]
> For Windows Display Driver Model (WDDM) v2 drivers, existing [D3DKMTWaitForSynchronizationObject](nf-d3dkmthk-d3dkmtwaitforsynchronizationobject.md) and [D3DKMTWaitForSynchronizationObject2](nf-d3dkmthk-d3dkmtwaitforsynchronizationobject2.md) callbacks are deprecated and will eventually be removed.

## -parameters

### -param unnamedParam1 [in]

A pointer to a [D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU](ns-d3dkmthk-_d3dkmt_waitforsynchronizationobjectfromgpu.md) structure that describes the operation.

## -returns

Returns one of the following values:

| Return code | Description |
|--|--|
| STATUS_SUCCESS | The operation was performed successfully. |
| STATUS_INVALID_PARAMETER | Parameters were validated and determined to be incorrect. |

This function might also return other **NTSTATUS** values.

## -remarks

This function semantics are similar to existing [D3DKMTWaitForSynchronizationObject2](nf-d3dkmthk-d3dkmtwaitforsynchronizationobject2.md) call, except that this function also supports monitored fence objects and an array of monitored fence values to wait for.

## -see-also

[D3DKMTWaitForSynchronizationObject](nf-d3dkmthk-d3dkmtwaitforsynchronizationobject.md)

[D3DKMTWaitForSynchronizationObject2](nf-d3dkmthk-d3dkmtwaitforsynchronizationobject2.md)

[D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU](ns-d3dkmthk-_d3dkmt_waitforsynchronizationobjectfromgpu.md)
