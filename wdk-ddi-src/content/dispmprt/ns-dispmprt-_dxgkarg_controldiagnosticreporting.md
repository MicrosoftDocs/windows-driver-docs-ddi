---
UID: NS:dispmprt._DXGKARG_CONTROLDIAGNOSTICREPORTING
title: _DXGKARG_CONTROLDIAGNOSTICREPORTING (dispmprt.h)
description: Contains arguments for the call to DxgkDdiControlDiagnosticReporting.
ms.date: 10/19/2018
keywords: ["DXGKARG_CONTROLDIAGNOSTICREPORTING structure"]
ms.keywords: _DXGKARG_CONTROLDIAGNOSTICREPORTING, *PDXGKARG_CONTROLDIAGNOSTICREPORTING, DXGKARG_CONTROLDIAGNOSTICREPORTING,
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
req.typenames: DXGKARG_CONTROLDIAGNOSTICREPORTING, *PDXGKARG_CONTROLDIAGNOSTICREPORTING
targetos: Windows
tech.root: display
f1_keywords:
 - _DXGKARG_CONTROLDIAGNOSTICREPORTING
 - dispmprt/_DXGKARG_CONTROLDIAGNOSTICREPORTING
 - PDXGKARG_CONTROLDIAGNOSTICREPORTING
 - dispmprt/PDXGKARG_CONTROLDIAGNOSTICREPORTING
 - DXGKARG_CONTROLDIAGNOSTICREPORTING
 - dispmprt/DXGKARG_CONTROLDIAGNOSTICREPORTING
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGKARG_CONTROLDIAGNOSTICREPORTING
product:
 - Windows
---

# _DXGKARG_CONTROLDIAGNOSTICREPORTING structure


## -description

Contains arguments for the call to [DxgkDdiControlDiagnosticReporting](nc-dispmprt-dxgkddi_controldiagnosticreporting.md).

## -struct-fields

### -field DiagnosticCategory

[in] A [DXGK_DIAGNOSTIC_CATEGORIES](ns-dispmprt-_dxgk_diagnostic_categories.md) structure which indicates which one of the diagnostic categories the diagnostic types being requested belong to.

### -field RequestedDiagnostics

[out] A [DXGK_DIAGNOSTIC_TYPES](ns-dispmprt-_dxgk_diagnostic_types.md) structure indicates which diagnostic types the driver is being requested to enable in the given category.  The driver should enable each diagnostic which is requested and disable each diagnostic which is not requested.

