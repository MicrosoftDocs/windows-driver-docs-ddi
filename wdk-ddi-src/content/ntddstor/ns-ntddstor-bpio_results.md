---
UID: NS:ntddstor._BPIO_RESULTS
tech.root: storage
title: BPIO_RESULTS
ms.date: 07/08/2021
targetos: Windows
description: The BPIO_RESULTS structure defines BypassIO operation-specific outputs for BPIO_OP_ENABLE and BPIO_OP_QUERY operations when a driver is failing the operation.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntddstor.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11
req.target-min-winversvr: 
req.target-type: 
req.typenames: BPIO_RESULTS, *PBPIO_RESULTS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - _BPIO_RESULTS
 - PBPIO_RESULTS
 - BPIO_RESULTS
f1_keywords:
 - _BPIO_RESULTS
 - ntddstor/_BPIO_RESULTS
 - PBPIO_RESULTS
 - ntddstor/PBPIO_RESULTS
 - BPIO_RESULTS
 - ntddstor/BPIO_RESULTS
dev_langs:
 - c++
---

## -description

The **BPIO_RESULTS** structure defines BypassIO operation-specific outputs for [**BPIO_OP_ENABLE** and **BPIO_OP_QUERY** operations](ne-ntddstor-bpio_operations.md) when a driver is failing the operation.

## -struct-fields

### -field OpStatus

Receives a NTSTATUS code available to the caller that identifies why the failing driver cannot support BypassIO. This field should only be set by the first driver to fail the enable/query request.

### -field FailingDriverNameLen

Receives the length of the string stored in **FailingDriverName**, in characters.

### -field FailingDriverName

Receives a string that specifies the name of the driver that failed the request. For diagnostic reasons, a driver must store its name when it fails a [**BPIO_OP_ENABLE** or **BPIO_OP_QUERY** operation](ne-ntddstor-bpio_operations.md). The name must match the actual name of the driver that is used by the system; for example, *ntfs.sys*. This string is not guaranteed to be NULL-terminated.

### -field FailureReasonLen

Receives the length of the string stored in **FailingReason**, in characters.

### -field FailureReason

Receives a unique, descriptive string describing why the driver vetoed the enable/query request. This string is used for diagnostic reasons, and should be in English so that it does not need to be localized. This string is not guaranteed to be NULL-terminated.

## -remarks

See [BypassIO for storage drivers](/windows-hardware/drivers/storage/bypassio) for more information.

## -see-also

[**BPIO_OPERATIONS**](ne-ntddstor-bpio_operations.md)

[**IOCTL_STORAGE_MANAGE_BYPASS_IO**](../ntddstor/ni-ntddstor-ioctl_storage_manage_bypass_io.md)
