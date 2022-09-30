---
UID: NE:ntddstor._STORAGE_IDENTIFIER_TYPE
tech.root: storage
title: STORAGE_IDENTIFIER_TYPE
ms.date: 09/30/2022
targetos: Windows
description: Learn more about the STORAGE_IDENTIFIER_TYPE enumeration.
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
 - _STORAGE_IDENTIFIER_TYPE
 - PSTORAGE_IDENTIFIER_TYPE
 - STORAGE_IDENTIFIER_TYPE
f1_keywords:
 - _STORAGE_IDENTIFIER_TYPE
 - ntddstor/_STORAGE_IDENTIFIER_TYPE
 - PSTORAGE_IDENTIFIER_TYPE
 - ntddstor/PSTORAGE_IDENTIFIER_TYPE
 - STORAGE_IDENTIFIER_TYPE
 - ntddstor/STORAGE_IDENTIFIER_TYPE
dev_langs:
 - c++
helpviewer_keywords:
 - _STORAGE_IDENTIFIER_TYPE
---

## -description

The STORAGE\_IDENTIFIER\_TYPE enumeration specifies the type of storage identifier.

## -enum-fields

### -field StorageIdTypeVendorSpecific

Indicates that the vendor created the identifier without reference to an assignment authority, and consequently there is no guarantee that the identifier is globally unique.

### -field StorageIdTypeVendorId

Indicates a vendor identifier strings assigned by the SCSI-3 specification to the vendor.

### -field StorageIdTypeEUI64

Indicates a 64-bit IEEE extended unique identifier (EUI-64).

### -field StorageIdTypeFCPHName

Indicates a 64-bit FC-PH name identifier as defined in the *X3.230-1994* specification.

### -field StorageIdTypePortRelative

Indicates that the identifier type depends on the port.

### -field StorageIdTypeTargetPortGroup

### -field StorageIdTypeLogicalUnitGroup

### -field StorageIdTypeMD5LogicalUnitIdentifier

### -field StorageIdTypeScsiNameString

Indicates that the identifier type is specified by a Scsi name string.

## -see-also

[**STORAGE\_IDENTIFIER**](ns-ntddstor-_storage_identifier.md)
