---
UID: NF:ntifs.FsRtlNotifyFilterChangeDirectory
title: FsRtlNotifyFilterChangeDirectory function (ntifs.h)
description: The FsRtlNotifyFilterChangeDirectory routine creates a notify structure for an IRP_MN_NOTIFY_CHANGE_DIRECTORY request and adds it to the specified notify list.
old-location: ifsk\fsrtlnotifyfilterchangedirectory.htm
tech.root: ifsk
ms.assetid: 445b6836-aeac-4183-ba11-a787c1e125ac
ms.date: 04/16/2018
ms.keywords: FsRtlNotifyFilterChangeDirectory, FsRtlNotifyFilterChangeDirectory routine [Installable File System Drivers], fsrtlref_ef37396f-2844-4b1e-a474-16788aa1de75.xml, ifsk.fsrtlnotifyfilterchangedirectory, ntifs/FsRtlNotifyFilterChangeDirectory
f1_keywords:
 - "ntifs/FsRtlNotifyFilterChangeDirectory"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Update Rollup for Windows 2000 Service Pack 4 (SP4) and on Windows XP and later.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlNotifyFilterChangeDirectory
product:
- Windows
targetos: Windows
req.typenames: 
dev_langs:
 - c++
ms.custom: RS5
---

# FsRtlNotifyFilterChangeDirectory function


## -description


The <b>FsRtlNotifyFilterChangeDirectory</b> routine creates a notify structure for an IRP_MN_NOTIFY_CHANGE_DIRECTORY request and adds it to the specified notify list.


## -parameters




### -param NotifySync [in]

Pointer to an opaque synchronization object for the change directory notify list that is pointed to by the <i>NotifyList</i> parameter. 


### -param NotifyList [in]

Pointer to the head of the change directory notify list for the current volume. Each element in the list is an opaque notify structure. 


### -param FsContext [in]

Pointer to a unique value assigned by the file system to identify the notify structure to be created as belonging to a particular file object. If a <i>TraverseCallback</i> routine is supplied, <i>FsContext</i> is passed as the <i>NotifyContext</i> parameter to that routine. 


### -param FullDirectoryName [in]

Pointer to an ANSI or Unicode string that contains the full name for the directory associated with this notify structure. Ignored if <i>NotifyIrp</i> is <b>NULL</b>.


### -param WatchTree [in]

Set to <b>TRUE</b> if all subdirectories of this directory should also be watched. Set to <b>FALSE</b> if only the directory itself is to be watched. Ignored if <i>NotifyIrp</i> is <b>NULL</b>.


### -param IgnoreBuffer [in]

Set to <b>TRUE</b> to ignore any user buffers and force the directory to be reenumerated. This action speeds the operation. Ignored if <i>NotifyIrp</i> is <b>NULL</b>.


### -param CompletionFilter [in]

Bitmask of flags that specify the types of changes to files or directories that should cause the IRPs in the notify list to be completed. The possible flag values are described following.

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
 

<i>CompletionFilter</i> is ignored if <i>NotifyIrp</i> is <b>NULL</b>.


### -param NotifyIrp [in, optional]

Pointer to the IRP to be added to the notify list. If <i>NotifyIrp</i> is <b>NULL</b>, this means that the file stream represented by the file object (identified by the <i>FsContext</i> parameter) is being deleted.


### -param TraverseCallback [in, optional]

Optional pointer to a callback routine to be invoked when a change occurs in a subdirectory being watched in a directory tree. This lets the file system check whether the watcher has traverse access to that directory. Such a caller-supplied routine is declared as follows:

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
For more information about the <i>TargetContext</i> parameter, see the <i>TargetContext</i> parameter of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfullreportchange">FsRtlNotifyFullReportChange</a>. <i>TraverseCallback</i> is ignored if <i>NotifyIrp</i> is <b>NULL</b>.


### -param SubjectContext [in, optional]

Pointer to a context structure to be passed to <i>TraverseCallback</i>. <b>FsRtlNotifyFilterChangeDirectory</b> releases the context and frees the structure after using it. Ignored if <i>NotifyIrp</i> is <b>NULL</b>. If a <i>TraverseCallback</i> routine is supplied, <i>SubjectContext</i> is passed as the <i>SubjectContext</i> parameter to that routine.


### -param FilterCallback [in, optional]

Optional pointer to a callback routine to be invoked when a change occurs to the directory. If this callback routine returns <b>TRUE</b>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfilterreportchange">FsRtlNotifyFilterReportChange</a> completes the pending IRP_MN_NOTIFY_CHANGE_DIRECTORY requests in the notify list; otherwise, it does not. Such a caller-supplied routine is declared as follows: 

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

## -remarks



<b>FsRtlNotifyFilterChangeDirectory</b> is called by a file system that has received an IRP with major function code <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-directory-control">IRP_MJ_DIRECTORY_CONTROL</a>, minor function code IRP_MN_NOTIFY_CHANGE_DIRECTORY. 

The file system calls <b>FsRtlNotifyFilterChangeDirectory</b> to create a notify structure to hold the IRP and add the notify structure to the notify list for the current volume. 

If <i>NotifyIrp</i> is <b>NULL</b>, <b>FsRtlNotifyFilterChangeDirectory</b> checks whether the notify list already contains any pending IRPs whose file objects match the given <i>FsContext</i> value and, if so, completes the IRPs with STATUS_DELETE_PENDING. 

If <i>NotifyIrp</i> is not <b>NULL</b>, <b>FsRtlNotifyFilterChangeDirectory</b> does the following:

<ul>
<li>
Checks whether the IRP's file object has undergone cleanup. If so, <b>FsRtlNotifyFilterChangeDirectory</b> completes the IRP with status STATUS_NOTIFY_CLEANUP and does not add it to the notify list. 

</li>
<li>
If the IRP's file object has not undergone cleanup, <b>FsRtlNotifyFilterChangeDirectory</b> checks whether the notify list already contains a notify structure for the given <i>FsContext</i> value. If such a notify structure is found, and there are pending changes to report, <b>FsRtlNotifyFilterChangeDirectory</b> completes <i>NotifyIrp</i>. If a notify structure is found, but there are no pending changes to report, <b>FsRtlNotifyFilterChangeDirectory</b> marks the IRP pointed to by <i>NotifyIrp</i>  as pending and inserts it into the list of notify IRPs in the notify structure. If no such notify structure is found, <b>FsRtlNotifyFilterChangeDirectory</b> marks the IRP pointed to by <i>NotifyIrp</i>  as pending, creates a notify structure, and inserts it into the notify list. 

</li>
</ul>
When a change occurs to the directory, the file system calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfilterreportchange">FsRtlNotifyFilterReportChange</a> to complete the pending IRP_MN_NOTIFY_CHANGE_DIRECTORY requests in the notify list. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfilterreportchange">FsRtlNotifyFilterReportChange</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfullchangedirectory">FsRtlNotifyFullChangeDirectory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfullreportchange">FsRtlNotifyFullReportChange</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-directory-control">IRP_MJ_DIRECTORY_CONTROL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">SECURITY_SUBJECT_CONTEXT</a>
 

 

