---
UID: NS:dispmprt._DXGKARG_QUERYDIAGNOSTICTYPESSUPPORT
title: _DXGKARG_QUERYDIAGNOSTICTYPESSUPPORT (dispmprt.h)
description: Arguments for the DxgkddiQueryDiagnosticTypesSupport callback function.
ms.assetid: 05382c90-2195-4352-b12a-b9fcaec51033
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: _DXGKARG_QUERYDIAGNOSTICTYPESSUPPORT, *PDXGKARG_QUERYDIAGNOSTICTYPESSUPPORT, DXGKARG_QUERYDIAGNOSTICTYPESSUPPORT,
req.header: dispmprt.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: DXGKARG_QUERYDIAGNOSTICTYPESSUPPORT, *PDXGKARG_QUERYDIAGNOSTICTYPESSUPPORT
topic_type:
- apiref
api_type:
- HeaderDef
api_location:
- dispmprt.h
api_name:
- _DXGKARG_QUERYDIAGNOSTICTYPESSUPPORT
product: 
- Windows
targetos: Windows
tech.root: display
---

# _DXGKARG_QUERYDIAGNOSTICTYPESSUPPORT structure

## -description

Arguments for the [DxgkddiQueryDiagnosticTypesSupport](nc-dispmprt-dxgkddi_querydiagnostictypessupport.md) callback function.

## -struct-fields

### -field DiagnosticCategory

[in] A [DXGK_DIAGNOSTIC_CATEGORIES](ns-dispmprt-_dxgk_diagnostic_categories.md) structure that indicates which one of the diagnostic categories the supported types are being queried for.

### -field NoninvasiveTypes

[out] A [DXGK_DIAGNOSTIC_TYPES](ns-dispmprt-_dxgk_diagnostic_types.md) structure that indicates driver support for diagnostics, which can be achieved without significant overhead or impact on the system. Noninvasive diagnostics should be sufficiently benign that they may be enabled by the OS to proactively gather telemetry.

### -field InvasiveTypes

[out] A [DXGK_DIAGNOSTIC_TYPES](ns-dispmprt-_dxgk_diagnostic_types.md) structure that indicates driver support for diagnostics, which the driver supports but may require significant overhead or have significant impact on the system. Invasive diagnostics will only be enabled when required to gather information for specific investigations and are expected to have power and/or performance drawbacks making them unsuitable for automated usage.

