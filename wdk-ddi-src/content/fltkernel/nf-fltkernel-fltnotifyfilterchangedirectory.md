---
UID: NF:fltkernel.FltNotifyFilterChangeDirectory
title: FltNotifyFilterChangeDirectory function (fltkernel.h)
description: The FltNotifyFilterChangeDirectory routine creates a notify structure for an IRP_MN_NOTIFY_CHANGE_DIRECTORY operation and adds it to the specified notify list.
old-location: ifsk\fltnotifyfilterchangedirectory.htm
tech.root: ifsk
ms.assetid: bbeabd33-951e-4fd5-9845-cabed5f95fcd
ms.date: 04/16/2018
keywords: ["FltNotifyFilterChangeDirectory function"]
ms.keywords: FltApiRef_e_to_o_855490c1-8b4e-4973-9a96-808b50c20740.xml, FltNotifyFilterChangeDirectory, FltNotifyFilterChangeDirectory routine [Installable File System Drivers], fltkernel/FltNotifyFilterChangeDirectory, ifsk.fltnotifyfilterchangedirectory
req.header: fltkernel.h
req.include-header: Fltkernel.h
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltNotifyFilterChangeDirectory
 - fltkernel/FltNotifyFilterChangeDirectory
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltNotifyFilterChangeDirectory
---

# FltNotifyFilterChangeDirectory function


## -description

The <b>FltNotifyFilterChangeDirectory</b> routine creates a notify structure for an IRP_MN_NOTIFY_CHANGE_DIRECTORY operation and adds it to the specified notify list.

## -parameters

### -param NotifySync 

[in, out]
Pointer to an opaque synchronization object for the change directory notify list that the <i>NotifyList</i> parameter points to.

### -param NotifyList 

[in, out]
Pointer to the head of the change directory notify list for the current volume. Each element in the list is an opaque notify structure.

### -param FsContext 

[in]
Pointer to a unique value assigned by the caller to identify the notify structure to be created. If a callback routine is supplied in the <i>TraverseCallback</i> parameter, <i>FsContext</i> is passed as the <i>NotifyContext</i> parameter to that routine.

### -param FullDirectoryName 

[in]
Pointer to an ANSI or Unicode string that contains the full name for the directory associated with this notify structure.

### -param WatchTree 

[in]
Set to <b>TRUE</b> if all subdirectories of the directory that is specified by the <i>FullDirectoryName</i> parameter should also be watched. Set to <b>FALSE</b> if only the directory itself is to be watched.

### -param IgnoreBuffer 

[in]
Set to <b>TRUE</b> to ignore any user buffers and force the directory to be reenumerated. This action speeds the operation.

### -param CompletionFilter 

[in]
Bitmask of flags that specify the types of changes to files or directories that should cause the callback data structures in the notify list to be completed. The possible flag values are described in the following table.

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FILE_NOTIFY_CHANGE_FILE_NAME

</td>
<td>
A file has been added, deleted, or renamed in this directory.

</td>
</tr>
<tr>
<td>
FILE_NOTIFY_CHANGE_DIR_NAME

</td>
<td>
A subdirectory has been created, removed, or renamed.

</td>
</tr>
<tr>
<td>
FILE_NOTIFY_CHANGE_NAME

</td>
<td>
This directory's name has changed.

</td>
</tr>
<tr>
<td>
FILE_NOTIFY_CHANGE_ATTRIBUTES

</td>
<td>
The value of an attribute of this file, such as last access time, has changed.

</td>
</tr>
<tr>
<td>
FILE_NOTIFY_CHANGE_SIZE

</td>
<td>
This file's size has changed.

</td>
</tr>
<tr>
<td>
FILE_NOTIFY_CHANGE_LAST_WRITE

</td>
<td>
This file's last modification time has changed.

</td>
</tr>
<tr>
<td>
FILE_NOTIFY_CHANGE_LAST_ACCESS

</td>
<td>
This file's last access time has changed.

</td>
</tr>
<tr>
<td>
FILE_NOTIFY_CHANGE_CREATION

</td>
<td>
This file's creation time has changed.

</td>
</tr>
<tr>
<td>
FILE_NOTIFY_CHANGE_EA

</td>
<td>
This file's extended attributes have been modified.

</td>
</tr>
<tr>
<td>
FILE_NOTIFY_CHANGE_SECURITY

</td>
<td>
This file's security information has changed.

</td>
</tr>
<tr>
<td>
FILE_NOTIFY_CHANGE_STREAM_NAME

