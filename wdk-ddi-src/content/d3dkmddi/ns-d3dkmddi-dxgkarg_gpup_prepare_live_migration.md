---
UID: NS:d3dkmddi._DXGKARG_GPUP_PREPARE_LIVE_MIGRATION
tech.root: display
title: DXGKARG_GPUP_PREPARE_LIVE_MIGRATION
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGKARG_GPUP_PREPARE_LIVE_MIGRATION structure.
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
req.typenames: DXGKARG_GPUP_PREPARE_LIVE_MIGRATION
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
 - _DXGKARG_GPUP_PREPARE_LIVE_MIGRATION
 - DXGKARG_GPUP_PREPARE_LIVE_MIGRATION
f1_keywords:
 - _DXGKARG_GPUP_PREPARE_LIVE_MIGRATION
 - d3dkmddi/_DXGKARG_GPUP_PREPARE_LIVE_MIGRATION
 - DXGKARG_GPUP_PREPARE_LIVE_MIGRATION
 - d3dkmddi/DXGKARG_GPUP_PREPARE_LIVE_MIGRATION
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARG_GPUP_PREPARE_LIVE_MIGRATION
---

# DXGKARG_GPUP_PREPARE_LIVE_MIGRATION structure (d3dkmddi.h)

## -description

The **DXGKARG_GPUP_PREPARE_LIVE_MIGRATION** structure contains information for the KMD's [**DxgkDdiPrepareLiveMigration**](nc-d3dkmddi-dxgkddi_preparelivemigration.md) function to prepare for a live migration.

## -struct-fields

### -field vfIndex

[in] Identifies the virtual function / vDEV being referenced. This index value localizes to the specific virtual device.

### -field MigrationType

[in] A [**DXGK_GPUP_MIGRATION_TYPE**](ne-d3dkmddi-dxgk_gpup_migrationtype.md) enumeration that specifies the type of migration that is about to start.

## -remarks

For more information, see [Live migration on GPU-P devices](/windows-hardware/drivers/display/live-migration-on-gpup-devices).

## -see-also

[**DXGK_GPUP_MIGRATION_TYPE**](ne-d3dkmddi-dxgk_gpup_migrationtype.md)

[**DxgkDdiPrepareLiveMigration**](nc-d3dkmddi-dxgkddi_preparelivemigration.md)
