---
UID: NC:d3dkmddi.DXGKDDI_RESUMEHWENGINE
title: DXGKDDI_RESUMEHWENGINE (d3dkmddi.h)
description: Instructs the GPU scheduler to re-submit contexts that were not invalidated by the reset.
ms.assetid: 9dfb8a10-6ee2-4263-ba0c-b246736973bb
ms.date: 10/19/2018
keywords: ["DXGKDDI_RESUMEHWENGINE callback function"]
req.header: d3dkmddi.h
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
ms.custom: RS5
f1_keywords:
 - "d3dkmddi/DXGKDDI_RESUMEHWENGINE"
 - "DXGKDDI_RESUMEHWENGINE"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_RESUMEHWENGINE
product:
 - Windows
dev_langs:
 - c++
---

# DXGKDDI_RESUMEHWENGINE callback function

## -description

Instructs the GPU scheduler to re-submit contexts that were not invalidated by the reset. DxgkDdiResumeHwEngine is invoked by the DXG kernel after a GPU engine has been successfully reset.

## -parameters

### -param hAdapter

The logical adapter for which a new focus Present has completed.

### -param pResumeHwEngine

Pointer to a [DXGKARG_RESUMEHWENGINE](ns-d3dkmddi-_dxgkarg_resumehwengine.md) structure that contains information to resume the hardware engine.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. If the call fails, the OS will perform a full GPU reset.

## -prototype

```cpp
//Declaration

DXGKDDI_RESUMEHWENGINE DxgkddiResumehwengine;

// Definition

NTSTATUS DxgkddiResumehwengine
(
	IN_CONST_HANDLE hAdapter
	INOUT_PDXGKARG_RESUMEHWENGINE pResumeHwEngine
)
{...}

DXGKDDI_RESUMEHWENGINE *PDXGKDDI_RESUMEHWENGINE


```

## -remarks

Register your implementation of this callback function by setting the appropriate member of DXGKARG_RESUMEHWENGINE and then calling DxgkDdiResumeHwEngine.

DxgkDdiResetHwEngine implementation should inform the OS of all running contexts that were affected by the GPU engine reset operation via DxgkCbInvalidateHwContext callback. These context devices will be set in error and future submissions will not be performed.

After DxgkDdiResetHwEngine is called, the engine is not considered resumed yet, and contexts that were not invalidated are not allowed to be submitted. The OS needs to re-enable interrupts from this engine and synchronize its state with the reset GPU engine. After that, the OS will enable interrupts and call DxgkDdiResumeHwEngine, which instructs the GPU engine to start scheduling all runnable contexts that were not affected by the engine reset.

## -see-also

