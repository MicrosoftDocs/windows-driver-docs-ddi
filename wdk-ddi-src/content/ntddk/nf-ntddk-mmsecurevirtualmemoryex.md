---
UID: NF:ntddk.MmSecureVirtualMemoryEx
title: MmSecureVirtualMemoryEx function
description: This routine probes the requested address range and protects the specified address range from having its protection made more restrictive and being deleted.
tech.root: kernel
ms.date: 08/19/2019
keywords: ["MmSecureVirtualMemoryEx function"]
ms.keywords: MmSecureVirtualMemoryEx
req.header: ntddk.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: APC_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - MmSecureVirtualMemoryEx
 - ntddk/MmSecureVirtualMemoryEx
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - ntddk.h
api_name:
 - MmSecureVirtualMemoryEx
product:
 - Windows
---

# MmSecureVirtualMemoryEx function


## -description

This routine probes the requested address range and protects the specified address range from having its protection made more restrictive and being deleted.

## -parameters

### -param Address

Pointer to the base address to probe and secure.

### -param Size

Specifies the size, in bytes, of the range to secure.

### -param ProbeMode

Specifies the most restrictive page protection that is allowed. Use PAGE_READWRITE to specify that the address range must remain both readable and writable, or use PAGE_READONLY to specify that the address range must only remain readable.

|ProbeMode|Meaning|
|--- |--- |
|PAGE_READWRITE|Protection cannot be changed to PAGE_NOACCESS or PAGE_READONLY. All other protection changes are allowed.|
|PAGE_READONLY|Protection cannot be changed to PAGE_NOACCESS. All other protection changes are allowed.|

### -param Flags

Specifies one or more of the following  flags:

|Flag|Description|
|--- |--- |
|**MM_SECURE_EXCLUSIVE**|Securing only succeeds if there are no other secures already pinned anywhere onto the VAD in question.|
|**MM_SECURE_NO_CHANGE**|Once applied, no protection changes are allowed for the supplied virtual address region.  The region can still be deleted if the process is exiting.|
|**MM_SECURE_USER_MODE_ONLY**|The protection specified by this securing will only be applied to subsequent calls from user mode that are trying to change the protection (kernel mode callers will bypass this securing).|
|**MM_SECURE_NO_INHERIT**|If the process is cloned, then unlike the parent process, VAD of the child process will not be secured.|

## -returns

Returns a value resembling a handle to be used only to unsecure the range.

If the range could not be locked because of protection problems, noncommitted memory or invalid parameters, this routine returns NULL.

## -remarks

Use **MmSecureVirtualMemoryEx** instead of [**MmSecureVirtualMemory**](./nf-ntddk-mmsecurevirtualmemory.md) if you need to specify **MM_SECURE_NO_CHANGE** so that no protection change will be allowed on the supplied view.

The return value from this function can only be used with [**MmUnsecureVirtualMemory**](./nf-ntddk-mmunsecurevirtualmemory.md). The driver calls that routine to return the range to a normal state.

## -see-also

- [**MmSecureVirtualMemory**](./nf-ntddk-mmsecurevirtualmemory.md)
- [**MmUnsecureVirtualMemory**](./nf-ntddk-mmunsecurevirtualmemory.md)
