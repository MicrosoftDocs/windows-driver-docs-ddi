---
UID: NF:rxprocs.FsRtlNotifyFullChangeDirectory
title: FsRtlNotifyFullChangeDirectory macro (rxprocs.h)
description: The FsRtlNotifyFullChangeDirectory routine creates a notify structure for a notification request and adds it to the specified notify list.
old-location: ifsk\fsrtlnotifyfullchangedirectory.htm
tech.root: ifsk
ms.assetid: 42e5340e-0be4-49d1-a219-88b7425a41ef
ms.date: 04/16/2018
keywords: ["FsRtlNotifyFullChangeDirectory macro"]
ms.keywords: FsRtlNotifyFullChangeDirectory, FsRtlNotifyFullChangeDirectory routine [Installable File System Drivers], fsrtlref_551aff27-746f-49a4-b427-fa273249c36e.xml, ifsk.fsrtlnotifyfullchangedirectory, rxprocs/FsRtlNotifyFullChangeDirectory
req.header: rxprocs.h
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
f1_keywords:
 - FsRtlNotifyFullChangeDirectory
 - rxprocs/FsRtlNotifyFullChangeDirectory
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlNotifyFullChangeDirectory
---

# FsRtlNotifyFullChangeDirectory macro


## -description

The <b>FsRtlNotifyFullChangeDirectory</b> routine creates a notify structure for a notification request and adds it to the specified notify list.

## -parameters

### -param A1

<p>A pointer to an opaque synchronization object for the notify list for the current volume.</p>

### -param A2

<p>A pointer to the head of a notify list. Each element in the list is an opaque notify structure.</p>

### -param A3

<p>A pointer to a unique value assigned by the file system to identify the notify structure to be created as belonging to a particular file object. If a <i>TraverseCallback</i> routine is supplied, <i>FsContext</i> is passed as the <i>NotifyContext</i> parameter to that routine.</p>

### -param A4

<p>A pointer to an ANSI or Unicode string that contains the full name for the directory associated with this notify structure. Ignored if <i>NotifyIrp</i> is <b>NULL</b>.</p>

### -param A5

<p>Set to <b>TRUE</b> if all subdirectories of this directory should also be watched. Set to <b>FALSE</b> if only the directory itself is to be watched. Ignored if <i>NotifyIrp</i> is <b>NULL</b>.</p>

### -param A6

<p>Set to <b>TRUE</b> to ignore any user buffers and force the directory to be reenumerated. This action speeds the operation. Ignored if <i>NotifyIrp</i> is <b>NULL</b>.</p>

### -param A7

<p>Bitmask of flags that specify the types of changes to files or subdirectories that should cause the queue of pending notify IRPs to be completed. The possible flag values are described following.</p>
  <table>
    <tr>
      <th>Flag</th>
      <th>Meaning</th>
    </tr>
    <tr>
      <td>
        <p>FILE_NOTIFY_CHANGE_FILE_NAME</p>
      </td>
      <td>
        <p>A file has been added, deleted, or renamed in this directory.</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FILE_NOTIFY_CHANGE_DIR_NAME</p>
      </td>
      <td>
        <p>A subdirectory has been created, removed, or renamed.</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FILE_NOTIFY_CHANGE_NAME</p>
      </td>
      <td>
        <p>This directory's name has changed.</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FILE_NOTIFY_CHANGE_ATTRIBUTES</p>
      </td>
      <td>
        <p>The value of an attribute of this file, such as last access time, has changed.</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FILE_NOTIFY_CHANGE_SIZE</p>
      </td>
      <td>
        <p>This file's size has changed.</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FILE_NOTIFY_CHANGE_LAST_WRITE</p>
      </td>
      <td>
        <p>This file's last modification time has changed.</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FILE_NOTIFY_CHANGE_LAST_ACCESS</p>
      </td>
      <td>
        <p>This file's last access time has changed.</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FILE_NOTIFY_CHANGE_CREATION</p>
      </td>
      <td>
        <p>This file's creation time has changed.</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FILE_NOTIFY_CHANGE_EA</p>
      </td>
      <td>
        <p>This file's extended attributes have been modified.</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FILE_NOTIFY_CHANGE_SECURITY</p>
      </td>
      <td>
        <p>This file's security information has changed.</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FILE_NOTIFY_CHANGE_STREAM_NAME</p>
      </td>
      <td>
        <p>A file stream has been added, deleted, or renamed in this directory.</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FILE_NOTIFY_CHANGE_STREAM_SIZE</p>
      </td>
      <td>
        <p>This file stream's size has changed.</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FILE_NOTIFY_CHANGE_STREAM_WRITE</p>
      </td>
      <td>
        <p>This file stream's data has changed.</p>
      </td>
    </tr>
  </table>
  <p> </p>
  <p>
    <i>CompletionFilter</i> is ignored if <i>NotifyIrp</i> is <b>NULL</b>.</p>

