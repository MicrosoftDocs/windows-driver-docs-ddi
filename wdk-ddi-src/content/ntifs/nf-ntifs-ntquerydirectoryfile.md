---
UID: NF:ntifs.NtQueryDirectoryFile
title: NtQueryDirectoryFile function
author: windows-driver-content
description: The ZwQueryDirectoryFile routine returns various kinds of information about files in the directory specified by a given file handle.
old-location: kernel\zwquerydirectoryfile.htm
old-project: kernel
ms.assetid: 47e88095-fab3-4fa2-814e-db04ce864e7e
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: NtQueryDirectoryFile, ZwQueryDirectoryFile, ZwQueryDirectoryFile routine [Kernel-Mode Driver Architecture], k111_ffed894d-20dc-416e-8759-073a0cee3229.xml, kernel.zwquerydirectoryfile, ntifs/NtQueryDirectoryFile, ntifs/ZwQueryDirectoryFile
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ZwQueryDirectoryFile
-	NtQueryDirectoryFile
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# NtQueryDirectoryFile function


## -description


The <b>ZwQueryDirectoryFile</b> routine returns various kinds of information about files in the directory specified by a given file handle.


## -syntax


````
NTSTATUS ZwQueryDirectoryFile(
  _In_     HANDLE                 FileHandle,
  _In_opt_ HANDLE                 Event,
  _In_opt_ PIO_APC_ROUTINE        ApcRoutine,
  _In_opt_ PVOID                  ApcContext,
  _Out_    PIO_STATUS_BLOCK       IoStatusBlock,
  _Out_    PVOID                  FileInformation,
  _In_     ULONG                  Length,
  _In_     FILE_INFORMATION_CLASS FileInformationClass,
  _In_     BOOLEAN                ReturnSingleEntry,
  _In_opt_ PUNICODE_STRING        FileName,
  _In_     BOOLEAN                RestartScan
);
````


## -parameters




### -param FileHandle [in]

A handle returned by <a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a> or <a href="..\wdm\nf-wdm-zwopenfile.md">ZwOpenFile</a> for the file object that represents the directory for which information is being requested. The file object must have been opened for asynchronous I/O if the caller specifies a non-<b>NULL</b> value for <i>Event</i> or <i>ApcRoutine</i>.


### -param Event [in, optional]

An optional handle for a caller-created event. If this parameter is supplied, the caller will be put into a wait state until the requested operation is completed and the given event is set to the Signaled state. This parameter is optional and can be <b>NULL</b>. It must be <b>NULL</b> if the caller will wait for the <i>FileHandle</i> to be set to the Signaled state.


### -param ApcRoutine [in, optional]

An address of an optional, caller-supplied APC routine to be called when the requested operation completes. This parameter is optional and can be <b>NULL</b>. If there is an I/O completion object associated with the file object, this parameter must be <b>NULL</b>.


### -param ApcContext [in, optional]

An optional pointer to a caller-determined context area if the caller supplies an APC or if an I/O completion object is associated with the file object. When the operation completes, this context is passed to the APC, if one was specified, or is included as part of the completion message that the I/O Manager posts to the associated I/O completion object. 

This parameter is optional and can be <b>NULL</b>. It must be <b>NULL</b> if <i>ApcRoutine</i> is <b>NULL</b> and there is no I/O completion object associated with the file object.


### -param IoStatusBlock [out]

A pointer to an <a href="..\wdm\ns-wdm-_io_status_block.md">IO_STATUS_BLOCK</a> structure that receives the final completion status and information about the operation. For successful calls that return data, the number of bytes written to the <i>FileInformation</i> buffer is returned in the structure's <b>Information</b> member.


### -param FileInformation [out]

A pointer to a buffer that receives the desired information about the file. The structure of the information returned in the buffer is defined by the <i>FileInformationClass</i> parameter.


### -param Length [in]

The size, in bytes, of the buffer pointed to by <i>FileInformation</i>. The caller should set this parameter according to the given <i>FileInformationClass</i>.


### -param FileInformationClass [in]

The type of information to be returned about files in the directory. One of the following. 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>FileBothDirectoryInformation</b>

</td>
<td>
Return a <a href="..\ntifs\ns-ntifs-_file_both_dir_information.md">FILE_BOTH_DIR_INFORMATION</a> structure for each file.

</td>
</tr>
<tr>
<td>
<b>FileDirectoryInformation</b>

