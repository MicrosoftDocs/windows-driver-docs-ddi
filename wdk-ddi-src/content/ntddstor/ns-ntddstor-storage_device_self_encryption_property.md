---
UID: NS:ntddstor._STORAGE_DEVICE_SELF_ENCRYPTION_PROPERTY
tech.root: storage
title: STORAGE_DEVICE_SELF_ENCRYPTION_PROPERTY
ms.date: 05/13/2021
targetos: Windows
description: STORAGE_DEVICE_SELF_ENCRYPTION_PROPERTY is the structure used when a caller sends IOCTL_STORAGE_QUERY_PROPERTY to query whether a device supports self encryption.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntddstor.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 21H1
req.target-min-winversvr: 
req.target-type: 
req.typenames: STORAGE_DEVICE_SELF_ENCRYPTION_PROPERTY, *PSTORAGE_DEVICE_SELF_ENCRYPTION_PROPERTY
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - _STORAGE_DEVICE_SELF_ENCRYPTION_PROPERTY
 - PSTORAGE_DEVICE_SELF_ENCRYPTION_PROPERTY
 - STORAGE_DEVICE_SELF_ENCRYPTION_PROPERTY
f1_keywords:
 - _STORAGE_DEVICE_SELF_ENCRYPTION_PROPERTY
 - ntddstor/_STORAGE_DEVICE_SELF_ENCRYPTION_PROPERTY
 - PSTORAGE_DEVICE_SELF_ENCRYPTION_PROPERTY
 - ntddstor/PSTORAGE_DEVICE_SELF_ENCRYPTION_PROPERTY
 - STORAGE_DEVICE_SELF_ENCRYPTION_PROPERTY
 - ntddstor/STORAGE_DEVICE_SELF_ENCRYPTION_PROPERTY
dev_langs:
 - c++
---

## -description

**STORAGE_DEVICE_SELF_ENCRYPTION_PROPERTY** is the structure used when a caller sends [**IOCTL_STORAGE_QUERY_PROPERTY**](ni-ntddstor-ioctl_storage_query_property.md) to query whether a device supports self encryption.

## -struct-fields

### -field Version

Version of this structure. Set to ```sizeof(STORAGE_DEVICE_SELF_ENCRYPTION_PROPERTY)```.

### -field Size

Size of this structure, in bytes. Must be >= ```sizeof(STORAGE_DEVICE_SELF_ENCRYPTION_PROPERTY)```.

### -field SupportsSelfEncryption

Boolean value. This field is TRUE if the device supports self-encryption; otherwise it is FALSE.

## -remarks

**STORAGE_DEVICE_SELF_ENCRYPTION_PROPERTY** is used as the output buffer in which to return the result when a caller sends [**IOCTL_STORAGE_QUERY_PROPERTY**](ni-ntddstor-ioctl_storage_query_property.md) with a [**STORAGE_PROPERTY_ID**](ne-ntddstor-storage_property_id.md) value of **StorageDeviceSelfEncryptionProperty**.

## -see-also

[**IOCTL_STORAGE_QUERY_PROPERTY**](ni-ntddstor-ioctl_storage_query_property.md)

[**STORAGE_PROPERTY_ID**](ne-ntddstor-storage_property_id.md)

[**STORAGE_PROPERTY_QUERY**](ns-ntddstor-_storage_property_query.md)

[**STORAGE_QUERY_TYPE**](ne-ntddstor-_storage_query_type.md)
