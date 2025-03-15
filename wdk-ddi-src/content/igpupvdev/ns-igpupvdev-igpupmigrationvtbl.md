---
UID: NS:igpupvdev.IGPUPMigrationVtbl
tech.root: display
title: IGPUPMigrationVtbl
ms.date: 02/10/2025
targetos: Windows
description: Learn more about the IGPUPMigrationVtbl structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: igpupvdev.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: IGPUPMigrationVtbl
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - igpupvdev.h
api_name:
 - IGPUPMigrationVtbl
f1_keywords:
 - IGPUPMigrationVtbl
 - igpupvdev/IGPUPMigrationVtbl
dev_langs:
 - c++
helpviewer_keywords:
 - IGPUPMigrationVtbl
---

## -description

The **IGPUPMigrationVtbl** structure defines the virtual table for the [**IGPUPMigration**](nn-igpupvdev-igpupmigration.md) interface.

## -struct-fields

### -field b

### -field QueryInterface

Retrieves pointers to supported interfaces.

### -field AddRef

Increments the reference count for an interface on an object.

### -field Release

Decrements the reference count for an interface on an object.

### -field SaveImmutableGpup

Method to save the immutable GPU partition.

### -field RestoreImmutableGpup

Method to restore the immutable GPU partition.

## -remarks

For more information see [Live migration on GPU-P machines](/windows-hardware/drivers/display/live-migration-on-gpup-devices).

## -see-also

[**RestoreImmutableGpup**](nf-igpupvdev-igpupmigration-restoreimmutablegpup.md)

[**SaveImmutableGpup**](nf-igpupvdev-igpupmigration-saveimmutablegpup.md)

[**IGPUPMigration**](nn-igpupvdev-igpupmigration.md)
