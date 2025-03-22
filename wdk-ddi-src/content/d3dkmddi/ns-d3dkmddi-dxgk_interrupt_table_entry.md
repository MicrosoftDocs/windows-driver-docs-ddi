---
UID: NS:d3dkmddi._DXGK_INTERRUPT_TABLE_ENTRY
tech.root: display
title: DXGK_INTERRUPT_TABLE_ENTRY
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGK_INTERRUPT_TABLE_ENTRY structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGK_INTERRUPT_TABLE_ENTRY
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_INTERRUPT_TABLE_ENTRY
 - DXGK_INTERRUPT_TABLE_ENTRY
f1_keywords:
 - _DXGK_INTERRUPT_TABLE_ENTRY
 - d3dkmddi/_DXGK_INTERRUPT_TABLE_ENTRY
 - DXGK_INTERRUPT_TABLE_ENTRY
 - d3dkmddi/DXGK_INTERRUPT_TABLE_ENTRY
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGK_INTERRUPT_TABLE_ENTRY
---

# DXGK_INTERRUPT_TABLE_ENTRY structure (d3dkmddi.h)

## -description

The **DXGK_INTERRUPT_TABLE_ENTRY** structure contains data to write to an MSI-X table entry.

## -struct-fields

### -field MessageAddress

System-specified message address (per PCI Local Bus Specification, section 6.8).

### -field MessageData

System-specified message (per PCI Local Bus Specification, section 6.8).

### -field VectorControl

Vector control field (per PCI Local Bus Specification, section 6.8).

## -remarks

For more information, see [Live migration on GPU-P devices](/windows-hardware/drivers/display/live-migration-on-gpup-devices).

## -see-also

[**DXGKARG_GPUP_WRITE_VIRTUALIZED_MSIX**](ns-d3dkmddi-dxgkarg_gpup_write_virtualized_msix.md)

[**DxgkDdiWriteVirtualizedInterrupt**](nc-d3dkmddi-dxgkddi_writevirtualizedinterrupt.md)  
