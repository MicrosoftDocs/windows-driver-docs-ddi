---
UID: NS:miniport._PCI_SEGMENT_BUS_NUMBER
tech.root: PCI
title: PCI_SEGMENT_BUS_NUMBER
ms.date: 05/13/2021
targetos: Windows
description: The PCI_SEGMENT_BUS_NUMBER structure contains information about the bus and segment numbers.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: miniport.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 21H1
req.target-min-winversvr: 
req.target-type: 
req.typenames: PCI_SEGMENT_BUS_NUMBER, *PPCI_SEGMENT_BUS_NUMBER
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - miniport.h
api_name:
 - _PCI_SEGMENT_BUS_NUMBER
 - PPCI_SEGMENT_BUS_NUMBER
 - PCI_SEGMENT_BUS_NUMBER
f1_keywords:
 - _PCI_SEGMENT_BUS_NUMBER
 - miniport/_PCI_SEGMENT_BUS_NUMBER
 - PPCI_SEGMENT_BUS_NUMBER
 - miniport/PPCI_SEGMENT_BUS_NUMBER
 - PCI_SEGMENT_BUS_NUMBER
 - miniport/PCI_SEGMENT_BUS_NUMBER
dev_langs:
 - c++
---

## -description

The **PCI_SEGMENT_BUS_NUMBER** structure contains information about the bus and segment numbers.

## -struct-fields

### -field u

### -field u.bits

### -field u.bits.BusNumber

Identifies a PCI bus.

### -field u.bits.SegmentNumber

Identifies a PCI segment.

### -field u.bits.Reserved

Reserved.

### -field u.AsULONG

## -remarks

**PCI_SEGMENT_BUS_NUMBER** is reserved for system use.
