---
UID: NF:fltkernel.FltNotifyFilterChangeDirectory
title: FltNotifyFilterChangeDirectory function
author: windows-driver-content
description: The FltNotifyFilterChangeDirectory routine creates a notify structure for an IRP_MN_NOTIFY_CHANGE_DIRECTORY operation and adds it to the specified notify list.
old-location: ifsk\fltnotifyfilterchangedirectory.htm
old-project: ifsk
ms.assetid: bbeabd33-951e-4fd5-9845-cabed5f95fcd
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltApiRef_e_to_o_855490c1-8b4e-4973-9a96-808b50c20740.xml, ifsk.fltnotifyfilterchangedirectory, fltkernel/FltNotifyFilterChangeDirectory, FltNotifyFilterChangeDirectory routine [Installable File System Drivers], FltNotifyFilterChangeDirectory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltNotifyFilterChangeDirectory
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltNotifyFilterChangeDirectory function


## -description


The <b>FltNotifyFilterChangeDirectory</b> routine creates a notify structure for an IRP_MN_NOTIFY_CHANGE_DIRECTORY operation and adds it to the specified notify list.


## -syntax


````
VOID FltNotifyFilterChangeDirectory(
  _Inout_  PNOTIFY_SYNC               NotifySync,
  _Inout_  PLIST_ENTRY                NotifyList,
  _In_     PVOID                      FsContext,
  _In_     PSTRING                    FullDirectoryName,
  _In_     BOOLEAN                    WatchTree,
  _In_     BOOLEAN                    IgnoreBuffer,
  _In_     ULONG                      CompletionFilter,
  _In_     PFLT_CALLBACK_DATA         NotifyCallbackData,
  _In_opt_ PCHECK_FOR_TRAVERSE_ACCESS TraverseCallback,
  _In_opt_ PSECURITY_SUBJECT_CONTEXT  SubjectContext,
  _In_opt_ PFILTER_REPORT_CHANGE      FilterCallback
);
````


## -parameters




#### - NotifySync [in, out]

Pointer to an opaque synchronization object for the change directory notify list that the <i>NotifyList</i> parameter points to. 


#### - NotifyList [in, out]

Pointer to the head of the change directory notify list for the current volume. Each element in the list is an opaque notify structure. 


#### - FsContext [in]

Pointer to a unique value assigned by the caller to identify the notify structure to be created. If a callback routine is supplied in the <i>TraverseCallback</i> parameter, <i>FsContext</i> is passed as the <i>NotifyContext</i> parameter to that routine. 


#### - FullDirectoryName [in]

Pointer to an ANSI or Unicode string that contains the full name for the directory associated with this notify structure. 


#### - WatchTree [in]

Set to <b>TRUE</b> if all subdirectories of the directory that is specified by the <i>FullDirectoryName</i> parameter should also be watched. Set to <b>FALSE</b> if only the directory itself is to be watched. 


#### - IgnoreBuffer [in]

Set to <b>TRUE</b> to ignore any user buffers and force the directory to be reenumerated. This action speeds the operation. 


#### - CompletionFilter [in]

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


#### - NotifyCallbackData [in]

Pointer to the callback data structure for the operation to be added to the notify list. This parameter is required and cannot be <b>NULL</b>. 


#### - TraverseCallback [in, optional]

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
</table></span></div>For more information about the <i>TargetContext</i> parameter, see the <i>TargetContext</i> parameter of the <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfullreportchange~r8.md">FsRtlNotifyFullReportChange</a> routine. 


#### - SubjectContext [in, optional]

Pointer to a context structure to be passed to <i>TraverseCallback</i>. <b>FltNotifyFilterChangeDirectory</b> releases the context and frees the structure after using it. If a <i>TraverseCallback</i> routine is supplied, <i>SubjectContext</i> is passed as the <i>SubjectContext</i> parameter to that routine.


#### - FilterCallback [in, optional]

Optional pointer to a callback routine to be invoked when a change occurs to the directory. If this callback routine returns <b>TRUE</b>, <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfilterreportchange~r9.md">FsRtlNotifyFilterReportChange</a> completes the pending IRP_MN_NOTIFY_CHANGE_DIRECTORY operations in the notify list; otherwise, it does not. Such a caller-supplied routine is declared as follows: 
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


A minifilter driver can call <b>FltNotifyFilterChangeDirectory</b> from the preoperation callback routine (<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>) that it registered to process notify change directory operations. These operations have a major function code of <a href="https://msdn.microsoft.com/library/windows/hardware/ff548658">IRP_MJ_DIRECTORY_CONTROL</a> and a minor function code of  IRP_MN_NOTIFY_CHANGE_DIRECTORY. 

The minifilter driver calls <b>FltNotifyFilterChangeDirectory</b> to create a notify structure to hold the callback data structure for the operation and add the notify structure to the notify list for the current volume. 

<b>FltNotifyFilterChangeDirectory</b> does the following:
<ul>
<li>
Checks whether the operation's file object has been cleaned up. If so, <b>FltNotifyFilterChangeDirectory</b> completes the operation with status STATUS_NOTIFY_CLEANUP and does not add it to the notify list. 

</li>
<li>
If the operation's file object has not been cleaned up, <b>FltNotifyFilterChangeDirectory</b> checks whether the notify list already contains a notify structure for the given <i>FsContext</i> value. If such a notify structure is found, and there are pending changes to report, <b>FltNotifyFilterChangeDirectory</b> completes the callback data structure pointed to by the <i>NotifyCallbackData</i> parameter. If a notify structure is found, but there are no pending changes to report, <b>FltNotifyFilterChangeDirectory</b> adds the operation to the notify structure. If no such notify structure is found, <b>FltNotifyFilterChangeDirectory</b> creates a notify structure for the operation and inserts it into the list. 

</li>
</ul>When a change occurs to the directory, the file system calls <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfilterreportchange~r9.md">FsRtlNotifyFilterReportChange</a> to complete the pending IRP_MN_NOTIFY_CHANGE_DIRECTORY operations in the notify list. 



## -see-also

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfilterreportchange~r9.md">FsRtlNotifyFilterReportChange</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548658">IRP_MJ_DIRECTORY_CONTROL</a>

<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltNotifyFilterChangeDirectory routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

