---
UID: NS:d3dkmddi._DXGKARG_GPUP_RESTORE_IMMUTABLE_MIGRATION_DATA
tech.root: display
title: DXGKARG_GPUP_RESTORE_IMMUTABLE_MIGRATION_DATA
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGKARG_GPUP_RESTORE_IMMUTABLE_MIGRATION_DATA structure.
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
req.typenames: DXGKARG_GPUP_RESTORE_IMMUTABLE_MIGRATION_DATA
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
 - _DXGKARG_GPUP_RESTORE_IMMUTABLE_MIGRATION_DATA
 - DXGKARG_GPUP_RESTORE_IMMUTABLE_MIGRATION_DATA
f1_keywords:
 - _DXGKARG_GPUP_RESTORE_IMMUTABLE_MIGRATION_DATA
 - d3dkmddi/_DXGKARG_GPUP_RESTORE_IMMUTABLE_MIGRATION_DATA
 - DXGKARG_GPUP_RESTORE_IMMUTABLE_MIGRATION_DATA
 - d3dkmddi/DXGKARG_GPUP_RESTORE_IMMUTABLE_MIGRATION_DATA
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARG_GPUP_RESTORE_IMMUTABLE_MIGRATION_DATA
---

# DXGKARG_GPUP_RESTORE_IMMUTABLE_MIGRATION_DATA structure (d3dkmddi.h)

## -description

The **DXGKARG_GPUP_RESTORE_IMMUTABLE_MIGRATION_DATA** structure is used in a call to [**DxgkDdiRestoreImmutableMigrationData**](nc-d3dkmddi-dxgkddi_restoreimmutablemigrationdata.md) to restore immutable data that was saved by the sending-side driver in a previous call to its [**DxgkDdiSaveImmutableMigrationData**](nc-d3dkmddi-dxgkddi_saveimmutablemigrationdata.md).

## -struct-fields

### -field vfIndex

[in] Identifies the virtual function / vDEV being referenced. This index value localizes to the specific virtual device.

### -field DataSize

[in] Size of the buffer that **Data** points to, in bytes.

### -field Data

[in] Pointer to the buffer containing the immutable migration data collected and sent from the source system that is to be restored on the target.

## -remarks

For more information, see [Live migration on GPU-P devices](/windows-hardware/drivers/display/live-migration-on-gpup-devices).

## -see-also

[**DxgkDdiRestoreImmutableMigrationData**](nc-d3dkmddi-dxgkddi_restoreimmutablemigrationdata.md)

[**DxgkDdiSaveImmutableMigrationData**](nc-d3dkmddi-dxgkddi_saveimmutablemigrationdata.md)
