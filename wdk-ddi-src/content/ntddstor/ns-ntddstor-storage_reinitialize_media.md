---
UID: NS:ntddstor._STORAGE_REINITIALIZE_MEDIA
tech.root: storage
title: STORAGE_REINITIALIZE_MEDIA
ms.date: 05/13/2021
targetos: Windows
description: STORAGE_REINITIALIZE_MEDIA is an optional structure that contains sanitize parameters for IOCTL_STORAGE_REINITIALIZE_MEDIA.
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
req.typenames: STORAGE_REINITIALIZE_MEDIA, *PSTORAGE_REINITIALIZE_MEDIA
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - _STORAGE_REINITIALIZE_MEDIA
 - PSTORAGE_REINITIALIZE_MEDIA
 - STORAGE_REINITIALIZE_MEDIA
f1_keywords:
 - _STORAGE_REINITIALIZE_MEDIA
 - ntddstor/_STORAGE_REINITIALIZE_MEDIA
 - PSTORAGE_REINITIALIZE_MEDIA
 - ntddstor/PSTORAGE_REINITIALIZE_MEDIA
 - STORAGE_REINITIALIZE_MEDIA
 - ntddstor/STORAGE_REINITIALIZE_MEDIA
dev_langs:
 - c++
---

## -description

STORAGE_REINITIALIZE_MEDIA is an optional structure that contains sanitize parameters for [**IOCTL_STORAGE_REINITIALIZE_MEDIA**](ni-ntddstor-ioctl_storage_reinitialize_media.md).

## -struct-fields

### -field Version

The version of this structure. Set to ```sizeof(STORAGE_REINITIALIZE_MEDIA)```.

### -field Size

The size of this structure, in bytes. Set to ```sizeof(STORAGE_REINITIALIZE_MEDIA)```.

### -field TimeoutInSeconds

Time out value for the sanitize, in seconds.

### -field SanitizeOption

Structure that specifies sanitize operation options. **SanitizeOption** only applies to NVMe devices.

### -field SanitizeOption.SanitizeMethod

A [**STORAGE_SANITIZE_METHOD**](ne-ntddstor-storage_sanitize_method.md) value that specifies the sanitize method to use.

### -field SanitizeOption.DisallowUnrestrictedSanitizeExit

Indicates whether unrestricted sanitize exit is allowed. By default, unrestricted sanitize exit is allowed (set to 1).

### -field SanitizeOption.Reserved

Reserved. Do not use.

## -see-also

[**IOCTL_STORAGE_REINITIALIZE_MEDIA**](ni-ntddstor-ioctl_storage_reinitialize_media.md)

[**STORAGE_SANITIZE_METHOD**](ne-ntddstor-storage_sanitize_method.md)
