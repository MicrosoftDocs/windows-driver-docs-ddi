---
UID: NS:ks.__unnamed_struct_39
title: KS_FRAMING_RANGE_WEIGHTED (ks.h)
description: Drivers can use the KS_FRAMING_RANGE_WEIGHTED structure to specify a range of weighted frame sizes.
old-location: stream\ks_framing_range_weighted.htm
tech.root: stream
ms.assetid: a52cde43-f440-4e58-97b7-b2aac5fb5f6a
ms.date: 04/23/2018
keywords: ["KS_FRAMING_RANGE_WEIGHTED structure"]
ms.keywords: "*PKS_FRAMING_RANGE_WEIGHTED, KS_FRAMING_RANGE_WEIGHTED, KS_FRAMING_RANGE_WEIGHTED structure [Streaming Media Devices], PKS_FRAMING_RANGE_WEIGHTED, PKS_FRAMING_RANGE_WEIGHTED structure pointer [Streaming Media Devices], ks-struct_9bc7dcda-b095-4f53-9446-40ec43d6397b.xml, ks/KS_FRAMING_RANGE_WEIGHTED, ks/PKS_FRAMING_RANGE_WEIGHTED, stream.ks_framing_range_weighted"
req.header: ks.h
req.include-header: Ks.h
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
targetos: Windows
req.typenames: KS_FRAMING_RANGE_WEIGHTED, *PKS_FRAMING_RANGE_WEIGHTED
f1_keywords:
 - PKS_FRAMING_RANGE_WEIGHTED
 - ks/PKS_FRAMING_RANGE_WEIGHTED
 - KS_FRAMING_RANGE_WEIGHTED
 - ks/KS_FRAMING_RANGE_WEIGHTED
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KS_FRAMING_RANGE_WEIGHTED
---

# KS_FRAMING_RANGE_WEIGHTED structure


## -description

Drivers can use the KS_FRAMING_RANGE_WEIGHTED structure to specify a range of weighted frame sizes.

## -struct-fields

### -field Range

Specifies the framing range.

### -field InPlaceWeight

Not currently supported. Drivers should set to zero.

### -field NotInPlaceWeight

Not currently supported. Drivers should set to zero.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/ns-ks-ks_framing_item">KS_FRAMING_ITEM</a>