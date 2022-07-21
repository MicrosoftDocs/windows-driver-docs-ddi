---
UID: NC:d3dkmthk.PFND3DKMT_GETPROCESSSCHEDULINGPRIORITYCLASS
title: PFND3DKMT_GETPROCESSSCHEDULINGPRIORITYCLASS (d3dkmthk.h)
description: Pfnd3dkmtGetprocessschedulingpriorityclass retrieves the scheduling priority for a process.
ms.date: 03/04/2022
keywords: ["PFND3DKMT_GETPROCESSSCHEDULINGPRIORITYCLASS callback function"]
req.header: d3dkmthk.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - PFND3DKMT_GETPROCESSSCHEDULINGPRIORITYCLASS
 - d3dkmthk/PFND3DKMT_GETPROCESSSCHEDULINGPRIORITYCLASS
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_GETPROCESSSCHEDULINGPRIORITYCLASS
dev_langs:
 - c++
---

# PFND3DKMT_GETPROCESSSCHEDULINGPRIORITYCLASS callback function

## -description

**PfnD3dkmtGetProcessSchedulingPriorityClass** retrieves the scheduling priority for a process.

## -syntax

```cpp
PFND3DKMT_GETPROCESSSCHEDULINGPRIORITYCLASS PfnD3dkmtGetProcessSchedulingPriorityClass;

NTSTATUS PfnD3dkmtGetProcessSchedulingPriorityClass(
    HANDLE unnamedParam1
    D3DKMT_SCHEDULINGPRIORITYCLASS *unnamedParam2
)
{...}

```

## -parameters

### -param unnamedParam1

A handle to a display device.

### -param unnamedParam2

Pointer to a [D3DKMT_SCHEDULINGPRIORITYCLASS](ne-d3dkmthk-_d3dkmt_schedulingpriorityclass.md) enum value representing the scheduling priority class.

## -returns

The method returns **STATUS_SUCCESS** if the operation succeeds. Otherwise, this method might return an appropriate **[NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values)** error code.

## -remarks

## -see-also
