---
UID: NS:pointofservicedriverinterface._MSR_SUPPORTED_CARD_TYPES
title: _MSR_SUPPORTED_CARD_TYPES (pointofservicedriverinterface.h)
description: This structure defines the types of magnetic stripe cards supported by the reader.
old-location: pos\msr_supported_card_types.htm
tech.root: pos
ms.assetid: 57818ea9-f60b-4a37-9f42-613fb9cfaf36
ms.date: 02/23/2018
ms.keywords: "*PMSR_SUPPORTED_CARD_TYPES, MSR_SUPPORTED_CARD_TYPES, MSR_SUPPORTED_CARD_TYPES structure, PMSR_SUPPORTED_CARD_TYPES, PMSR_SUPPORTED_CARD_TYPES structure pointer, _MSR_SUPPORTED_CARD_TYPES, pointofservicedriverinterface/MSR_SUPPORTED_CARD_TYPES, pointofservicedriverinterface/PMSR_SUPPORTED_CARD_TYPES, pos.msr_supported_card_types"
ms.topic: struct
req.header: pointofservicedriverinterface.h
req.include-header: PointOfServiceDriverInterface.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- PointOfServiceDriverInterface.h
api_name:
- MSR_SUPPORTED_CARD_TYPES
product:
- Windows
targetos: Windows
req.typenames: MSR_SUPPORTED_CARD_TYPES, *PMSR_SUPPORTED_CARD_TYPES
---

# _MSR_SUPPORTED_CARD_TYPES structure


## -description


This structure defines the types of magnetic stripe cards supported by the reader.


## -struct-fields




### -field Count

Count of supported magnetic stripe cards defined in <b>CardTypes[MSR_CARD_TYPE_MAX_COUNT]</b>.


### -field CardTypes

Magnetic stripe cards supported by the reader. The first <b>Count</b> members are valid.

