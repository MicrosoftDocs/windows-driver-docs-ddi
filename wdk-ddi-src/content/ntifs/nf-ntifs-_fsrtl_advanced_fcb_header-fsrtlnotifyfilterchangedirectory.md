---
UID: NF:ntifs.FsRtlNotifyFilterChangeDirectory
title: FsRtlNotifyFilterChangeDirectory function (ntifs.h)
description: The FsRtlNotifyFilterChangeDirectory routine creates a notify structure for an IRP_MN_NOTIFY_CHANGE_DIRECTORY request and adds it to the specified notify list.
old-location: ifsk\fsrtlnotifyfilterchangedirectory.htm
tech.root: ifsk
ms.date: 02/21/2023
keywords: ["FsRtlNotifyFilterChangeDirectory function"]
ms.keywords: FsRtlNotifyFilterChangeDirectory, FsRtlNotifyFilterChangeDirectory routine [Installable File System Drivers], fsrtlref_ef37396f-2844-4b1e-a474-16788aa1de75.xml, ifsk.fsrtlnotifyfilterchangedirectory, ntifs/FsRtlNotifyFilterChangeDirectory
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows 2000 SP4 Update Rollup; Windows XP
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
req.irql: < APC_LEVEL
targetos: Windows
req.typenames: 
ms.custom: RS5
f1_keywords:
 - FsRtlNotifyFilterChangeDirectory
 - ntifs/FsRtlNotifyFilterChangeDirectory
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlNotifyFilterChangeDirectory
dev_langs:
 - c++
---

# FsRtlNotifyFilterChangeDirectory function

## -description

**FsRtlNotifyFilterChangeDirectory** creates a notify structure for an IRP_MN_NOTIFY_CHANGE_DIRECTORY request and adds it to the specified notify list.

## -parameters

### -param NotifySync [in]

Pointer to an opaque synchronization object for the change directory notify list that is pointed to by the **NotifyList** parameter.

### -param NotifyList [in]

Pointer to the head of the change directory notify list for the current volume. Each element in the list is an opaque notify structure.

### -param FsContext [in]

Pointer to a unique value assigned by the file system to identify the notify structure to be created as belonging to a particular file object. If a **TraverseCallback** routine is supplied, **FsContext** is passed as the **NotifyContext** parameter to that routine.

### -param FullDirectoryName [in]

Pointer to an ANSI or Unicode string that contains the full name for the directory associated with this notify structure. Ignored if **NotifyIrp** is NULL.

### -param WatchTree [in]

Set to TRUE if all subdirectories of this directory should also be watched. Set to FALSE if only the directory itself is to be watched. Ignored if **NotifyIrp** is NULL.

### -param IgnoreBuffer [in]

Set to TRUE to ignore any user buffers and force the directory to be reenumerated. This action speeds the operation. Ignored if **NotifyIrp** is NULL.

### -param CompletionFilter [in]

Bitmask of flags that specify the types of changes to files or directories that should cause the IRPs in the notify list to be completed. The following table describes the possible flag values.

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

Pointer to the IRP to be added to the notify list. If **NotifyIrp** is NULL, this means that the file stream represented by the file object (identified by the **FsContext** parameter) is being deleted.

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

Pointer to a [**SECURITY_SUBJECT_CONTEXT**](/windows-hardware/drivers/kernel/eprocess#security_subject_context) structure to be passed to **TraverseCallback**. **FsRtlNotifyFilterChangeDirectory** releases the context and frees the structure after using it. This parameter is ignored if **NotifyIrp** is NULL. If a **TraverseCallback** routine is supplied, **SubjectContext** is passed as the **SubjectContext** parameter to that routine.

### -param FilterCallback [in, optional]

Optional pointer to a callback routine to be invoked when a change occurs to the directory. If this callback routine returns TRUE, [**FsRtlNotifyFilterReportChange**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfilterreportchange.md) completes the pending IRP_MN_NOTIFY_CHANGE_DIRECTORY requests in the notify list; otherwise, it does not. Such a caller-supplied routine is declared as follows:

``` syntax
BOOLEAN
(*PFILTER_REPORT_CHANGE) (
    IN PVOID NotifyContext,                     // FsContext
    IN PVOID FilterContext                      // Context pointer
    );
```

## -remarks

**FsRtlNotifyFilterChangeDirectory** is called by a file system that has received an IRP with major function code [**IRP_MJ_DIRECTORY_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-directory-control), minor function code IRP_MN_NOTIFY_CHANGE_DIRECTORY.

The file system calls **FsRtlNotifyFilterChangeDirectory** to create a notify structure to hold the IRP and add the notify structure to the notify list for the current volume.

If **NotifyIrp** is NULL, **FsRtlNotifyFilterChangeDirectory** checks whether the notify list already contains any pending IRPs whose file objects match the given **FsContext** value and, if so, completes the IRPs with STATUS_DELETE_PENDING.

If **NotifyIrp** is not NULL, **FsRtlNotifyFilterChangeDirectory** does the following:

* Checks whether the IRP's file object has undergone cleanup. If so, **FsRtlNotifyFilterChangeDirectory** completes the IRP with status STATUS_NOTIFY_CLEANUP and does not add it to the notify list.

* If the IRP's file object has not undergone cleanup, **FsRtlNotifyFilterChangeDirectory** checks whether the notify list already contains a notify structure for the given **FsContext** value. If such a notify structure is found, and there are pending changes to report, **FsRtlNotifyFilterChangeDirectory** completes **NotifyIrp**. If a notify structure is found, but there are no pending changes to report, **FsRtlNotifyFilterChangeDirectory** marks the IRP pointed to by **NotifyIrp**  as pending and inserts it into the list of notify IRPs in the notify structure. If no such notify structure is found, **FsRtlNotifyFilterChangeDirectory** marks the IRP pointed to by **NotifyIrp**  as pending, creates a notify structure, and inserts it into the notify list.

When a change occurs to the directory, the file system calls [**FsRtlNotifyFilterReportChange**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfilterreportchange.md) to complete the pending IRP_MN_NOTIFY_CHANGE_DIRECTORY requests in the notify list.

## -see-also

[**FsRtlNotifyFilterReportChange**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfilterreportchange.md)

[**FsRtlNotifyFullChangeDirectory**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfullchangedirectory.md)

[**FsRtlNotifyFullReportChange**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfullreportchange.md)

[**IRP_MJ_DIRECTORY_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-directory-control)

[**SECURITY_SUBJECT_CONTEXT**](/windows-hardware/drivers/kernel/eprocess#security_subject_context)
