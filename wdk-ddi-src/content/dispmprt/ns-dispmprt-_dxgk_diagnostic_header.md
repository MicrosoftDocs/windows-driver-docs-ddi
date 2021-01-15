---
UID: NS:dispmprt._DXGK_DIAGNOSTIC_HEADER
title: _DXGK_DIAGNOSTIC_HEADER (dispmprt.h)
description: Header structure which contains the common fields used to describe all diagnostic events.
ms.date: 10/19/2018
keywords: ["DXGK_DIAGNOSTIC_HEADER structure"]
ms.keywords: _DXGK_DIAGNOSTIC_HEADER, DXGK_DIAGNOSTIC_HEADER, *IN_PDXGK_DIAGNOSTIC_HEADER
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
req.typenames: DXGK_DIAGNOSTIC_HEADER
targetos: Windows
tech.root: display
f1_keywords:
 - _DXGK_DIAGNOSTIC_HEADER
 - dispmprt/_DXGK_DIAGNOSTIC_HEADER
 - DXGK_DIAGNOSTIC_HEADER
 - dispmprt/DXGK_DIAGNOSTIC_HEADER
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGK_DIAGNOSTIC_HEADER
 - DXGK_DIAGNOSTIC_HEADER
product:
 - Windows
---

# _DXGK_DIAGNOSTIC_HEADER structure


## -description

Header structure which contains the common fields used to describe all diagnostic events.

## -struct-fields

### -field Size

Size in bytes of the event being reported including the header. For OS defined event types, the size will be checked against the expected size of the associated structure.

### -field Reserved

Reserved.

### -field Value

Value of the header.

### -field TargetId

A 32-bit value that identifies the component to which this event relates. The interpretation of the field is dependent on the type of diagnostic being reported.

### -field SourceId

A 32-bit value that identifies the component to which this event relates. The interpretation of the field is dependent on the type of diagnostic being reported.

### -field Id

A 32-bit value that identifies the component to which this event relates. The interpretation of the field is dependent on the type of diagnostic being reported.

### -field Category

A [DXGK_DIAGNOSTIC_CATEGORIES](ns-dispmprt-_dxgk_diagnostic_categories.md) structure with a single bit field set to one to indicate the category of diagnostic being described.

### -field Type

A [DXGK_DIAGNOSTIC_TYPES](ns-dispmprt-_dxgk_diagnostic_types.md) structure with a single bit field set to one to indicate the type of diagnostic being described.

### -field SequenceNumber

An adapter global value incremented for each diagnostic reported such that each report has a unique sequence number, within the limits of a 32-bit value.

