---
UID: NE:d3dkmddi._DXGK_GPUP_MIGRATIONTYPE
tech.root: display
title: DXGK_GPUP_MIGRATIONTYPE
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGK_GPUP_MIGRATIONTYPE enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_GPUP_MIGRATIONTYPE
 - DXGK_GPUP_MIGRATIONTYPE
f1_keywords:
 - _DXGK_GPUP_MIGRATIONTYPE
 - d3dkmddi/_DXGK_GPUP_MIGRATIONTYPE
 - DXGK_GPUP_MIGRATIONTYPE
 - d3dkmddi/DXGK_GPUP_MIGRATIONTYPE
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGK_GPUP_MIGRATIONTYPE
---

# DXGK_GPUP_MIGRATIONTYPE enumeration (d3dkmddi.h)

## -description

The **DXGK_GPUP_MIGRATIONTYPE** enumeration identifies the side of the migration process to prepare for.

## -enum-fields

### -field DXGK_GPUP_MIGRATIONTYPE_SOURCE:0

The migration is starting on the source side.

### -field DXGK_GPUP_MIGRATIONTYPE_TARGET:1

The migration is starting on the target side.

## -remarks

For more information, see [Live migration on GPU-P devices](/windows-hardware/drivers/display/live-migration-on-gpup-devices).

## -see-also

[**DXGKARG_GPUP_PREPARE_LIVE_MIGRATION**](ns-d3dkmddi-dxgkarg_gpup_prepare_live_migration.md)

[**DxgkDdiPrepareLiveMigration**](nc-d3dkmddi-dxgkddi_preparelivemigration.md)
