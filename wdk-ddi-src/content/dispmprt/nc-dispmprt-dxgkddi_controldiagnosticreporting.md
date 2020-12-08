---
UID: NC:dispmprt.DXGKDDI_CONTROLDIAGNOSTICREPORTING
title: DXGKDDI_CONTROLDIAGNOSTICREPORTING (dispmprt.h)
description: The OS calls DxgkddiControlDiagnosticReporting to apply the set of diagnostics which should be enabled for a diagnostic category.
ms.date: 10/19/2018
keywords: ["DXGKDDI_CONTROLDIAGNOSTICREPORTING callback function"]
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
 - DXGKDDI_CONTROLDIAGNOSTICREPORTING
 - dispmprt/DXGKDDI_CONTROLDIAGNOSTICREPORTING
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - dispmprt.h
api_name:
 - DXGKDDI_CONTROLDIAGNOSTICREPORTING
product:
 - Windows
---

# DXGKDDI_CONTROLDIAGNOSTICREPORTING callback function


## -description

The OS calls DxgkddiControlDiagnosticReporting to apply the set of diagnostics which should be enabled for a diagnostic category. Any diagnostics which are not included in the set should be disabled.

## -parameters

### -param MiniportDeviceContext

Identifies the adapter.

### -param pArgControlDiagnosticReporting

A pointer to a [DXGKARG_QUERYDIAGNOSTICTYPESSUPPORT](ns-dispmprt-_dxgkarg_querydiagnostictypessupport.md) structure that indicates the category of diagnostic being queried and provides space for the driver to describe the diagnostic support it has.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, returns an appropriate NTSTATUS Values error code defined in Ntstatus.h.

## -prototype

```cpp
//Declaration

DXGKDDI_CONTROLDIAGNOSTICREPORTING DxgkddiControldiagnosticreporting;

// Definition

NTSTATUS DxgkddiControldiagnosticreporting
(
	IN_CONST_PVOID MiniportDeviceContext
	IN_PDXGKARG_CONTROLDIAGNOSTICREPORTING pArgControlDiagnosticReporting
)
{...}

DXGKDDI_CONTROLDIAGNOSTICREPORTING *PDXGKDDI_CONTROLDIAGNOSTICREPORTING


```

## -remarks

This function is always called at PASSIVE level so the supporting code should be made pageable.

## -see-also

[DXGKARG_QUERYDIAGNOSTICTYPESSUPPORT structure](ns-dispmprt-_dxgkarg_querydiagnostictypessupport.md)

