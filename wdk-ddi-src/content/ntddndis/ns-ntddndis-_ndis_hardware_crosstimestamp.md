---
UID: NS:ntddndis._NDIS_HARDWARE_CROSSTIMESTAMP
title: _NDIS_HARDWARE_CROSSTIMESTAMP (ntddndis.h)
description: This structure is reserved for system use and should not be used in your code.
tech.root: netvista
ms.date: 08/08/2018
keywords: ["NDIS_HARDWARE_CROSSTIMESTAMP structure"]
ms.keywords: _NDIS_HARDWARE_CROSSTIMESTAMP, NDIS_HARDWARE_CROSSTIMESTAMP, *PNDIS_HARDWARE_CROSSTIMESTAMP,
req.header: ntddndis.h
req.include-header: ndis.h
req.target-type: 
req.target-min-winverclnt: Windows 10, version 21H1. Supported in NDIS 6.82 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: NDIS_HARDWARE_CROSSTIMESTAMP, *PNDIS_HARDWARE_CROSSTIMESTAMP
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _NDIS_HARDWARE_CROSSTIMESTAMP
 - ntddndis/_NDIS_HARDWARE_CROSSTIMESTAMP
 - PNDIS_HARDWARE_CROSSTIMESTAMP
 - ntddndis/PNDIS_HARDWARE_CROSSTIMESTAMP
 - NDIS_HARDWARE_CROSSTIMESTAMP
 - ntddndis/NDIS_HARDWARE_CROSSTIMESTAMP
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddndis.h
api_name:
 - _NDIS_HARDWARE_CROSSTIMESTAMP
---

# _NDIS_HARDWARE_CROSSTIMESTAMP structure


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.

This structure is reserved for system use and should not be used in your code.

## -struct-fields

### -field Header


The [NDIS_OBJECT_HEADER](../objectheader/ns-objectheader-ndis_object_header.md) structure that describes this **NDIS_HARDWARE_CROSSTIMESTAMP** structure. Set the members of the **NDIS_OBJECT_HEADER** structure as follows:

* Set the **Type** member to **NDIS_OBJECT_TYPE_DEFAULT**.

* Set the **Revision** member to **NDIS_HARDWARE_CROSSTIMESTAMP_REVISION_1**.

* Set the **Size** member to **NDIS_SIZEOF_HARDWARE_CROSSTIMESTAMP_REVISION_1**.

### -field Flags

Reserved.

### -field SystemTimestamp1

Reserved.

### -field HardwareClockTimestamp

Reserved.

### -field SystemTimestamp2

Reserved.

## -remarks

## -see-also

