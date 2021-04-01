---
UID: NE:ntddstor._STORAGE_SANITIZE_METHOD
tech.root: storage
title: STORAGE_SANITIZE_METHOD
ms.date: 05/13/2021
targetos: Windows
description: The STORAGE_SANITIZE_METHOD enumeration identifies the sanitize method for an NVMe device.
req.construct-type: enumeration
req.ddi-compliance: 
req.header: ntddstor.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 10, version 21H1
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
 - _STORAGE_SANITIZE_METHOD
 - PSTORAGE_SANITIZE_METHOD
 - STORAGE_SANITIZE_METHOD
f1_keywords:
 - _STORAGE_SANITIZE_METHOD
 - ntddstor/_STORAGE_SANITIZE_METHOD
 - PSTORAGE_SANITIZE_METHOD
 - ntddstor/PSTORAGE_SANITIZE_METHOD
 - STORAGE_SANITIZE_METHOD
 - ntddstor/STORAGE_SANITIZE_METHOD
dev_langs:
 - c++
---

## -description

The **STORAGE_SANITIZE_METHOD** enumeration identifies the sanitize method for an NVMe device.

## -enum-fields

### -field StorageSanitizeMethodDefault

Perform the default sanitize operation.

### -field StorageSanitizeMethodBlockErase

Perform a Block Erase sanitize operation.

### -field StorageSanitizeMethodCryptoErase

Perform a Crypto Erase sanitize operation.

## -remarks

**STORAGE_SANITIZE_METHOD** applies to NVMe devices only. It is specified in a[**STORAGE_REINITIALIZE_MEDIA**](ns-ntddstor-storage_reinitialize_media.md) structure, which is optionally provided to [**IOCTL_STORAGE_REINITIALIZE_MEDIA**](ni-ntddstor-ioctl_storage_reinitialize_media.md).

## -see-also

[**IOCTL_STORAGE_REINITIALIZE_MEDIA**](ni-ntddstor-ioctl_storage_reinitialize_media.md)

[**STORAGE_REINITIALIZE_MEDIA**](ns-ntddstor-storage_reinitialize_media.md)
