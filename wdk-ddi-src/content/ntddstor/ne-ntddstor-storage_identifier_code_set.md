---
UID: NE:ntddstor._STORAGE_IDENTIFIER_CODE_SET
tech.root: storage
title: STORAGE_IDENTIFIER_CODE_SET
ms.date: 09/30/2022
targetos: Windows
description: Learn more about the STORAGE_IDENTIFIER_CODE_SET enumeration.
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
 - _STORAGE_IDENTIFIER_CODE_SET
 - PSTORAGE_IDENTIFIER_CODE_SET
 - STORAGE_IDENTIFIER_CODE_SET
f1_keywords:
 - _STORAGE_IDENTIFIER_CODE_SET
 - ntddstor/_STORAGE_IDENTIFIER_CODE_SET
 - PSTORAGE_IDENTIFIER_CODE_SET
 - ntddstor/PSTORAGE_IDENTIFIER_CODE_SET
 - STORAGE_IDENTIFIER_CODE_SET
 - ntddstor/STORAGE_IDENTIFIER_CODE_SET
dev_langs:
 - c++
helpviewer_keywords:
 - _STORAGE_IDENTIFIER_CODE_SET
---

## -description

The STORAGE\_IDENTIFIER\_CODE\_SET enumeration specifies the code set used by a SCSI identification descriptor ([**STORAGE\_IDENTIFIER**](ns-ntddstor-_storage_identifier.md)) to identify a logical unit.

## -enum-fields

### -field StorageIdCodeSetReserved

Reserved.

### -field StorageIdCodeSetBinary

Indicates that the identification descriptor contains a binary representation of the identifier.

### -field StorageIdCodeSetAscii

Indicates that the identification descriptor contains an ASCII representation of the identifier.

### -field StorageIdCodeSetUtf8

Indicates that the identification descriptor contains a UTF8 representation of the identifier.

## -remarks

This field is intended to be an aid to software that displays the identifier field. Every device identification page (page code 0x83) of SCSI vital product data contains a series of identification descriptors, each of which contains an identifier.

## -see-also

[**STORAGE\_IDENTIFIER**](ns-ntddstor-_storage_identifier.md)
