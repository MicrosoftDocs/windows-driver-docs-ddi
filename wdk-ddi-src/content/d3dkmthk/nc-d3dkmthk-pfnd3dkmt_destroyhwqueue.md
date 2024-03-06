---
UID: NC:d3dkmthk.PFND3DKMT_DESTROYHWQUEUE
title: PFND3DKMT_DESTROYHWQUEUE (d3dkmthk.h)
description: Implemented by the client driver to destroy a hardware queue.
ms.date: 03/04/2022
keywords: ["PFND3DKMT_DESTROYHWQUEUE callback function"]
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
tech.root: display
f1_keywords:
 - PFND3DKMT_DESTROYHWQUEUE
 - d3dkmthk/PFND3DKMT_DESTROYHWQUEUE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmthk.h
api_name:
 - PFND3DKMT_DESTROYHWQUEUE
---

# PFND3DKMT_DESTROYHWQUEUE callback function

## -description

Implemented by the client driver to destroy a hardware queue.

## -syntax

```cpp
PFND3DKMT_DESTROYHWQUEUE PfnD3dkmtDestroyHwQueue;

NTSTATUS PfnD3dkmtDestroyHwQueue(
    CONST D3DKMT_DESTROYHWQUEUE *unnamedParam1
)
{...}
```

## -parameters

### -param unnamedParam1

Pointer to a [D3DKMT_DESTROYHWQUEUE](ns-d3dkmthk-_d3dkmt_destroyhwqueue.md) structure that contains the information needed to destroy a hardware queue.

## -returns

The method returns **STATUS_SUCCESS** if the operation succeeds. Otherwise, this method might return an appropriate **[NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values)** error code.

## -remarks

Register your implementation of this callback function by setting the appropriate member of [D3DKMT_DESTROYHWQUEUE](ns-d3dkmthk-_d3dkmt_destroyhwqueue.md) and then calling **PfnD3dkmtDestroyHwQueue**.
