---
UID: NS:ntddstor._STORAGE_DIAGNOSTIC_REQUEST
title: _STORAGE_DIAGNOSTIC_REQUEST (ntddstor.h)
description: Describes a diagnostic request about the storage driver stack. The STORAGE_DIAGNOSTIC_REQUEST structure is provided in the input buffer of an IOCTL_STORAGE_DIAGNOSTIC request.
old-location: storage\storage_diagnostic_request.htm
tech.root: storage
ms.assetid: BAC83B5C-4F14-430D-9CEF-46812FC4DFED
ms.date: 03/29/2018
keywords: ["STORAGE_DIAGNOSTIC_REQUEST structure"]
ms.keywords: "*PSTORAGE_DIAGNOSTIC_REQUEST, PSTORAGE_DIAGNOSTIC_REQUEST, PSTORAGE_DIAGNOSTIC_REQUEST structure pointer [Storage Devices], STORAGE_DIAGNOSTIC_REQUEST, STORAGE_DIAGNOSTIC_REQUEST structure [Storage Devices], _STORAGE_DIAGNOSTIC_REQUEST, ntddstor/PSTORAGE_DIAGNOSTIC_REQUEST, ntddstor/STORAGE_DIAGNOSTIC_REQUEST, storage.storage_diagnostic_request"
req.header: ntddstor.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10, version 1709.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: STORAGE_DIAGNOSTIC_REQUEST, *PSTORAGE_DIAGNOSTIC_REQUEST
f1_keywords:
 - _STORAGE_DIAGNOSTIC_REQUEST
 - ntddstor/_STORAGE_DIAGNOSTIC_REQUEST
 - PSTORAGE_DIAGNOSTIC_REQUEST
 - ntddstor/PSTORAGE_DIAGNOSTIC_REQUEST
 - STORAGE_DIAGNOSTIC_REQUEST
 - ntddstor/STORAGE_DIAGNOSTIC_REQUEST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - STORAGE_DIAGNOSTIC_REQUEST
---

# _STORAGE_DIAGNOSTIC_REQUEST structure

## -description

Describes a diagnostic request about the storage driver stack. The **STORAGE_DIAGNOSTIC_REQUEST** structure is provided in the input buffer of an [**IOCTL_STORAGE_DIAGNOSTIC**](ni-ntddstor-ioctl_storage_diagnostic.md) request.

## -struct-fields

### -field Version

Version of this structure.

### -field Size

Specifies the whole size of the structure and the associated data buffer.

### -field Reserved

Reserved for future use.

### -field TargetType

Specifies the request target type. See definitions for [**STORAGE_DIAGNOSTIC_TARGET_TYPE**](ne-ntddstor-_storage_diagnostic_target_type.md).

### -field Level

Specifies the Diagnostic level. See definitions for [**STORAGE_DIAGNOSTIC_LEVEL**](ne-ntddstor-_storage_diagnostic_level.md).

## -see-also

[**IOCTL_STORAGE_DIAGNOSTIC**](ni-ntddstor-ioctl_storage_diagnostic.md)

[**STORAGE_DIAGNOSTIC_DATA**](ns-ntddstor-_storage_diagnostic_data.md)

[**STORAGE_DIAGNOSTIC_LEVEL**](ne-ntddstor-_storage_diagnostic_level.md)

[**STORAGE_DIAGNOSTIC_TARGET_TYPE**](ne-ntddstor-_storage_diagnostic_target_type.md)
