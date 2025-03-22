---
UID: NC:d3dkmddi.DXGKDDI_WRITEVIRTUALIZEDINTERRUPT
tech.root: display
title: DXGKDDI_WRITEVIRTUALIZEDINTERRUPT
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGKDDI_WRITEVIRTUALIZEDINTERRUPT function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_WRITEVIRTUALIZEDINTERRUPT
f1_keywords:
 - DXGKDDI_WRITEVIRTUALIZEDINTERRUPT
 - d3dkmddi/DXGKDDI_WRITEVIRTUALIZEDINTERRUPT
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_WRITEVIRTUALIZEDINTERRUPT
---

# DXGKDDI_WRITEVIRTUALIZEDINTERRUPT function (d3dkmddi.h)

## -description

**DxgkDdiWriteVirtualizedInterrupt** services writes to the MSI-X interrupt table during the process of live migration of a virtualized GPU device.

## -parameters

### -param hAdapter

[in] A handle to a context block associated with a display adapter. The display miniport driver previously provided this handle to *Dxgkrnl* in the **MiniportDeviceContext** output parameter of the [**DXGKDDI_ADD_DEVICE**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md) function.

### -param pArgs

[in] Pointer to a [**DXGKARG_GPUP_WRITE_VIRTUALIZED_MSIX**](ns-d3dkmddi-dxgkarg_gpup_write_virtualized_msix.md) structure that contains information needed to write to the MSI-X table.

## -returns

**DxgkDdiWriteVirtualizedInterrupt** returns STATUS_SUCCESS upon successful completion of the write operation; otherwise it returns an appropriate NTSTATUS code.

## -remarks

KMD's **DxgkDdiWriteVirtualizedInterrupt** is used in the context of virtualizing GPU devices, specifically for handling interrupts. The MSI-X (Message Signaled Interrupts eXtended) table is a data structure used in the PCI (Peripheral Component Interconnect) system of a computer, which allows for device-specific handling of interrupts.

**DxgkDdiWriteVirtualizedInterrupt** should write the values specified in [**WriteValue**](ns-d3dkmddi-dxgk_interrupt_table_entry.md) to the MSI-X table.

For more information, see [Live migration on GPU-P devices](/windows-hardware/drivers/display/live-migration-on-gpup-devices).

## -see-also

[**DXGKARG_GPUP_WRITE_VIRTUALIZED_MSIX**](ns-d3dkmddi-dxgkarg_gpup_write_virtualized_msix.md)

[**DXGK_INTERRUPT_TABLE_ENTRY**](ns-d3dkmddi-dxgk_interrupt_table_entry.md)
