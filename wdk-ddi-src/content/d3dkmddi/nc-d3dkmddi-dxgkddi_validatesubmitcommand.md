---
UID: NC:d3dkmddi.DXGKDDI_VALIDATESUBMITCOMMAND
title: DXGKDDI_VALIDATESUBMITCOMMAND (d3dkmddi.h)
description: Validates private driver data, which is passed by user mode driver in D3DKMTSubmitCommand or D3DKMTSubmitCommandToHwQueue.
ms.assetid: bc83b8eb-da96-49f3-8462-1cd0838ba03d
ms.date: 10/19/2018
ms.topic: callback
req.header: d3dkmddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- UserDefined
api_location: 
- d3dkmddi.h
api_name: 
- DXGKDDI_VALIDATESUBMITCOMMAND
product:
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# DXGKDDI_VALIDATESUBMITCOMMAND callback function

## -description

Validates private driver data, which is passed by user mode driver in [D3DKMTSubmitCommand](nc-d3dkmddi-dxgkddi_submitcommand.md) or [D3DKMTSubmitCommandToHwQueue](../d3dkmthk/nf-d3dkmthk-d3dkmtsubmitcommandtohwqueue.md).

## -prototype

```cpp
//Declaration

DXGKDDI_VALIDATESUBMITCOMMAND DxgkddiValidatesubmitcommand; 

// Definition

NTSTATUS DxgkddiValidatesubmitcommand 
(
	IN_CONST_HANDLE hContext
	INOUT_PDXGKARG_VALIDATESUBMITCOMMAND pArgs
)
{...}

```

## -parameters

### -param hContext

Driver context handle for the context.

### -param pArgs

Pointer to a [DXGKARG_VALIDATESUBMITCOMMAND](ns-d3dkmddi-_dxgkarg_validatesubmitcommand.md) structure.

## -returns

Returns NTSTATUS:

* STATUS_SUCCESS
* STATUS_INVALID_USER_BUFFER

## -remarks

When this callback is implemented, private data, passed in [DxgkDdiSubmitCommandVirtual](nc-d3dkmddi-dxgkddi_submitcommandvirtual.md) or [DxgkDdiSubmitCommandToHwQueue](nc-d3dkmddi-dxgkddi_submitcommandtohwqueue.md) is always validated by kernel mode driver.

This callback is called only when private driver size in [D3DKMTSubmitCommand](nc-d3dkmddi-dxgkddi_submitcommand.md) is not zero. It is called once per D3DKMTSubmitCommand or D3DKMTSubmitCommandToHwQueue.

The kernel mode driver should not assume that this callback is called in the context of the process, which called D3DKMTSubmitCommand. So, the driver should not pass any user mode pointers or handles in private data.

This callback is called before the command is submitted to the GPU scheduler software queue.



## -see-also