</td>
<td>
A file stream has been added, deleted, or renamed in this directory.

</td>
</tr>
<tr>
<td>
FILE_NOTIFY_CHANGE_STREAM_SIZE

</td>
<td>
This file stream's size has changed.

</td>
</tr>
<tr>
<td>
FILE_NOTIFY_CHANGE_STREAM_WRITE

</td>
<td>
This file stream's data has changed.

</td>
</tr>
</table>

### -param NotifyCallbackData 

[in]
Pointer to the callback data structure for the operation to be added to the notify list. This parameter is required and cannot be <b>NULL</b>.

### -param TraverseCallback 

[in, optional]
Optional pointer to a callback routine to be invoked when a change occurs in a subdirectory that is being watched in a directory tree. This pointer lets the file system check whether the watcher has traverse access to that directory. Such a caller-supplied routine is declared as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
(*PCHECK_FOR_TRAVERSE_ACCESS) (
    IN PVOID NotifyContext,                     // FsContext
    IN PVOID TargetContext,                     // Context pointer
    IN PSECURITY_SUBJECT_CONTEXT SubjectContext // SubjectContext
    );</pre>
</td>
</tr>
</table></span></div>
For more information about the <i>TargetContext</i> parameter, see the <i>TargetContext</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfullreportchange">FsRtlNotifyFullReportChange</a> routine.

### -param SubjectContext 

[in, optional]
Pointer to a context structure to be passed to <i>TraverseCallback</i>. <b>FltNotifyFilterChangeDirectory</b> releases the context and frees the structure after using it. If a <i>TraverseCallback</i> routine is supplied, <i>SubjectContext</i> is passed as the <i>SubjectContext</i> parameter to that routine.

### -param FilterCallback 

[in, optional]
Optional pointer to a callback routine to be invoked when a change occurs to the directory. If this callback routine returns <b>TRUE</b>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfilterreportchange">FsRtlNotifyFilterReportChange</a> completes the pending IRP_MN_NOTIFY_CHANGE_DIRECTORY operations in the notify list; otherwise, it does not. Such a caller-supplied routine is declared as follows: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>BOOLEAN
(*PFILTER_REPORT_CHANGE) (
    IN PVOID NotifyContext,                     // FsContext
    IN PVOID FilterContext                      // Context pointer
    );</pre>
</td>
</tr>
</table></span></div>

## -returns

None

## -remarks

A minifilter driver can call <b>FltNotifyFilterChangeDirectory</b> from the preoperation callback routine (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_pre_operation_callback">PFLT_PRE_OPERATION_CALLBACK</a>) that it registered to process notify change directory operations. These operations have a major function code of <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-directory-control">IRP_MJ_DIRECTORY_CONTROL</a> and a minor function code of  IRP_MN_NOTIFY_CHANGE_DIRECTORY. 

The minifilter driver calls <b>FltNotifyFilterChangeDirectory</b> to create a notify structure to hold the callback data structure for the operation and add the notify structure to the notify list for the current volume. 

<b>FltNotifyFilterChangeDirectory</b> does the following:

<ul>
<li>
Checks whether the operation's file object has been cleaned up. If so, <b>FltNotifyFilterChangeDirectory</b> completes the operation with status STATUS_NOTIFY_CLEANUP and does not add it to the notify list. 

</li>
<li>
If the operation's file object has not been cleaned up, <b>FltNotifyFilterChangeDirectory</b> checks whether the notify list already contains a notify structure for the given <i>FsContext</i> value. If such a notify structure is found, and there are pending changes to report, <b>FltNotifyFilterChangeDirectory</b> completes the callback data structure pointed to by the <i>NotifyCallbackData</i> parameter. If a notify structure is found, but there are no pending changes to report, <b>FltNotifyFilterChangeDirectory</b> adds the operation to the notify structure. If no such notify structure is found, <b>FltNotifyFilterChangeDirectory</b> creates a notify structure for the operation and inserts it into the list. 

</li>
</ul>
When a change occurs to the directory, the file system calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfilterreportchange">FsRtlNotifyFilterReportChange</a> to complete the pending IRP_MN_NOTIFY_CHANGE_DIRECTORY operations in the notify list.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfilterreportchange">FsRtlNotifyFilterReportChange</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-directory-control">IRP_MJ_DIRECTORY_CONTROL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_pre_operation_callback">PFLT_PRE_OPERATION_CALLBACK</a>

