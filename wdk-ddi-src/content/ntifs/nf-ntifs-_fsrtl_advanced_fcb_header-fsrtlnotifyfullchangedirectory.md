---
UID: NF:ntifs.FsRtlNotifyFullChangeDirectory
title: FsRtlNotifyFullChangeDirectory function (ntifs.h)
description: The FsRtlNotifyFullChangeDirectory routine creates a notify structure for a notification request and adds it to the specified notify list.
old-location: ifsk\fsrtlnotifyfullchangedirectory.htm
tech.root: ifsk
ms.date: 02/21/2023
keywords: ["FsRtlNotifyFullChangeDirectory function"]
ms.keywords: FsRtlNotifyFullChangeDirectory, FsRtlNotifyFullChangeDirectory routine [Installable File System Drivers], fsrtlref_551aff27-746f-49a4-b427-fa273249c36e.xml, ifsk.fsrtlnotifyfullchangedirectory, rxprocs/FsRtlNotifyFullChangeDirectory
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
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
ms.custom: RS5
f1_keywords:
 - FsRtlNotifyFullChangeDirectory
 - ntifs/FsRtlNotifyFullChangeDirectory
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlNotifyFullChangeDirectory
dev_langs:
 - c++
---

# FsRtlNotifyFullChangeDirectory function

## -description

The **FsRtlNotifyFullChangeDirectory** routine creates a notify structure for a notification request and adds it to the specified notify list.

## -parameters

### -param NotifySync [in]

A pointer to an opaque synchronization object for the notify list for the current volume.

### -param NotifyList [in]

A pointer to the head of a notify list. Each element in the list is an opaque notify structure.

### -param FsContext [in]

A pointer to a unique value assigned by the file system to identify the notify structure to be created as belonging to a particular file object. If a **TraverseCallback** routine is supplied, **FsContext** is passed as the **NotifyContext** parameter to that routine.

### -param FullDirectoryName [in]

A pointer to an ANSI or Unicode string that contains the full name for the directory associated with this notify structure. Ignored if **NotifyIrp** is NULL.

### -param WatchTree [in]

Set to TRUE if all subdirectories of this directory should also be watched. Set to FALSE if only the directory itself is to be watched. Ignored if **NotifyIrp** is NULL.

### -param IgnoreBuffer [in]

Set to TRUE to ignore any user buffers and force the directory to be reenumerated. This action speeds the operation. Ignored if **NotifyIrp** is NULL.

### -param CompletionFilter [in]

Bitmask of flags that specify the types of changes to files or subdirectories that should cause the queue of pending notify IRPs to be completed. The following table describes the possible flag values.

| Flag | Meaning |
| ---- | ------- |
| FILE_NOTIFY_CHANGE_FILE_NAME (0x0001)    | A file has been added, deleted, or renamed in this directory. |
| FILE_NOTIFY_CHANGE_DIR_NAME  (0x0002)    | A subdirectory has been created, removed, or renamed. |
| FILE_NOTIFY_CHANGE_NAME (0x0003)         | This directory's name has changed. |
| FILE_NOTIFY_CHANGE_ATTRIBUTES (0x0004)   | The value of an attribute of this file, such as last access time, has changed. |
| FILE_NOTIFY_CHANGE_SIZE (0x0008)         | This file's size has changed. |
| FILE_NOTIFY_CHANGE_LAST_WRITE (0x0010)   | This file's last modification time has changed. |
| FILE_NOTIFY_CHANGE_LAST_ACCESS (0x0020)  | This file's last access time has changed. |
| FILE_NOTIFY_CHANGE_CREATION (0x0040)     | This file's creation time has changed. |
| FILE_NOTIFY_CHANGE_EA (0x0080)           | This file's extended attributes have been modified. |
| FILE_NOTIFY_CHANGE_SECURITY (0x0100)     | This file's security information has changed. |
| FILE_NOTIFY_CHANGE_STREAM_NAME (0x0200)  | A file stream has been added, deleted, or renamed in this directory. |
| FILE_NOTIFY_CHANGE_STREAM_SIZE (0x0400)  | This file stream's size has changed. |
| FILE_NOTIFY_CHANGE_STREAM_WRITE (0x0800) | This file stream's data has changed. |

**CompletionFilter** is ignored if **NotifyIrp** is NULL.

### -param NotifyIrp [in, optional]

A pointer to the IRP to complete on notify change. If **NotifyIrp** is NULL, this means that the file stream represented by this file object is being deleted.

### -param TraverseCallback [in, optional]

Optional pointer to a callback routine to be invoked when a change occurs in a subdirectory being watched in a directory tree. This lets the file system check whether the watcher has traverse access to that directory. Such a caller-supplied routine is declared as follows:

``` syntax
NTSTATUS
(*PCHECK_FOR_TRAVERSE_ACCESS) (
    IN PVOID NotifyContext,                     // FsContext
    IN PVOID TargetContext,                     // Context pointer
    IN PSECURITY_SUBJECT_CONTEXT SubjectContext // SubjectContext
    );
```

For more information about the **TargetContext** parameter, see the **TargetContext** parameter of [**FsRtlNotifyFullReportChange**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfullreportchange.md). **TraverseCallback** is ignored if **NotifyIrp** is NULL.

### -param SubjectContext [in, optional]

A pointer to a [**SECURITY_SUBJECT_CONTEXT**](/windows-hardware/drivers/kernel/eprocess#security_subject_context) structure to be passed to **TraverseCallback**. **FsRtlNotifyFullChangeDirectory** releases the context and frees the structure after using it. Ignored if **NotifyIrp** is NULL. If a **TraverseCallback** routine is supplied, **SubjectContext** is passed as the **SubjectContext** parameter to that routine.

## -remarks

**FsRtlNotifyFullChangeDirectory** is called by a file system that has received a notify change request. This request is received as an IRP with major function code IRP_MJ_DIRECTORY_CONTROL, minor function code IRP_MN_NOTIFY_CHANGE_DIRECTORY.

If **NotifyIrp** is NULL, **FsRtlNotifyFullChangeDirectory** checks whether the notify list contains a pending IRP that refers to this file object and, if so, completes it with STATUS_DELETE_PENDING.

If **NotifyIrp** is not NULL, **FsRtlNotifyFullChangeDirectory** does the following:

* Checks whether the file object has undergone cleanup. If so, **FsRtlNotifyFullChangeDirectory** completes the notify IRP with status STATUS_NOTIFY_CLEANUP.

* If the file object has not undergone cleanup, **FsRtlNotifyFullChangeDirectory** checks whether the notify list for this volume already contains a notify structure for this change. If so, **FsRtlNotifyFullChangeDirectory** completes any pending IRPs. If not, **FsRtlNotifyFullChangeDirectory** marks the notify IRP as pending, creates a notify structure, and inserts it into the list.

## -see-also

[**FsRtlNotifyFullReportChange**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfullreportchange.md)

[**IRP_MJ_DIRECTORY_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-directory-control)

[**SECURITY_SUBJECT_CONTEXT**](/windows-hardware/drivers/kernel/eprocess#security_subject_context)
