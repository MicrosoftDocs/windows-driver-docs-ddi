---
UID: NC:d3dkmddi.DXGKDDI_SAVEMUTABLEMIGRATIONDATA
tech.root: display
title: DXGKDDI_SAVEMUTABLEMIGRATIONDATA
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGKDDI_SAVEMUTABLEMIGRATIONDATA function.
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
 - DXGKDDI_SAVEMUTABLEMIGRATIONDATA
f1_keywords:
 - DXGKDDI_SAVEMUTABLEMIGRATIONDATA
 - d3dkmddi/DXGKDDI_SAVEMUTABLEMIGRATIONDATA
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_SAVEMUTABLEMIGRATIONDATA
---

# DXGKDDI_SAVEMUTABLEMIGRATIONDATA function (d3dkmddi.h)

## -description

KMD's **DxgkDdiSaveMutableMigrationData** function collects mutable data for a live migration that is about to end.

## -parameters

### -param hAdapter

[in] A handle to a context block associated with a display adapter. The display miniport driver previously provided this handle to *Dxgkrnl* in the **MiniportDeviceContext** output parameter of the [**DXGKDDI_ADD_DEVICE**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md) function.

### -param pArgs

[in/out] Pointer to a [**DXGKARG_GPUP_SAVE_MUTABLE_MIGRATION_DATA**](ns-d3dkmddi-dxgkarg_gpup_save_mutable_migration_data.md) structure for information related to the call.

## -returns

**DxgkDdiSaveMutableMigrationData** returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate NTSTATUS code.

## -remarks

[**DxgkDdiSaveMutableMigrationData**](/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_savemutablemigrationdata) is called to collect mutable data when a live migration is about to end. This DDI should only ever be called for VFs that are currently paused.

**DxgkDdiSaveMutableMigrationData** is called in the classic dynamic buffer pattern:

* On the first call, **DataSize** is set to 0 and **Data** to NULL. KMD should change **DataSize** to the total number of bytes it needs to store the immutable data.
* *Dxgkrnl* creates a buffer of **DataSize** bytes and makes a second call with **DataSize** set to the value returned by KMD and **Data** pointing to the allocated buffer. *Dxgkrnl* controls the lifetime of this allocated memory after the call.

[**DxgkDdiSaveImmutableMigrationData**](/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_saveimmutablemigrationdata) is called at the start of a live migration to collect immutable data.

For more information, see [Live migration on GPU-P devices](/windows-hardware/drivers/display/live-migration-on-gpup-devices).

## -see-also

[**DXGKARG_GPUP_SAVE_MUTABLE_MIGRATION_DATA**](ns-d3dkmddi-dxgkarg_gpup_save_immutable_migration_data.md)

[**DxgkDdiSaveImmutableMigrationData**](/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_saveimmutablemigrationdata)
