---
UID: NC:d3dkmddi.DXGKDDI_SWITCHTOHWCONTEXTLIST
title: DXGKDDI_SWITCHTOHWCONTEXTLIST (d3dkmddi.h)
description: Clarifies the order of execution of first and second contexts submitted.
ms.assetid: 37f7d107-50ec-452e-b98f-a1bea73ab2d0
ms.date: 10/19/2018
ms.topic: callback
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
topic_type: 
-	apiref
api_type: 
-	UserDefined
api_location: 
-	d3dkmddi.h
api_name: 
-	DXGKDDI_SWITCHTOHWCONTEXTLIST
product:
-	Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# DXGKDDI_SWITCHTOHWCONTEXTLIST callback function

## -description

Clarifies the order of execution of first and second contexts submitted.

## -prototype

```cpp
//Declaration

DXGKDDI_SWITCHTOHWCONTEXTLIST DxgkddiSwitchtohwcontextlist; 

// Definition

NTSTATUS DxgkddiSwitchtohwcontextlist 
(
	IN_CONST_HANDLE hAdapter
	IN_CONST_PDXGKARG_SWITCHTOHWCONTEXTLIST pHwContextList
)
{...}

```

## -parameters

### -param hAdapter

A handle to the hardware adapter.

### -param pHwContextList: 

Pointer to the [DXGKARG_SWITCHTOHWCONTEXTLIST](ns-d3dkmddi-_dxgkarg_switchtohwcontextlist.md) structure that represents the hardware context list.

## -returns

Returns NTSTATUS.


