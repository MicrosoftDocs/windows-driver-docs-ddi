---
UID: NE:ntddstor._STORAGE_STACK_TYPE
tech.root: storage
title: STORAGE_STACK_TYPE
ms.date: 03/15/2024
targetos: Windows
description: The STORAGE_STACK_TYPE enum indicates the storage stack type for the device, such as SCSI, NVMe, and so on.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: ntddstor.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
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
 - ntddstor.h
api_name:
 - _STORAGE_STACK_TYPE
 - PSTORAGE_STACK_TYPE
 - STORAGE_STACK_TYPE
f1_keywords:
 - _STORAGE_STACK_TYPE
 - ntddstor/_STORAGE_STACK_TYPE
 - PSTORAGE_STACK_TYPE
 - ntddstor/PSTORAGE_STACK_TYPE
 - STORAGE_STACK_TYPE
 - ntddstor/STORAGE_STACK_TYPE
dev_langs:
 - c++
helpviewer_keywords:
 - _STORAGE_STACK_TYPE
---

# STORAGE_STACK_TYPE enumeration (ntddstor.h)

## -description

The **STORAGE_STACK_TYPE** enum indicates the storage stack type for the device, such as SCSI, NVMe, and so on.

## -enum-fields

### -field StorageStackTypeUnknown

Specifies that the storage stack type is unknown.

### -field StorageStackTypeScsi

Specifies that the storage stack type is SCSI.

### -field StorageStackTypeNVMe

Specifies that the storage stack type is NVMe.

## -remarks

## -see-also