### -param A8

<p>A pointer to the IRP to complete on notify change. If <i>NotifyIrp</i> is <b>NULL</b>, this means that the file stream represented by this file object is being deleted.</p>

### -param A9

<p>Optional pointer to a callback routine to be invoked when a change occurs in a subdirectory being watched in a directory tree. This lets the file system check whether the watcher has traverse access to that directory. Such a caller-supplied routine is declared as follows:</p>
  <div class="code">
    <span codelanguage="">
      <table>
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
      </table>
    </span>
  </div>
  <p>For more information about the <i>TargetContext</i> parameter, see the <i>TargetContext</i> parameter of <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfullreportchange"><b>FsRtlNotifyFullReportChange</b></a>. <i>TraverseCallback</i> is ignored if <i>NotifyIrp</i> is <b>NULL</b>.</p>

### -param A10

<p>A pointer to a context structure to be passed to <i>TraverseCallback</i>. <b>FsRtlNotifyFullChangeDirectory</b> releases the context and frees the structure after using it. Ignored if <i>NotifyIrp</i> is <b>NULL</b>. If a <i>TraverseCallback</i> routine is supplied, <i>SubjectContext</i> is passed as the <i>SubjectContext</i> parameter to that routine.</p>

## -remarks

<b>FsRtlNotifyFullChangeDirectory</b> is called by a file system that has received a notify change request. This request is received as an IRP with major function code IRP_MJ_DIRECTORY_CONTROL, minor function code IRP_MN_NOTIFY_CHANGE_DIRECTORY. 

If <i>NotifyIrp</i> is <b>NULL</b>, <b>FsRtlNotifyFullChangeDirectory</b> checks whether the notify list contains a pending IRP that refers to this file object and, if so, completes it with STATUS_DELETE_PENDING.

If <i>NotifyIrp</i> is not <b>NULL</b>, <b>FsRtlNotifyFullChangeDirectory</b> does the following:

<ul>
<li>
Checks whether the file object has undergone cleanup. If so, <b>FsRtlNotifyFullChangeDirectory</b> completes the notify IRP with status STATUS_NOTIFY_CLEANUP.

</li>
<li>
If the file object has not undergone cleanup, <b>FsRtlNotifyFullChangeDirectory</b> checks whether the notify list for this volume already contains a notify structure for this change. If so, <b>FsRtlNotifyFullChangeDirectory</b> completes any pending IRPs. If not, <b>FsRtlNotifyFullChangeDirectory</b> marks the notify IRP as pending, creates a notify structure, and inserts it into the list. 

</li>
</ul>

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfullreportchange">FsRtlNotifyFullReportChange</a>



<a href="/windows-hardware/drivers/ifs/irp-mj-directory-control">IRP_MJ_DIRECTORY_CONTROL</a>



<a href="/windows-hardware/drivers/kernel/eprocess">SECURITY_SUBJECT_CONTEXT</a>