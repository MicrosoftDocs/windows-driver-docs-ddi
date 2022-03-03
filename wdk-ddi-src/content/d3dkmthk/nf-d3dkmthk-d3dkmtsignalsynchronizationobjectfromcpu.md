---
UID: NF:d3dkmthk.D3DKMTSignalSynchronizationObjectFromCpu
title: D3DKMTSignalSynchronizationObjectFromCpu function (d3dkmthk.h)
description: D3DKMTSignalSynchronizationObjectFromCpu enables a driver to signal a monitored fence.
old-location: display\d3dkmtsignalsynchronizationobjectfromcpu.htm
ms.date: 03/02/2022
keywords: ["D3DKMTSignalSynchronizationObjectFromCpu function"]
ms.keywords: D3DKMTSignalSynchronizationObjectFromCpu, D3DKMTSignalSynchronizationObjectFromCpu function [Display Devices], d3dkmthk/D3DKMTSignalSynchronizationObjectFromCpu, display.d3dkmtsignalsynchronizationobjectfromcpu
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
 - D3DKMTSignalSynchronizationObjectFromCpu
 - d3dkmthk/D3DKMTSignalSynchronizationObjectFromCpu
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
 - D3DKMTSignalSynchronizationObjectFromCpu
---

# D3DKMTSignalSynchronizationObjectFromCpu function

## -description

**D3DKMTSignalSynchronizationObjectFromCpu** enables a driver to signal a monitored fence.

## -parameters

### -param unnamedParam1 [in]

A pointer to a [D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU](ns-d3dkmthk-_d3dkmt_signalsynchronizationobjectfromcpu.md) structure that provides the details of the requested operation..

## -returns

**D3DKMTSignalSynchronizationObjectFromCpu** returns one of the following values:

| Return code | Description |
|--|--|
| STATUS_SUCCESS | The operation was successful. |

This function might also return other **NTSTATUS** values.

## -remarks

When a monitored fence object is signaled by the CPU, the graphics kernel will update the fence memory location with the signaled value, so it becomes immediately visible to any user mode reader as well as immediately un-wait any satisfied waiters. However, the caller cannot assume that the signal operation will be completed upon the return from this function. Instead, the caller should use appropriate wait functions to check for signal completion.

> [!NOTE]
> A signal from a graphics processing unit (GPU) call is not provided. Instead, a driver can signal a new fence value by inserting a GPU write command for **FenceValueGPUVirtualAddress** into a command buffer.

## -see-also

[D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMCPU](ns-d3dkmthk-_d3dkmt_signalsynchronizationobjectfromcpu.md)
