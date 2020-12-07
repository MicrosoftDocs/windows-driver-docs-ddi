---
UID: NC:dispmprt.DXGKDDI_QUERYDIAGNOSTICTYPESSUPPORT
title: DXGKDDI_QUERYDIAGNOSTICTYPESSUPPORT (dispmprt.h)
description: The OS calls the DXGKDDI_QUERYDIAGNOSTICTYPESSUPPORT callback function to discover what types of diagnostic the driver supports for the passed diagnostic category.
ms.date: 10/19/2018
keywords: ["DXGKDDI_QUERYDIAGNOSTICTYPESSUPPORT callback function"]
req.header: dispmprt.h
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
 - DXGKDDI_QUERYDIAGNOSTICTYPESSUPPORT
 - dispmprt/DXGKDDI_QUERYDIAGNOSTICTYPESSUPPORT
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - dispmprt.h
api_name:
 - DXGKDDI_QUERYDIAGNOSTICTYPESSUPPORT
product:
 - Windows
---

# DXGKDDI_QUERYDIAGNOSTICTYPESSUPPORT callback function


## -description

The OS calls the DXGKDDI_QUERYDIAGNOSTICTYPESSUPPORT callback function to discover what types of diagnostic the driver supports for the passed diagnostic category.

## -parameters

### -param MiniportDeviceContext

A handle to a context block associated with a display adapter.

### -param pArgQueryDiagnosticTypesSupport

Pointer to a [DXGKARG_QUERYDIAGNOSTICTYPESSUPPORT](ns-dispmprt-_dxgkarg_querydiagnostictypessupport.md) structure.

## -returns

Returns NTSTATUS.

## -prototype

```cpp
//Declaration

DXGKDDI_QUERYDIAGNOSTICTYPESSUPPORT DxgkddiQuerydiagnostictypessupport; 

// Definition

NTSTATUS DxgkddiQuerydiagnostictypessupport 
(
	IN_CONST_PVOID MiniportDeviceContext
	INOUT_PDXGKARG_QUERYDIAGNOSTICTYPESSUPPORT pArgQueryDiagnosticTypesSupport
)
{...}

DXGKDDI_QUERYDIAGNOSTICTYPESSUPPORT *PDXGKDDI_QUERYDIAGNOSTICTYPESSUPPORT


```

## -remarks

## -see-also

