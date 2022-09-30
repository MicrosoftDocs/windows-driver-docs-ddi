---
UID: NE:ntddstor._STORAGE_ASSOCIATION_TYPE
tech.root: storage
title: STORAGE_ASSOCIATION_TYPE
ms.date: 09/30/2022
targetos: Windows
description: Learn more about the STORAGE_ASSOCIATION_TYPE enumeration.
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
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - _STORAGE_ASSOCIATION_TYPE
 - PSTORAGE_ASSOCIATION_TYPE
 - STORAGE_ASSOCIATION_TYPE
f1_keywords:
 - _STORAGE_ASSOCIATION_TYPE
 - ntddstor/_STORAGE_ASSOCIATION_TYPE
 - PSTORAGE_ASSOCIATION_TYPE
 - ntddstor/PSTORAGE_ASSOCIATION_TYPE
 - STORAGE_ASSOCIATION_TYPE
 - ntddstor/STORAGE_ASSOCIATION_TYPE
dev_langs:
 - c++
helpviewer_keywords:
 - _STORAGE_ASSOCIATION_TYPE
---

## -description

The STORAGE\_ASSOCIATION\_TYPE enumeration indicates whether a storage descriptor identifies a device or a port.

## -enum-fields

### -field StorageIdAssocDevice

Indicates that the descriptor identifies a device.

### -field StorageIdAssocPort

Indicates that the descriptor identifies a port.

### -field StorageIdAssocTarget

Indicates that the descriptor identifies a target.

## -see-also

[**STORAGE\_IDENTIFIER**](ns-ntddstor-_storage_identifier.md)
