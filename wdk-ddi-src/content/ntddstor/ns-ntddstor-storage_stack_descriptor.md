---
UID: NS:ntddstor._STORAGE_STACK_DESCRIPTOR
tech.root: storage
title: STORAGE_STACK_DESCRIPTOR
ms.date: 03/15/2024
targetos: Windows
description: The STORAGE_STACK_DESCRIPTOR structure describes the storage stack for the device.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntddstor.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: STORAGE_STACK_DESCRIPTOR, *PSTORAGE_STACK_DESCRIPTOR
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - _STORAGE_STACK_DESCRIPTOR
 - PSTORAGE_STACK_DESCRIPTOR
 - STORAGE_STACK_DESCRIPTOR
f1_keywords:
 - _STORAGE_STACK_DESCRIPTOR
 - ntddstor/_STORAGE_STACK_DESCRIPTOR
 - PSTORAGE_STACK_DESCRIPTOR
 - ntddstor/PSTORAGE_STACK_DESCRIPTOR
 - STORAGE_STACK_DESCRIPTOR
 - ntddstor/STORAGE_STACK_DESCRIPTOR
dev_langs:
 - c++
helpviewer_keywords:
 - _STORAGE_STACK_DESCRIPTOR
---

# STORAGE_STACK_DESCRIPTOR structure (ntddstor.h)

## -description

The **STORAGE_STACK_DESCRIPTOR** structure describes the storage stack for the device.

## -struct-fields

### -field Version

The size of this structure serves as the version. This is set to `sizeof(STORAGE_STACK_DESCRIPTOR)`.

### -field Size

Size of buffer. The returned value indicates how big the buffer should be to store complete data.

### -field StorageStackType

Type of storage stack for the device, such as SCSI, NVMe, and so on.

## -remarks

## -see-also
