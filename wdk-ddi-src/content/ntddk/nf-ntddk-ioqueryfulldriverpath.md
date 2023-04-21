---
UID: NF:ntddk.IoQueryFullDriverPath
title: IoQueryFullDriverPath function (ntddk.h)
description: The IoQueryFullDriverPath routine retrieves the full path name of the binary file that is loaded for the specified driver object.
tech.root: kernel
ms.date: 04/20/2023
keywords: ["IoQueryFullDriverPath function"]
ms.keywords: IoQueryFullDriverPath, IoQueryFullDriverPath routine [Kernel-Mode Driver Architecture], kernel.ioqueryfulldriverpath, wdm/IoQueryFullDriverPath
req.header: ntddk.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.1.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoQueryFullDriverPath
 - ntddk/IoQueryFullDriverPath
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoQueryFullDriverPath
---

## -description

The **IoQueryFullDriverPath** routine retrieves the full path name of the binary file that is loaded for the specified driver object. Starting in Windows 10 version 1709, callers may query for driver objects that are not their own, as long as they use proper synchronization to ensure that the DRIVER_OBJECT structure remains valid during the call.

## -parameters

### -param DriverObject [in]

A pointer to a [**DRIVER_OBJECT**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_driver_object) structure. If you are calling **IoQueryFullDriverPath** on a computer running a version of Windows 10 earlier than version 1709, this structure is required to be the driver object for the calling driver.

### -param FullPath [out]

A pointer to a caller-allocated [**UNICODE_STRING**](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) structure. On successful return, this structure contains the path name.

## -returns

**IoQueryFullDriverPath** returns STATUS_SUCCESS if the call successfully fetches the path name. Possible error return values include the following status codes.

| Return code | Description |
|--|--|
| **STATUS_ACCESS_DENIED** | The target driver object does not belong to the caller. This status code is only returned on versions of Windows 10 earlier than 1709. |
| **STATUS_NOT_FOUND** | The driver object has no section (loaded memory image) associated with it. |
| **STATUS_INSUFFICIENT_RESOURCES** | Insufficient resources are available to perform the requested operation. |

## -remarks

A driver can call this routine to query for the full path name of its binary file, or, starting in Windows 10 version 1709, the full path name of the binary file for another driver.

The caller allocates the [**UNICODE_STRING**](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) structure pointed to by the *FullPath* parameter, but does not need to initialize this structure. **IoQueryFullDriverPath** assumes that the original contents of this structure are invalid and overwrites them. This routine allocates a string buffer from paged system memory, sets the **Buffer** member of the structure to point to this buffer, and sets the **MaximumLength** and **Buffer** members to describe the buffer and its contents.

The caller is responsible for freeing the storage pointed to by *FullPath*->**Buffer** when the full path string is no longer needed. Typically, the caller frees this storage by calling a routine such as [ExFreePool](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool).

## -see-also

[**DRIVER_OBJECT**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_driver_object)

[ExFreePool](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool)

[**UNICODE_STRING**](/windows/win32/api/ntdef/ns-ntdef-_unicode_string)
