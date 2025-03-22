---
UID: NC:d3dkmddi.DXGKDDI_SAVEIMMUTABLEMIGRATIONDATA
tech.root: display
title: DXGKDDI_SAVEIMMUTABLEMIGRATIONDATA
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGKDDI_SAVEIMMUTABLEMIGRATIONDATA function.
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
 - DXGKDDI_SAVEIMMUTABLEMIGRATIONDATA
f1_keywords:
 - DXGKDDI_SAVEIMMUTABLEMIGRATIONDATA
 - d3dkmddi/DXGKDDI_SAVEIMMUTABLEMIGRATIONDATA
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_SAVEIMMUTABLEMIGRATIONDATA
---

# DXGKDDI_SAVEIMMUTABLEMIGRATIONDATA function (d3dkmddi.h)

## -description

KMD's **DxgkDdiSaveImmutableMigrationData** function saves immutable data for a live migration that is about to start.

## -parameters

### -param hAdapter

[in] A handle to a context block associated with a display adapter. The display miniport driver previously provided this handle to *Dxgkrnl* in the **MiniportDeviceContext** output parameter of the [**DXGKDDI_ADD_DEVICE**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md) function.

### -param pArgs

[in/out] Pointer to a [**DXGKARG_GPUP_SAVE_IMMUTABLE_MIGRATION_DATA**](ns-d3dkmddi-dxgkarg_gpup_save_immutable_migration_data.md) structure for information related to the call.

## -returns

**DxgkDdiSaveImmutableMigrationData** returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate NTSTATUS code.

## -remarks

After calling KMD's [**DxgkDdiPrepareLiveMigration**](/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_preparelivemigration) function, *Dxgkrnl* then calls**DxgkDdiSaveImmutableMigrationData** to gather information about the device to restore on the target side. This point is also an opportunity for the system to validate the configuration of the remote, so **DxgkDdiSaveImmutableMigrationData** should package up enough information to validate any hardware, firmware, or driver validation data that can detect the capability to move the VF over to the target configuration.

The driver should store data about the VF that won't change while it is alive that the target's KMD can use to help initialize the new VF. This data doesn't need to include the vGPU creation parameters, as those will be transferred in lower levels and used to create the vGPU using the normal DDI. This can include all data that is immutably tied to the VF, and doesn't all need to be restored on the target side. Data can be sent purely for validation purposes, which is a critical part of this interface.

**DxgkDdiSaveImmutableMigrationData** is called in the classic dynamic buffer pattern:

* On the first call, **DataSize** is set to 0 and **Data** to NULL. KMD should change **DataSize** to the total number of bytes it needs to store the immutable data.
* *Dxgkrnl* creates a buffer of **DataSize** bytes and makes a second call with **DataSize** set to the value returned by KMD and **Data** pointing to the allocated buffer. *Dxgkrnl* controls the lifetime of this allocated memory after the call.

[**DxgkDdiSaveMutableMigrationData**](/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_savemutablemigrationdata) is called at the end of a live migration to collect mutable data.

For more information, see [Live migration on GPU-P devices](/windows-hardware/drivers/display/live-migration-on-gpup-devices).

## -see-also

[**DXGKARG_GPUP_SAVE_IMMUTABLE_MIGRATION_DATA**](ns-d3dkmddi-dxgkarg_gpup_save_immutable_migration_data.md)

[**DxgkDdiPrepareLiveMigration**](/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_preparelivemigration)

[**DxgkDdiSaveMutableMigrationData**](/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_savemutablemigrationdata)
