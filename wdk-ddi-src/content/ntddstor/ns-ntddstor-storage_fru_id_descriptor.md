---
UID: NS:ntddstor._STORAGE_FRU_ID_DESCRIPTOR
tech.root: storage
title: STORAGE_FRU_ID_DESCRIPTOR
ms.date: 05/13/2021
targetos: Windows
description: STORAGE_FRU_ID_DESCRIPTOR is the structure used when a caller sends IOCTL_STORAGE_QUERY_PROPERTY to query for the ID of a fault replacement unit (FRU).
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
req.typenames: STORAGE_FRU_ID_DESCRIPTOR, *PSTORAGE_FRU_ID_DESCRIPTOR
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - _STORAGE_FRU_ID_DESCRIPTOR
 - PSTORAGE_FRU_ID_DESCRIPTOR
 - STORAGE_FRU_ID_DESCRIPTOR
f1_keywords:
 - _STORAGE_FRU_ID_DESCRIPTOR
 - ntddstor/_STORAGE_FRU_ID_DESCRIPTOR
 - PSTORAGE_FRU_ID_DESCRIPTOR
 - ntddstor/PSTORAGE_FRU_ID_DESCRIPTOR
 - STORAGE_FRU_ID_DESCRIPTOR
 - ntddstor/STORAGE_FRU_ID_DESCRIPTOR
dev_langs:
 - c++
---

## -description

**STORAGE_FRU_ID_DESCRIPTOR** is the structure used when a caller sends [**IOCTL_STORAGE_QUERY_PROPERTY**](ni-ntddstor-ioctl_storage_query_property.md) to query for the ID of a fault replacement unit (FRU).

## -struct-fields

### -field Version

Version of this structure. Set to ```sizeof(STORAGE_FRU_ID_DESCRIPTOR)```.

### -field Size

Size of this structure, in bytes. Must be >= ```sizeof(STORAGE_FRU_ID_DESCRIPTOR)```.

### -field IdentifierSize

Size of the array in **Identifier**, in bytes.

### -field Identifier

Array in which to write the FRU's identifier. The size of this array is **IdentifierSize** bytes.

## -remarks

**STORAGE_FRU_ID_DESCRIPTOR** is used as the output buffer in which to return the result when a caller sends [**IOCTL_STORAGE_QUERY_PROPERTY**](ni-ntddstor-ioctl_storage_query_property.md) with a [**STORAGE_PROPERTY_ID**](ne-ntddstor-storage_property_id.md) value of **StorageFruIdProperty**.

## -see-also

[**IOCTL_STORAGE_QUERY_PROPERTY**](ni-ntddstor-ioctl_storage_query_property.md)

[**STORAGE_PROPERTY_ID**](ne-ntddstor-storage_property_id.md)

[**STORAGE_PROPERTY_QUERY**](ns-ntddstor-_storage_property_query.md)

[**STORAGE_QUERY_TYPE**](ne-ntddstor-_storage_query_type.md)
