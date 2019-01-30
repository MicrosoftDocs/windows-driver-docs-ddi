---
UID: NC:dispmprt.DXGKCB_REPORT_DIAGNOSTIC
title: DXGKCB_REPORT_DIAGNOSTIC (dispmprt.h)
description: Implemented by the kernel mode driver to report diagnostic logging.
ms.assetid: 1c38189b-daaf-4d55-826a-5e868a0e1190
ms.date: 10/19/2018
ms.topic: callback
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
topic_type:
-	apiref
api_type:
-	UserDefined
api_location:
-	dispmprt.h
api_name:
-	DXGKCB_REPORT_DIAGNOSTIC
product: 
- Windows
targetos: Windows
tech.root: display
---

# DXGKCB_REPORT_DIAGNOSTIC callback function

## -description

Implemented by the kernel mode driver to report diagnostic logging.

## -prototype

```cpp
//Declaration

DXGKCB_REPORT_DIAGNOSTIC DxgkcbReportDiagnostic;

// Definition

_IRQL_requires_same_ DxgkcbReportDiagnostic
(
	HANDLE DeviceHandle
	IN_PDXGK_DIAGNOSTIC_HEADER pDiagnostic
)
{...}

DXGKCB_REPORT_DIAGNOSTIC


```

## -parameters

### -param DeviceHandle

A handle to a display device adapter.

### -param pDiagnostic

Pointer to a [_DXGK_DIAGNOSTIC_HEADER](C:\drivers\wdk-ddi\wdk-ddi-src\content\dispmprt\ns-dispmprt-_dxgk_diagnostic_header.md) structure that contains the diagnostic event report.

## -returns

Returns the following values:

| Value | Description |
| -- | -- |
| STATUS_SUCCESS| The diagnostic event is recorded successfully by the OS.|
| STATUS_INVALID_PARAMETER| The adapter handle is incorrect or the event type is not recognized. |
| STATUS_BUFFER_TOO_SMALL | the event size is too small for the type. |
| STATUS_UNSUCCESSFUL | The OS was unable to process a valid event.|

Other return codes may be returned as appropriate.