</td>
<td>
Return a <a href="..\ntifs\ns-ntifs-_file_directory_information.md">FILE_DIRECTORY_INFORMATION</a> structure for each file.

</td>
</tr>
<tr>
<td>
<b>FileFullDirectoryInformation</b>

</td>
<td>
Return a <a href="..\ntifs\ns-ntifs-_file_full_dir_information.md">FILE_FULL_DIR_INFORMATION</a> structure for each file.

</td>
</tr>
<tr>
<td>
<b>FileIdBothDirectoryInformation</b>

</td>
<td>
Return a <a href="..\ntifs\ns-ntifs-_file_id_both_dir_information.md">FILE_ID_BOTH_DIR_INFORMATION</a> structure for each file.

</td>
</tr>
<tr>
<td>
<b>FileIdFullDirectoryInformation</b>

</td>
<td>
Return a <a href="..\ntifs\ns-ntifs-_file_id_full_dir_information.md">FILE_ID_FULL_DIR_INFORMATION</a> structure for each file.

</td>
</tr>
<tr>
<td>
<b>FileNamesInformation</b>

</td>
<td>
Return a <a href="..\ntifs\ns-ntifs-_file_names_information.md">FILE_NAMES_INFORMATION</a> structure for each file.

</td>
</tr>
<tr>
<td>
<b>FileObjectIdInformation</b>

</td>
<td>
Return a <a href="..\ntifs\ns-ntifs-_file_objectid_information.md">FILE_OBJECTID_INFORMATION</a> structure for each file. This information class is valid only for NTFS volumes on Windows 2000 and later versions of Windows.

</td>
</tr>
<tr>
<td>
<b>FileReparsePointInformation</b>

</td>
<td>
Return a single <a href="..\ntifs\ns-ntifs-_file_reparse_point_information.md">FILE_REPARSE_POINT_INFORMATION</a> structure for the directory.

</td>
</tr>
</table>
 


### -param ReturnSingleEntry [in]

Set to <b>TRUE</b> if only a single entry should be returned, <b>FALSE</b> otherwise. If this parameter is <b>TRUE</b>, <b>ZwQueryDirectoryFile</b> returns only the first entry that is found.


### -param FileName [in, optional]

An optional pointer to a caller-allocated Unicode string containing the name of a file (or multiple files, if wildcards are used) within the directory specified by <i>FileHandle</i>. This parameter is optional and can be <b>NULL</b>. 

If <i>FileName</i> is not <b>NULL</b>, only files whose names match the <i>FileName</i> string are included in the directory scan. If <i>FileName</i> is <b>NULL</b>, all files are included. 

The <i>FileName</i> is used as a search expression and is captured on the very first call to <b>ZwQueryDirectoryFile</b> for a given handle. Subsequent calls to <b>ZwQueryDirectoryFile</b> will use the search expression set in the first call. The <i>FileName</i> parameter passed to subsequent calls will be ignored. 


### -param RestartScan [in]

Set to <b>TRUE</b> if the scan is to start at the first entry in the directory. Set to <b>FALSE</b> if resuming the scan from a previous call.

When the <b>ZwQueryDirectoryFile</b> routine is called for a particular handle, the <i>RestartScan</i> parameter is treated as if it were set to <b>TRUE</b>, regardless of its value. On subsequent <b>ZwQueryDirectoryFile</b> calls, the value of the <i>RestartScan</i> parameter is honored.


## -returns



The <b>ZwQueryDirectoryFile</b>routine returns STATUS_SUCCESS or an appropriate error status. Note that the set of error status values that can be returned is file-system-specific. <b>ZwQueryDirectoryFile</b>also returns the number of bytes actually written to the given <i>FileInformation</i> buffer in the <b>Information</b> member of <i>IoStatusBlock</i>.




## -remarks



The <b>ZwQueryDirectoryFile</b> routine returns information about files that are contained in the directory represented by <i>FileHandle</i>.

If provided, the value of the <i>FileName</i> parameter determines the entries that are included in the directory scan for all subsequent calls to <b>ZwQueryDirectoryFile</b> for a given <i>FileHandle</i>.

If there is at least one matching entry, <b>ZwQueryDirectoryFile</b> creates a <b>FILE_<i>XXX</i>_INFORMATION</b> structure for each entry and stores them in the buffer.

Assuming that at least one matching directory entry is found, the number of entries for which information is returned is the <i>smallest</i> of the following:

