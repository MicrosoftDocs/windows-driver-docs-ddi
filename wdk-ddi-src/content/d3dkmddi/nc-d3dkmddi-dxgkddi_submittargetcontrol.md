---
UID: NC:d3dkmddi.DXGKDDI_SUBMITTARGETCONTROL
title: DXGKDDI_SUBMITTARGETCONTROL
author: windows-driver-content
description: Allows the OS to request control operations to be performed on a target using a control interface to the target owned by the graphics adapter.
tech.root: display
ms.assetid: 5a5bdf05-0a89-48d7-a659-ded08982861f
ms.author: windowsdriverdev
ms.date: 04/04/2019
f1_keywords:
 - "d3dkmddi/DXGKDDI_SUBMITTARGETCONTROL"
req.header: d3dkmddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1903
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
 - DXGKDDI_SUBMITTARGETCONTROL
product:
- Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: WDDM 2.6, 19H1
---

# DXGKDDI_SUBMITTARGETCONTROL callback function

## -description

Allows the OS to request control operations to be performed on a target using a control interface to the target owned by the graphics adapter.

## -prototype

```
//Declaration

DXGKDDI_SUBMITTARGETCONTROL DxgkddiSubmittargetcontrol; 

// Definition

NTSTATUS DxgkddiSubmittargetcontrol 
(
	IN_CONST_HANDLE hAdapter
	IN_OUT_PDXGKARG_SUBMITTARGETCONTROL pSubmitTargetControl
)
{...}

```

## -parameters

### -param hAdapter

[in] WDDM display miniport adapter handle.

### -param pSubmitTargetControl

[in, out] Pointer to a [DXGKARG_SUBMITTARGETCONTROL](ns-d3dkmddi-dxgkarg_submittargetcontrol.md) structure.

## -returns

Return STATUS_SUCCESS if the operation succeeds. 

## -remarks


## -see-also
