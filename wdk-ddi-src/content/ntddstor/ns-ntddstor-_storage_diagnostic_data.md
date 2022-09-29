---
UID: NS:ntddstor._STORAGE_DIAGNOSTIC_DATA
title: STORAGE_DIAGNOSTIC_DATA (ntddstor.h)
description: Describes diagnostic data about the storage driver stack. The STORAGE_DIAGNOSTIC_DATA structure is provided in the output buffer of an IOCTL_STORAGE_DIAGNOSTIC request.
old-location: storage\storage_diagnostic_data.htm
tech.root: storage
ms.date: 12/16/2021
keywords: ["STORAGE_DIAGNOSTIC_DATA structure"]
ms.keywords: "*PSTORAGE_DIAGNOSTIC_DATA, PSTORAGE_DIAGNOSTIC_DATA, PSTORAGE_DIAGNOSTIC_DATA structure pointer [Storage Devices], STORAGE_DIAGNOSTIC_DATA, STORAGE_DIAGNOSTIC_DATA structure [Storage Devices], _STORAGE_DIAGNOSTIC_DATA, ntddstor/PSTORAGE_DIAGNOSTIC_DATA, ntddstor/STORAGE_DIAGNOSTIC_DATA, storage.storage_diagnostic_data"
req.header: ntddstor.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
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
req.typenames: STORAGE_DIAGNOSTIC_DATA, *PSTORAGE_DIAGNOSTIC_DATA
f1_keywords:
 - _STORAGE_DIAGNOSTIC_DATA
 - ntddstor/_STORAGE_DIAGNOSTIC_DATA
 - PSTORAGE_DIAGNOSTIC_DATA
 - ntddstor/PSTORAGE_DIAGNOSTIC_DATA
 - STORAGE_DIAGNOSTIC_DATA
 - ntddstor/STORAGE_DIAGNOSTIC_DATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - _STORAGE_DIAGNOSTIC_DATA
 - PSTORAGE_DIAGNOSTIC_DATA
 - STORAGE_DIAGNOSTIC_DATA
---

# STORAGE_DIAGNOSTIC_DATA structure

## -description

**STORAGE_DIAGNOSTIC_DATA** describes diagnostic data about the storage driver stack. It is provided in the output buffer of an [**IOCTL_STORAGE_DIAGNOSTIC**](ni-ntddstor-ioctl_storage_diagnostic.md) request.

## -struct-fields

### -field Version

Version of this structure. Set to ```sizeof(STORAGE_DIAGNOSTIC_DATA)```.

### -field Size

Specifies the whole size of the structure and the associated data buffer, in bytes.

### -field ProviderId

Specifies the GUID of a diagnostic data provider.

### -field BufferSize

The driver should set **BufferSize** as follows:

* If the request is successful, set with the returned buffer size of **DiagnosticDataBuffer**.
* If the request failed because of buffer too small, set with the required buffer size for a **DiagnosticDataBuffer** needed by the provider.
* If the request failed for any other reason, clear to zero.

### -field Reserved

Reserved for future use.

### -field DiagnosticDataBuffer

Specifies the Diagnostic data buffer.

## -see-also

[**IOCTL_STORAGE_DIAGNOSTIC**](ni-ntddstor-ioctl_storage_diagnostic.md)

[**STORAGE_DIAGNOSTIC_REQUEST**](ns-ntddstor-_storage_diagnostic_request.md)
