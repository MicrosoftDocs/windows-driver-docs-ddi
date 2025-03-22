---
UID: NC:d3dkmddi.DXGKDDI_RESTOREIMMUTABLEMIGRATIONDATA
tech.root: display
title: DXGKDDI_RESTOREIMMUTABLEMIGRATIONDATA
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGKDDI_RESTOREIMMUTABLEMIGRATIONDATA function.
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
 - DXGKDDI_RESTOREIMMUTABLEMIGRATIONDATA
f1_keywords:
 - DXGKDDI_RESTOREIMMUTABLEMIGRATIONDATA
 - d3dkmddi/DXGKDDI_RESTOREIMMUTABLEMIGRATIONDATA
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_RESTOREIMMUTABLEMIGRATIONDATA
---

# DXGKDDI_RESTOREIMMUTABLEMIGRATIONDATA function (d3dkmddi.h)

## -description

The receiving-side OS calls **DxgkDdiRestoreImmutableMigrationData** to restore immutable data that was saved by the sending-side driver in a previous call to [**DxgkDdiSaveImmutableMigrationData**](nc-d3dkmddi-dxgkddi_saveimmutablemigrationdata.md).

## -parameters

### -param hAdapter

[in] A handle to a context block associated with a display adapter. The display miniport driver previously provided this handle to *Dxgkrnl* in the **MiniportDeviceContext** output parameter of the [**DXGKDDI_ADD_DEVICE**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md) function.

### -param pArgs

[in] Pointer to a [**DXGKARG_GPUP_RESTORE_IMMUTABLE_MIGRATION_DATA**](ns-d3dkmddi-dxgkarg_gpup_restore_immutable_migration_data.md) structure that contains information needed to restore the immutable data.

## -returns

**DxgkDdiRestoreImmutableMigrationData** returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate NTSTATUS code such as the STATUS_OBJECT_TYPE_MISMATCH error code (see Remarks).

## -remarks

Unlike the save/send side that is called twice, **DxgkDdiRestoreImmutableMigrationData** is called only once because it has all the data needed to present a full data buffer to the receiving side KMD. The driver should take the data and apply it to the VF being constructed, as well as any tracking for it, and it should validate the data invariants necessary for a successful restore.

The buffer is the content that was filled on the source side in [**DxgkDdiSaveImmutableMigrationData**](nc-d3dkmddi-dxgkddi_saveimmutablemigrationdata.md), so KMD should be tracking that data in a common type. There should also be a versioning scheme implemented in the content data if the data might potentially need to change with new drivers, and this scheme should be a part of the version checking done on the target.

If the data indicates that the target system isn't configured properly to have the VF migrated from the source, KMD should do the following:

1. Report this issue through the [**DxgkCbLogEtwEvent**](/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkcb_log_etw_event) with the GUID_DxgkAzureTriageEvent identifier and specific details on what failed validation so that the issue can be triaged and corrected.
2. Return from this DDI call with the STATUS_OBJECT_TYPE_MISMATCH error.

**DxgkDdiRestoreImmutableMigrationData** should only ever be called for VFs that are currently paused.

For more information, see [Live migration on GPU-P devices](/windows-hardware/drivers/display/live-migration-on-gpup-devices).

## -see-also

[**DXGKARG_GPUP_RESTORE_IMMUTABLE_MIGRATION_DATA**](ns-d3dkmddi-dxgkarg_gpup_restore_immutable_migration_data.md)

[**DxgkDdiSaveImmutableMigrationData**](nc-d3dkmddi-dxgkddi_saveimmutablemigrationdata.md)
