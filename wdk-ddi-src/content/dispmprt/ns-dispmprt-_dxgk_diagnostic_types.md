---
UID: NS:dispmprt._DXGK_DIAGNOSTIC_TYPES
title: _DXGK_DIAGNOSTIC_TYPES (dispmprt.h)
description: A structure that contains a union of all the defined sets of diagnostic types.
ms.assetid: 9373b413-20a5-4bee-a619-b71c0258124d
ms.date: 10/19/2018
keywords: ["DXGK_DIAGNOSTIC_TYPES structure"]
ms.keywords: _DXGK_DIAGNOSTIC_TYPES, DXGK_DIAGNOSTIC_TYPES,
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
req.typenames: DXGK_DIAGNOSTIC_TYPES
targetos: Windows
tech.root: display
f1_keywords:
 - _DXGK_DIAGNOSTIC_TYPES
 - dispmprt/_DXGK_DIAGNOSTIC_TYPES
 - DXGK_DIAGNOSTIC_TYPES
 - dispmprt/DXGK_DIAGNOSTIC_TYPES
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGK_DIAGNOSTIC_TYPES
product:
 - Windows
---

# _DXGK_DIAGNOSTIC_TYPES structure


## -description

A structure that contains a union of all the defined sets of diagnostic types. The member of the union which should be used to interpret this data is determined by the bit-field which is set in the associated [DXGK_DIAGNOSTIC_CATEGORIES](ns-dispmprt-_dxgk_diagnostic_categories.md) structure.  In general, there will be one set of diagnostic types for each diagnostic category.

## -struct-fields

### -field Notifications

A [DXGK_DIAGTYPE_NOTIFICATIONS](ns-dispmprt-_dxgk_diagtype_notifications.md) structure for indicating what kind of diagnostics are being described.

### -field Progressions

A [DXGK_DIAGTYPE_PROGRESSIONS](../dispmprt/ns-dispmprt-_dxgk_diagtype_progressions.md) structure for indicating a Progressions diagnostic type.

### -field Value

Value of the diagnostic type.

## -remarks

The DXGK_DIAGNOSTIC_TYPES structure is used to identify diagnostic types in different scenarios. \ Depending on the context, zero, one or multiple bits may be set. When reporting a diagnostic, exactly one bit must be set. When controlling diagnostics or querying support, multiple bits may be set and zero bits can be a valid value, for example, when the OS calls [DxgkDdiControlDiagnosticReporting](nc-dispmprt-dxgkddi_controldiagnosticreporting.md) to disable all reporting.

