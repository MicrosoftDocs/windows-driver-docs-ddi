---
UID: NC:d3dkmddi.DXGKDDI_RESTOREMUTABLEMIGRATIONDATA
tech.root: display
title: DXGKDDI_RESTOREMUTABLEMIGRATIONDATA
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGKDDI_RESTOREMUTABLEMIGRATIONDATA function.
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
 - DXGKDDI_RESTOREMUTABLEMIGRATIONDATA
f1_keywords:
 - DXGKDDI_RESTOREMUTABLEMIGRATIONDATA
 - d3dkmddi/DXGKDDI_RESTOREMUTABLEMIGRATIONDATA
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_RESTOREMUTABLEMIGRATIONDATA
---

# DXGKDDI_RESTOREMUTABLEMIGRATIONDATA function (d3dkmddi.h)

## -description

The receiving-side OS calls **DxgkDdiRestoreMutableMigrationData** to restore mutable data that was saved by the sending-side driver in a previous call to [**DxgkDdiSaveMutableMigrationData**](nc-d3dkmddi-dxgkddi_savemutablemigrationdata.md).

## -parameters

### -param hAdapter

[in] A handle to a context block associated with a display adapter. The display miniport driver previously provided this handle to *Dxgkrnl* in the **MiniportDeviceContext** output parameter of the [**DXGKDDI_ADD_DEVICE**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md) function.

### -param pArgs

[in] Pointer to a [**DXGKARG_GPUP_RESTORE_MUTABLE_MIGRATION_DATA**](ns-d3dkmddi-dxgkarg_gpup_restore_mutable_migration_data.md) structure that contains information needed to restore the mutable data.

## -returns

**DxgkDdiRestoreImmutableMigrationData** returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate NTSTATUS code.

## -remarks

This DDI should only ever be called for VFs that are currently paused.

For more information, see [Live migration on GPU-P devices](/windows-hardware/drivers/display/live-migration-on-gpup-devices).

## -see-also

[**DXGKARG_GPUP_RESTORE_MUTABLE_MIGRATION_DATA**](ns-d3dkmddi-dxgkarg_gpup_restore_mutable_migration_data.md)

[**DxgkDdiSaveMutableMigrationData**](nc-d3dkmddi-dxgkddi_savemutablemigrationdata.md)
