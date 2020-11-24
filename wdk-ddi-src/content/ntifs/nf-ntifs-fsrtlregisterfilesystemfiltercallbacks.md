---
UID: NF:ntifs.FsRtlRegisterFileSystemFilterCallbacks
title: FsRtlRegisterFileSystemFilterCallbacks function (ntifs.h)
description: File system filter drivers and file systems call the FsRtlRegisterFileSystemFilterCallbacks routine to register notification callback routines to be invoked when the underlying file system performs certain operations.
old-location: ifsk\fsrtlregisterfilesystemfiltercallbacks.htm
tech.root: ifsk
ms.assetid: cd6d2ab6-ce17-47db-b5d0-4f9543e15487
ms.date: 11/23/2020
keywords: ["FsRtlRegisterFileSystemFilterCallbacks function"]
ms.keywords: FsRtlRegisterFileSystemFilterCallbacks, FsRtlRegisterFileSystemFilterCallbacks routine [Installable File System Drivers], fsrtlref_a831a0f3-f819-45e3-9121-ae50ef1b95bf.xml, ifsk.fsrtlregisterfilesystemfiltercallbacks, ntifs/FsRtlRegisterFileSystemFilterCallbacks
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows XP and later versions of the Windows operating system.
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FsRtlRegisterFileSystemFilterCallbacks
 - ntifs/FsRtlRegisterFileSystemFilterCallbacks
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlRegisterFileSystemFilterCallbacks
---

# FsRtlRegisterFileSystemFilterCallbacks function

## -description

File system filter drivers and file systems call the **FsRtlRegisterFileSystemFilterCallbacks** routine to register notification callback routines to be invoked when the underlying file system performs certain operations.

## -parameters

### -param FilterDriverObject

[in] A pointer to the driver object for the filter or file system driver.

### -param Callbacks

[in] Pointer to a [**FS_FILTER_CALLBACKS**](ns-ntifs-fs_filter_callbacks.md) structure that contains the entry points of caller-supplied notification callback routines. All of the callback entry points are optional and can be set to **NULL**.

## -returns

The **FsRtlRegisterFileSystemFilterCallbacks** routine can return one of the following status values:

| Return code | Description |
| ----------- | ----------- |
| STATUS_SUCCESS | The callback routines were successfully registered. |
| STATUS_INSUFFICIENT_RESOURCES | **FsRtlRegisterFileSystemFilterCallbacks** encountered a pool allocation failure when allocating memory to store the callback information. |
| STATUS_FSFILTER_OP_COMPLETED_SUCCESSFULLY | **FsRtlRegisterFileSystemFilterCallbacks** successfully completed an FsFilter operation. |
| STATUS_FILE_LOCKED_WITH_ONLY_READERS | The file was locked and all users of the file can only read. |
| STATUS_FILE_LOCKED_WITH_WRITERS | The file was locked and at least one user of the file can write |
| STATUS_INVALID_PARAMETER | One of the parameters is invalid. |

## -remarks

File system and file system filter drivers should call **FsRtlRegisterFileSystemFilterCallbacks** from the driver's **DriverEntry** routine.  

**FsRtlRegisterFileSystemFilterCallbacks** registers the notification callback routines that were specified in the **Callbacks** parameter to be invoked when requests for certain file operations are sent to the underlying file system.

File systems call **FsRtlRegisterFileSystemFilterCallbacks** to set the **PreAcquireForSectionSynchronization** callback member of the [**FS_FILTER_CALLBACKS**](ns-ntifs-fs_filter_callbacks.md) structure instead of using the obsolete **AcquireFileForNtCreateSection**.

The callback routines registered by **FsRtlRegisterFileSystemFilterCallbacks** supersede the following fast I/O callback routines, which are obsolete and should not be used by file system filter drivers:

* **AcquireForCcFlush**
* **AcquireFileForNtCreateSection**
* **AcquireForModWrite**
* **ReleaseForCcFlush**
* **ReleaseFileForNtCreateSection**
* **ReleaseForModWrite**

## -see-also

[**FS_FILTER_CALLBACKS**](ns-ntifs-fs_filter_callbacks.md)
