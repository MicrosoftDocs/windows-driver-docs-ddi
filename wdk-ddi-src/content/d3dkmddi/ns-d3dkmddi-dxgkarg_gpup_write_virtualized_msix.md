---
UID: NS:d3dkmddi._DXGKARG_GPUP_WRITE_VIRTUALIZED_MSIX
tech.root: display
title: DXGKARG_GPUP_WRITE_VIRTUALIZED_MSIX
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGKARG_GPUP_WRITE_VIRTUALIZED_MSIX structure.
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
req.typenames: DXGKARG_GPUP_WRITE_VIRTUALIZED_MSIX
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
 - _DXGKARG_GPUP_WRITE_VIRTUALIZED_MSIX
 - DXGKARG_GPUP_WRITE_VIRTUALIZED_MSIX
f1_keywords:
 - _DXGKARG_GPUP_WRITE_VIRTUALIZED_MSIX
 - d3dkmddi/_DXGKARG_GPUP_WRITE_VIRTUALIZED_MSIX
 - DXGKARG_GPUP_WRITE_VIRTUALIZED_MSIX
 - d3dkmddi/DXGKARG_GPUP_WRITE_VIRTUALIZED_MSIX
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARG_GPUP_WRITE_VIRTUALIZED_MSIX
---

# DXGKARG_GPUP_WRITE_VIRTUALIZED_MSIX structure (d3dkmddi.h)

## -description

The **DXGKARG_GPUP_WRITE_VIRTUALIZED_MSIX** structure is a parameter for the [**DxgkDdiWriteVirtualizedInterrupt**](nc-d3dkmddi-dxgkddi_writevirtualizedinterrupt.md) function that writes to the MSI-X interrupt table during the process of live migration of a virtualized GPU device.

## -struct-fields

### -field vfIndex

[in] Identifies the virtual function / vDEV being referenced. This index value localizes to the specific virtual device.

### -field InterruptTableIndex

[in] Index of the MSI-X table entry to write to.

### -field WriteValue

[in] A [**DXGK_INTERRUPT_TABLE_ENTRY**](ns-d3dkmddi-dxgk_interrupt_table_entry.md) structure that contains the data to write to the MSI-X table entry.

## -remarks

For more information, see [Live migration on GPU-P devices](/windows-hardware/drivers/display/live-migration-on-gpup-devices).

## -see-also

[**DXGK_INTERRUPT_TABLE_ENTRY**](ns-d3dkmddi-dxgk_interrupt_table_entry.md)

[**DxgkDdiWriteVirtualizedInterrupt**](nc-d3dkmddi-dxgkddi_writevirtualizedinterrupt.md)  
