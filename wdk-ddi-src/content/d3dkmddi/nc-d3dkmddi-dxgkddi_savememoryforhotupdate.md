---
UID: NC:d3dkmddi.DXGKDDI_SAVEMEMORYFORHOTUPDATE
title: DXGKDDI_SAVEMEMORYFORHOTUPDATE
description: Before the driver is unloaded, it must call the DXGKDDI_SAVEMEMORYFORHOTUPDATE callback function to save information.
tech.root: display
ms.date: 04/04/2019
keywords: ["DXGKDDI_SAVEMEMORYFORHOTUPDATE callback function"]
req.header: d3dkmddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - DXGKDDI_SAVEMEMORYFORHOTUPDATE
 - d3dkmddi/DXGKDDI_SAVEMEMORYFORHOTUPDATE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_SAVEMEMORYFORHOTUPDATE
dev_langs:
 - c++
---

# DXGKDDI_SAVEMEMORYFORHOTUPDATE callback function


## -description

Before the driver is unloaded, it must call the DXGKDDI_SAVEMEMORYFORHOTUPDATE callback function to save information. This information is required to continue running virtual GPUs after the driver is started again.

## -parameters

### -param hContext

[in] A handle to the miniport context that is returned by the driver in DXGKDDI_DRIVERHOTUPDATE_INTERFACE.

### -param pArgs

[in] A pointer to a [PDXGKARG_SAVEMEMORYFORHOTUPDATE](ns-d3dkmddi-dxgkarg_savememoryforhotupdate.md) structure.

## -returns

Return STATUS_SUCCESS if the operation succeeds.

## -prototype

```
//Declaration

DXGKDDI_SAVEMEMORYFORHOTUPDATE DxgkddiSavememoryforhotupdate; 

// Definition

NTSTATUS DxgkddiSavememoryforhotupdate 
(
	IN_CONST_HANDLE hContext
	IN_CONST_PDXGKARG_SAVEMEMORYFORHOTUPDATE pArgs
)
{...}

```

## -remarks

This callback supports driver hot update. Before the driver is unloaded, it is called to save information, which is required to continue running virtual GPUs after it is started again. The driver needs to have the state of every active virtual GPU (virtual function). In the context of a **DxgkDdiSaveMemoryForHotUpdate** call, the driver could call [DxgkCbSaveMemoryForHotUpdate](nc-d3dkmddi-dxgkcb_savememoryforhotupdate.md) multiple times to save information about running virtual GPUs and other adapter information needed to restore the virtual GPU state after the device is started again.

## -see-also

