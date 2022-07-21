---
UID: NF:d3dkmthk.D3DKMTWaitForSynchronizationObjectFromCpu
title: D3DKMTWaitForSynchronizationObjectFromCpu function (d3dkmthk.h)
description: D3DKMTWaitForSynchronizationObjectFromCpu waits for a monitored fence to reach a certain value.
old-location: display\d3dkmtwaitforsynchronizationobjectfromcpu.htm
ms.date: 03/02/2022
keywords: ["D3DKMTWaitForSynchronizationObjectFromCpu function"]
ms.keywords: D3DKMTWaitForSynchronizationObjectFromCpu, D3DKMTWaitForSynchronizationObjectFromCpu function [Display Devices], d3dkmthk/D3DKMTWaitForSynchronizationObjectFromCpu, display.d3dkmtwaitforsynchronizationobjectfromcpu
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
 - D3DKMTWaitForSynchronizationObjectFromCpu
 - d3dkmthk/D3DKMTWaitForSynchronizationObjectFromCpu
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
 - D3DKMTWaitForSynchronizationObjectFromCpu
---

# D3DKMTWaitForSynchronizationObjectFromCpu function

## -description

**D3DKMTWaitForSynchronizationObjectFromCpu** waits for a monitored fence to reach a certain value.

## -parameters

### -param unnamedParam1 [in]

A pointer to a [D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU](ns-d3dkmthk-_d3dkmt_waitforsynchronizationobjectfromcpu.md) structure that describes the operation.

## -returns

Returns one of the following values:

| Return code | Description |
|--|--|
| STATUS_SUCCESS | The operation was performed successfully. |
| STATUS_INVALID_PARAMETER | Parameters were validated and determined to be incorrect. |

This function might also return other **NTSTATUS** values.

## -see-also

[D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMCPU](ns-d3dkmthk-_d3dkmt_waitforsynchronizationobjectfromcpu.md)