<ul>
<li>
One entry, if <i>ReturnSingleEntry</i> is <b>TRUE</b> and <i>FileName</i> is <b>NULL</b>.

</li>
<li>
The number of entries that match the <i>FileName</i> string, if <i>FileName</i> is not <b>NULL</b>. (Note that if the string contains no wildcards, there can be at most one matching entry.)

</li>
<li>
The number of entries whose information fits into the specified buffer.

</li>
<li>
The number of entries contained in the directory.

</li>
</ul>
On the first call to <b>ZwQueryDirectoryFile</b>, if the structure created for the first entry found is too large to fit into the output buffer, the routine writes the fixed portion of the structure to the output buffer. The routine then writes to the output buffer as much of the <i>FileName</i> string as will fit. (The fixed portion of the structure consists of all fields except the final <i>FileName</i> string. On the first call, but not on subsequent calls, the I/O system ensures that the buffer is large enough to hold the fixed portion of the appropriate <b>FILE_<i>XXX</i>_INFORMATION</b> structure.) When this happens, <b>ZwQueryDirectoryFile</b> returns an appropriate status value such as STATUS_BUFFER_OVERFLOW.

On each call, <b>ZwQueryDirectoryFile</b> returns as many <b>FILE_<i>XXX</i>_INFORMATION</b> structures (one per directory entry) as can be contained entirely in the buffer pointed to by <i>FileInformation</i>. On the first call, <b>ZwQueryDirectoryFile</b> returns STATUS_SUCCESS only if the output buffer contains at least one complete structure. On subsequent calls, if the output buffer contains no structures, <b>ZwQueryDirectoryFile</b> returns STATUS_SUCCESS but sets <i>IoStatusBlock</i>-&gt;<b>Information</b> = 0 to notify the caller of this condition. In this case, the caller should allocate a larger buffer and call <b>ZwQueryDirectoryFile</b> again. No information about any remaining entries is reported. Thus, except in the cases listed above where only one entry is returned, <b>ZwQueryDirectoryFile</b> must be called at least twice to enumerate the contents of an entire directory.

When calling <b>ZwQueryDirectoryFile</b>, you may see changes made to the directory that occur in parallel with <b>ZwQueryDirectoryFile</b> calls.  This behavior is dependent on the implementation of the underlying file system.

The final call to <b>ZwQueryDirectoryFile</b> returns an empty output buffer and reports an appropriate status value such as STATUS_NO_MORE_FILES.

If <b>ZwQueryDirectoryFile</b> is called multiple times on the same directory and some other operation changes the contents of that directory, any changes may or may not be seen, depending on the timing of the operations.

<b>ZwQueryDirectoryFile</b>returns zero in any member of a <b>FILE_<i>XXX</i>_INFORMATION</b> structure that is not supported by the file system.

Callers of <b>ZwQueryDirectoryFile</b> must be running at IRQL = PASSIVE_LEVEL and <a href="https://msdn.microsoft.com/0578df31-1467-4bad-ba62-081d61278deb">with special kernel APCs enabled</a>.

For information about other file information query routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545843">File Objects</a>.

<div class="alert"><b>Note</b>  If the call to the <b>ZwQueryDirectoryFile</b> function occurs in user mode, you should use the name "<b>NtQueryDirectoryFile</b>" instead of "<b>ZwQueryDirectoryFile</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also

<a href="..\wdm\nf-wdm-zwopenfile.md">ZwOpenFile</a>



<a href="..\ntifs\ns-ntifs-_file_both_dir_information.md">FILE_BOTH_DIR_INFORMATION</a>



<a href="..\ntifs\ns-ntifs-_file_id_both_dir_information.md">FILE_ID_BOTH_DIR_INFORMATION</a>



<a href="..\ntifs\ns-ntifs-_file_objectid_information.md">FILE_OBJECTID_INFORMATION</a>



<a href="..\ntifs\ns-ntifs-_file_full_dir_information.md">FILE_FULL_DIR_INFORMATION</a>



<a href="..\ntifs\ns-ntifs-_file_names_information.md">FILE_NAMES_INFORMATION</a>



<a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a>



<a href="..\ntifs\ns-ntifs-_file_directory_information.md">FILE_DIRECTORY_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\ntifs\ns-ntifs-_file_reparse_point_information.md">FILE_REPARSE_POINT_INFORMATION</a>



<a href="..\ntifs\ns-ntifs-_file_id_full_dir_information.md">FILE_ID_FULL_DIR_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwQueryDirectoryFile routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

