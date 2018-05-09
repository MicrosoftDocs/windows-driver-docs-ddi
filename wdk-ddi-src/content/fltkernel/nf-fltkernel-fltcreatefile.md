---
UID: NF:fltkernel.FltCreateFile
title: FltCreateFile function
author: windows-driver-content
description: Minifilter drivers call FltCreateFile to create a new file or open an existing file.
old-location: ifsk\fltcreatefile.htm
old-project: ifsk
ms.assetid: fd7e1f27-e492-4402-ae9e-4ce52c3420d0
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FltApiRef_a_to_d_2059a625-6d9e-4083-9c2e-d92e76c7539a.xml, FltCreateFile, FltCreateFile function [Installable File System Drivers], fltkernel/FltCreateFile, ifsk.fltcreatefile
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows 2000 Update Rollup 1 for SP4, Windows XP SP2, Windows Server 2003 SP1, and later operating systems. Not available in Windows 2000 SP4 and earlier operating systems.
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
req.lib: Fltmgr.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Fltmgr.lib
-	Fltmgr.dll
api_name:
-	FltCreateFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltCreateFile function


## -description


Minifilter drivers call <b>FltCreateFile </b>to create a new file or open an existing file.


## -parameters




### -param Filter [in]

An opaque filter pointer for the caller. 


### -param Instance [in, optional]

An opaque instance pointer for the minifilter driver instance that the create request is to be sent to. The instance must be attached to the volume where the file or directory resides. This parameter is optional and can be <b>NULL</b>. If this parameter is <b>NULL</b>, the request is sent to the device object at the top of the file system driver stack for the volume. If it is non-<b>NULL</b>, the request is sent only to minifilter driver instances that are attached below the specified instance. 


### -param FileHandle [out]

A pointer to a caller-allocated variable that receives the file handle if the call to <b>FltCreateFile</b> is successful. 


### -param DesiredAccess [in]

A bitmask of flags specifying the type of access that the caller requires to the file or directory. The set of system-defined <i>DesiredAccess</i> flags determines the following specific access rights for file objects. 

Do not specify FILE_READ_DATA, FILE_WRITE_DATA, FILE_EXECUTE, or FILE_APPEND_DATA when creating or opening a directory.

<table>
<tr>
<th>DesiredAccess Flags</th>
<th>Meaning</th>
</tr>
<tr>
<td>
DELETE

</td>
<td>
The file can be deleted.

</td>
</tr>
<tr>
<td>
FILE_READ_DATA

</td>
<td>
Data can be read from the file.

</td>
</tr>
<tr>
<td>
FILE_READ_ATTRIBUTES

</td>
<td>
<i>FileAttributes</i> flags, described later, can be read.

</td>
</tr>
<tr>
<td>
FILE_READ_EA

</td>
<td>
Extended attributes associated with the file can be read. 

</td>
</tr>
<tr>
<td>
READ_CONTROL

</td>
<td>
The access control list (<a href="https://msdn.microsoft.com/library/windows/hardware/ff538866">ACL</a>) and ownership information associated with the file can be read.

</td>
</tr>
<tr>
<td>
FILE_WRITE_DATA

</td>
<td>
Data can be written to the file.

</td>
</tr>
<tr>
<td>
FILE_WRITE_ATTRIBUTES

</td>
<td>
<i>FileAttributes</i> flags can be written.

</td>
</tr>
<tr>
<td>
FILE_WRITE_EA 

</td>
<td>
Extended attributes associated with the file can be written. 

</td>
</tr>
<tr>
<td>
FILE_APPEND_DATA

</td>
<td>
Data can be appended to the file.

</td>
</tr>
<tr>
<td>
WRITE_DAC 

</td>
<td>
The discretionary access control list (<a href="https://msdn.microsoft.com/dac27df2-fabd-4402-8daf-9317888dd30b">DACL</a>) associated with the file can be written.

</td>
</tr>
<tr>
<td>
WRITE_OWNER 

</td>
<td>
Ownership information associated with the file can be written.

</td>
</tr>
<tr>
<td>
SYNCHRONIZE

</td>
<td>
The caller can synchronize the completion of an I/O operation by waiting for the returned <i>FileHandle</i> to be set to the Signaled state. This flag must be set if the <i>CreateOptions</i> FILE_SYNCHRONOUS_IO_ALERT or FILE_SYNCHRONOUS_IO_NONALERT flag is set. 

</td>
</tr>
<tr>
<td>
FILE_EXECUTE

</td>
<td>
Use system paging I/O to read data from the file into system memory. 

</td>
</tr>
</table>
 

Alternatively, for any file object that does not represent a directory, you can specify one or more of the following generic <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> flags. (The STANDARD_RIGHTS_<i>XXX</i> flags are predefined system values that are used to enforce security on system objects.) You can also combine these generic flags with additional flags from the preceding table. 

<table>
<tr>
<th>DesiredAccess to File Values</th>
<th>Maps to DesiredAccess Flags</th>
</tr>
<tr>
<td>
GENERIC_READ

</td>
<td>
STANDARD_RIGHTS_READ, FILE_READ_DATA, FILE_READ_ATTRIBUTES, FILE_READ_EA, and SYNCHRONIZE. 

</td>
</tr>
<tr>
<td>
GENERIC_WRITE

</td>
<td>
STANDARD_RIGHTS_WRITE, FILE_WRITE_DATA, FILE_WRITE_ATTRIBUTES, FILE_WRITE_EA, FILE_APPEND_DATA, and SYNCHRONIZE. 

</td>
</tr>
<tr>
<td>
GENERIC_EXECUTE

</td>
<td>
STANDARD_RIGHTS_EXECUTE, SYNCHRONIZE, FILE_READ_ATTRIBUTES, and FILE_EXECUTE. 

</td>
</tr>
</table>
 

For directories, you can specify one or more of the following ACCESS_MASK flags, which you can also combine with any compatible flags that were described earlier. 

<table>
<tr>
<th>DesiredAccess to Directory Values</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FILE_LIST_DIRECTORY

</td>
<td>
Files in the directory can be listed.

</td>
</tr>
<tr>
<td>
FILE_TRAVERSE

</td>
<td>
The directory can be traversed: that is, it can be part of the pathname of a file.

</td>
</tr>
</table>
 


### -param ObjectAttributes [in]

A pointer to a structure already initialized with <a href="https://msdn.microsoft.com/library/windows/hardware/ff547804">InitializeObjectAttributes</a>. If the caller is running in the system process context, this parameter can be <b>NULL</b>. Otherwise, the caller must set the OBJ_KERNEL_HANDLE attribute in the call to <b>InitializeObjectAttributes</b>. Members of this structure for a file object include the following. 

<table>
<tr>
<th>Member</th>
<th>Value</th>
</tr>
<tr>
<td>
<b>ULONGLength</b>

</td>
<td>
Specifies the number of bytes of <i>ObjectAttributes</i> data supplied. This value must be at least <b>sizeof(</b>OBJECT_ATTRIBUTES<b>)</b>.

</td>
</tr>
<tr>
<td>
<b>PUNICODE_STRING ObjectName</b>

</td>
<td>
Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure containing the name of the file to be created or opened. This name must be a fully qualified file specification or the name of a device object unless it is the name of a file relative to the directory specified by <b>RootDirectory</b>. For example, \Device\Floppy1\myfile.dat or \??\B:\myfile.dat could be the fully qualified file specification, if the floppy driver and overlying file system are already loaded. (Note: \?? replaces \DosDevices as the name of the Win32 object namespace. \DosDevices still works, but \?? is translated faster by the object manager.)

</td>
</tr>
<tr>
<td>
<b>HANDLERootDirectory</b>

</td>
<td>
Optionally specifies a handle to a directory obtained by a preceding call to <b>FltCreateFile</b>. If this value is <b>NULL</b>, the <b>ObjectName </b>member must be a fully qualified file specification that includes the full path to the target file. If this value is non-<b>NULL</b>, the <b>ObjectName</b> member specifies a file name relative to this directory.

</td>
</tr>
<tr>
<td>
<b>PSECURITY_DESCRIPTOR SecurityDescriptor</b>

</td>
<td>
Optionally specifies a security descriptor (<a href="https://msdn.microsoft.com/library/windows/hardware/ff563689">SECURITY_DESCRIPTOR</a>) to be applied to a file. <a href="https://msdn.microsoft.com/dac27df2-fabd-4402-8daf-9317888dd30b">ACLs</a> specified by such a security descriptor are only applied to the file when it is created. If the value is <b>NULL</b> when a file is created, the ACL placed on the file is file-system-dependent; most file systems propagate some part of such an ACL from the parent directory file combined with the caller's default ACL. 

</td>
</tr>
<tr>
<td>
<b>ULONGAttributes</b>

</td>
<td>
Is a set of flags that controls the file object attributes. If the caller is running in the system process context, this parameter can be zero. Otherwise, the caller must set the OBJ_KERNEL_HANDLE flag. The caller can also optionally set the OBJ_CASE_INSENSITIVE flag, which indicates that name-lookup code should ignore the case of <b>ObjectName</b> rather than performing an exact-match search. 

</td>
</tr>
</table>
 


### -param IoStatusBlock [out]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550671">IO_STATUS_BLOCK</a> structure that receives the final completion status and information about the requested operation. On return from <b>FltCreateFile</b>, the <b>Information</b> member contains one of the following values.

FILE_CREATED

FILE_OPENED

FILE_OVERWRITTEN

FILE_SUPERSEDED

FILE_EXISTS

FILE_DOES_NOT_EXIST


### -param AllocationSize [in, optional]

Optionally specifies the initial allocation size, in bytes, for the file stream. A nonzero value has no effect unless the file is being created, overwritten, or superseded. 


### -param FileAttributes [in]

Specifies one or more of the following FILE_ATTRIBUTE_<i>XXX</i> flags, which represent the file attributes to set if you are creating, superseding, or overwriting a file. Normally, you specify FILE_ATTRIBUTE_NORMAL, which sets the default attributes. 

<table>
<tr>
<th>FileAttributes Flags</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FILE_ATTRIBUTE_NORMAL

</td>
<td>
A file with standard attributes should be created.

</td>
</tr>
<tr>
<td>
FILE_ATTRIBUTE_READONLY

</td>
<td>
A read-only file should be created.

</td>
</tr>
<tr>
<td>
FILE_ATTRIBUTE_HIDDEN

</td>
<td>
A hidden file should be created.

</td>
</tr>
<tr>
<td>
FILE_ATTRIBUTE_SYSTEM

</td>
<td>
A system file should be created.

</td>
</tr>
<tr>
<td>
FILE_ATTRIBUTE_ARCHIVE

</td>
<td>
An archive file should be created. This attribute is used to mark files for backup or removal.

</td>
</tr>
<tr>
<td>
FILE_ATTRIBUTE_TEMPORARY

</td>
<td>
A temporary file should be created.

</td>
</tr>
</table>
 


### -param ShareAccess [in]

Specifies the type of share access to the file that the caller requires, as zero or one, or a combination of the following flags. To request exclusive access, set this parameter to zero. If the IO_IGNORE_SHARE_ACCESS_CHECK flag is specified in the <i>Flags</i> parameter, the I/O manager ignores this parameter. However, the file system might still perform access checks. Thus, it is important to specify the sharing mode you would like for this parameter, even when using the IO_IGNORE_SHARE_ACCESS_CHECK flag. For the greatest chance of avoiding sharing violation errors, specify all of the following share access flags. 

<table>
<tr>
<th>ShareAccess Flags</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FILE_SHARE_READ

</td>
<td>
The file can be opened for read access by other threads.

</td>
</tr>
<tr>
<td>
FILE_SHARE_WRITE

</td>
<td>
The file can be opened for write access by other threads.

</td>
</tr>
<tr>
<td>
FILE_SHARE_DELETE

</td>
<td>
The file can be opened for delete access by other threads.

</td>
</tr>
</table>
 


### -param CreateDisposition [in]

Specifies a value that determines the action to be taken, depending on whether the file already exists. The value can be any of those described following. 

<table>
<tr>
<th>CreateDisposition Values</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FILE_SUPERSEDE

</td>
<td>
If the file already exists, replace it with the given file. If it does not, create the given file. 

</td>
</tr>
<tr>
<td>
FILE_CREATE 

</td>
<td>
If the file already exists, fail the request and do not create or open the given file. If it does not, create the given file.

</td>
</tr>
<tr>
<td>
FILE_OPEN 

</td>
<td>
If the file already exists, open it instead of creating a new file. If it does not, fail the request and do not create a new file.

</td>
</tr>
<tr>
<td>
FILE_OPEN_IF

</td>
<td>
If the file already exists, open it. If it does not, create the given file.

</td>
</tr>
<tr>
<td>
FILE_OVERWRITE

</td>
<td>
If the file already exists, open it and overwrite it. If it does not, fail the request.

</td>
</tr>
<tr>
<td>
FILE_OVERWRITE_IF

</td>
<td>
If the file already exists, open it and overwrite it. If it does not, create the given file.

</td>
</tr>
</table>
 


### -param CreateOptions [in]

Specifies the options to be applied when creating or opening the file, as a compatible combination of the following flags. 

<table>
<tr>
<th>CreateOptions Flags</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FILE_DIRECTORY_FILE

</td>
<td>
The file being created or opened is a directory file. With this flag, the <i>CreateDisposition </i>parameter must be set to one of FILE_CREATE, FILE_OPEN, or FILE_OPEN_IF. With this flag, other compatible <i>CreateOptions</i> flags include only the following: FILE_SYNCHRONOUS_IO_ALERT, FILE_SYNCHRONOUS_IO_NONALERT, FILE_WRITE_THROUGH, FILE_OPEN_FOR_BACKUP_INTENT, and FILE_OPEN_BY_FILE_ID. 

</td>
</tr>
<tr>
<td>
FILE_NON_DIRECTORY_FILE

</td>
<td>
The file being opened must not be a directory file or this call fails. The file object being opened can represent a data file; a logical, virtual, or physical device; or a volume. 

</td>
</tr>
<tr>
<td>
FILE_WRITE_THROUGH

</td>
<td>
System services, file systems, and drivers that write data to the file must actually transfer the data into the file before any requested write operation is considered complete.

</td>
</tr>
<tr>
<td>
FILE_SEQUENTIAL_ONLY

</td>
<td>
All accesses to the file will be sequential.

</td>
</tr>
<tr>
<td>
FILE_RANDOM_ACCESS

</td>
<td>
Accesses to the file can be random, so no sequential read-ahead operations should be performed on the file by file systems or the operating system.

</td>
</tr>
<tr>
<td>
FILE_NO_INTERMEDIATE_BUFFERING

</td>
<td>
The file cannot be cached or buffered in a driver's internal buffers. This flag is incompatible with the <i>DesiredAccess </i>FILE_APPEND_DATA flag. 

</td>
</tr>
<tr>
<td>
FILE_SYNCHRONOUS_IO_ALERT

</td>
<td>
All operations on the file are performed synchronously. Any wait on behalf of the caller is subject to premature termination from alerts. This flag also causes the I/O system to maintain the file position context. If this flag is set, the <i>DesiredAccess</i> SYNCHRONIZE flag also must be set so that the I/O Manager uses the file object as a synchronization object. 

</td>
</tr>
<tr>
<td>
FILE_SYNCHRONOUS_IO_NONALERT

</td>
<td>
All operations on the file are performed synchronously. Waits in the system to synchronize I/O queuing and completion are not subject to alerts. This flag also causes the I/O system to maintain the file position context. If this flag is set, the <i>DesiredAccess</i> SYNCHRONIZE flag also must be set so that the I/O Manager uses the file object as a synchronization object.

</td>
</tr>
<tr>
<td>
FILE_CREATE_TREE_CONNECTION

</td>
<td>
Create a tree connection for this file in order to open it over the network. 

</td>
</tr>
<tr>
<td>
FILE_COMPLETE_IF_OPLOCKED

</td>
<td>
Complete this operation immediately with an alternate success code if the target file is oplocked, rather than blocking the caller's thread. If the file is oplocked, another caller already has access to the file over the network. 

</td>
</tr>
<tr>
<td>
FILE_NO_EA_KNOWLEDGE

</td>
<td>
If the extended attributes on an existing file being opened indicate that the caller must understand extended attributes to properly interpret the file, fail this request because the caller does not understand how to deal with extended attributes. 

</td>
</tr>
<tr>
<td>
FILE_OPEN_REPARSE_POINT

</td>
<td>
Open a file with a reparse point and bypass normal reparse point processing for the file.  For more information, see the following Remarks section.

</td>
</tr>
<tr>
<td>
FILE_DELETE_ON_CLOSE 

</td>
<td>
Delete the file when the last handle to it is passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff541863">FltClose</a>. 

</td>
</tr>
<tr>
<td>
FILE_OPEN_BY_FILE_ID

</td>
<td>
The file is being opened by ID. The file name contains the name of a device and a 64-bit ID to be used to open the file. 

</td>
</tr>
<tr>
<td>
FILE_OPEN_FOR_BACKUP_INTENT

</td>
<td>
The file is being opened for backup intent; therefore, the system should check for certain access rights and grant the caller the appropriate accesses to the file before checking the input <i>DesiredAccess</i> against the file's security descriptor. 

</td>
</tr>
<tr>
<td>
FILE_OPEN_REQUIRING_OPLOCK 

</td>
<td>
The file is being opened and an opportunistic lock (oplock) on the file is being requested as a single atomic operation. The file system checks for oplocks before it performs the create operation, and the create operationwill fail with a return code of STATUS_CANNOT_BREAK_OPLOCK if the create operation would break an existing oplock. 

<div class="alert"><b>Note</b>   The FILE_OPEN_REQUIRING_OPLOCK flag is available in Windows 7, Windows Server 2008 R2 and later Windows operating systems.</div>
<div> </div>
</td>
</tr>
<tr>
<td>
FILE_RESERVE_OPFILTER 

</td>
<td>
This flag allows an application to request a filter opportunistic lock (oplock) to prevent other applications from getting share violations.  If there are already open handles, the create request will fail with STATUS_OPLOCK_NOT_GRANTED.  For more information, see the following Remarks section.

</td>
</tr>
</table>
 


### -param EaBuffer [in, optional]

A pointer to a caller-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff545793">FILE_FULL_EA_INFORMATION</a>-structured buffer containing extended attribute (EA) information to be applied to the file. 


### -param EaLength [in]

Length, in bytes, of <i>EaBuffer</i>. 


### -param Flags [in]

Specifies options to be used during the creation of the create request. The following table lists the available options. 

<table>
<tr>
<th>Options Flags</th>
<th>Meaning</th>
</tr>
<tr>
<td>
IO_FORCE_ACCESS_CHECK

</td>
<td>
Indicates that the I/O manager must check the create request against the file's security descriptor.

</td>
</tr>
<tr>
<td>
IO_IGNORE_SHARE_ACCESS_CHECK

</td>
<td>
Indicates that the I/O manager should not perform share-access checks on the file object after it is created. However, the file system might still perform these checks. 

</td>
</tr>
<tr>
<td>
IO_NO_PARAMETER_CHECKING

</td>
<td>
Indicates that the parameters for this call should not be validated before attempting to issue the create request. Driver writers should use this flag with caution because certain invalid parameters can cause a system failure.

</td>
</tr>
</table>
 


## -returns



<b>FltCreateFile</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>
</td>
<td width="60%">
The specified <i>Filter</i> or <i>Instance</i> is being torn down. This status code can be received if the open crosses a volume mount point and the <i>Instance</i> parameter is non-<b>NULL</b>. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541935">FltCreateFile</a> encountered a pool allocation. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_MOUNT_POINT_NOT_RESOLVED</b></dt>
</dl>
</td>
<td width="60%">
The file or directory name contains a mount point that resolves to a volume other than the one that the specified minifilter driver instance is attached to. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_PATH_SYNTAX_BAD</b></dt>
</dl>
</td>
<td width="60%">
The <i>ObjectAttributes</i> parameter did not contain a <b>RootDirectory</b> member, but the <b>ObjectName</b> member in the OBJECT_ATTRIBUTES structure was an empty string or did not contain an OBJECT_NAME_PATH_SEPARATOR character. This indicates incorrect syntax for the object path.

</td>
</tr>
</table>
 

<div class="alert"><b>Note</b>  <b>FltCreateFile</b> might return STATUS_FILE_LOCK_CONFLICT as the return value or in the <b>Status</b> member of the IO_STATUS_BLOCK structure that is pointed to by the IoStatusBlock parameter. This would occur only if the NTFS log file is full, and an error occurs while <b>FltCreateFile</b> tries to handle this situation.</div>
<div> </div>



## -remarks



On versions of Windows earlier than Microsoft Windows Update Rollup for Windows 2000 SP4 and Windows Server 2003 SP1, minifilter drivers should call <b>FltCreateFile</b> instead of <a href="https://msdn.microsoft.com/library/windows/hardware/ff548418">IoCreateFile</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff548289">IoCreateFileSpecifyDeviceObjectHint</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff566424">ZwCreateFile</a>) to obtain a file handle for use with <b>Zw</b><i>Xxx</i> I/O routines such as <a href="https://msdn.microsoft.com/library/windows/hardware/ff567072">ZwReadFile</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff567052">ZwQueryInformationFile</a>.

On Microsoft Windows Update Rollup for Windows 2000 SP4, Windows Server 2003 SP1 and later, minifilter drivers can use <a href="https://msdn.microsoft.com/library/windows/hardware/ff541937">FltCreateFileEx</a> to obtain a file object pointer for use with <b>Flt...File</b> routines such as <a href="https://msdn.microsoft.com/library/windows/hardware/ff544286">FltReadFile</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff544610">FltWriteFile</a>. On earlier versions of Windows, the handle obtained from <b>FltCreateFile</b> can be converted into a file object pointer by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff558679">ObReferenceObjectByHandle</a> as follows: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS status;
status = ObReferenceObjectByHandle(
           handle,                 //Handle
           0,                      //DesiredAccess
           NULL,                   //ObjectType
           KernelMode,             //AccessMode
           &amp;handleFileObject,      //Object
           NULL);                  //HandleInformation</pre>
</td>
</tr>
</table></span></div>
<b>FltCreateFile</b> sends the create request only to the instances attached below the specified minifilter driver instance and to the file system. The specified instance and the instances attached above it do not receive the create request. If no instance is specified, the request goes to the top of the stack and is received by all instances and the file system. 

There are two alternate ways to specify the name of the file to be created or opened with <b>FltCreateFile</b>: 

<ul>
<li>
As a fully qualified pathname, supplied in the <b>ObjectName</b> member of the input <i>ObjectAttributes </i>

</li>
<li>
As a pathname relative to the directory file represented by the handle in the <b>RootDirectory </b>member of the input <i>ObjectAttributes </i>

</li>
</ul>
Any handle that is obtained from <b>FltCreateFile</b> must eventually be released by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff541863">FltClose</a>. 

Driver routines that do not run in the system process context must set the OBJ_KERNEL_HANDLE attribute for the <i>ObjectAttributes</i> parameter of <b>FltCreateFile</b>. Setting this attribute restricts the use of the handle that is returned by <b>FltCreateFile</b> to processes running in kernel mode. Otherwise, the handle can be accessed by the process in whose context the driver is running. 

Certain <i>DesiredAccess</i> flags and combinations of flags have the following effects: 

<ul>
<li>
For a caller to synchronize an I/O completion by waiting for the returned <i>FileHandle</i> to be set to the Signaled state, the SYNCHRONIZE flag must be set. 

</li>
<li>
Setting the FILE_WRITE_DATA flag for a file also allows writes beyond the end of the file to occur. The file is automatically extended for this type of write, as well. 

</li>
<li>
If only the FILE_EXECUTE and SYNCHRONIZE flags are set, the caller cannot use the returned <i>FileHandle</i> to directly read or write any data to or from the file. That is, all operations on the file must use system paging I/O to read or write file data. 

</li>
</ul>
The <i>ShareAccess</i> parameter determines whether separate threads can access the same file, possibly simultaneously. If both file openers have the privilege to access a file in the specified manner, the file can be successfully opened and shared. If the original caller of <b>FltCreateFile</b> does not specify FILE_SHARE_READ, FILE_SHARE_WRITE, or FILE_SHARE_DELETE, no other open operations can be performed on the file because the original caller is given exclusive access to the file. 

For a shared file to be successfully opened, the requested <i>DesiredAccess</i> to the file must be compatible with both the <i>DesiredAccess</i> and <i>ShareAccess</i> specifications of all preceding opens that have not yet been released with <a href="https://msdn.microsoft.com/library/windows/hardware/ff541863">FltClose</a>. That is, the <i>DesiredAccess</i> specified to <b>FltCreateFile</b> for a given file must not conflict with the accesses that other openers of the file have disallowed. 

<div class="alert"><b>Note</b>    If IO_IGNORE_SHARE_ACCESS_CHECK is specified in the <i>Flags</i> parameter, the I/O manager ignores the <i>ShareAccess</i> parameter. However, the file system might still perform access checks. Thus, it is important to specify the sharing mode you would like for the <i>ShareAccess </i>parameter, even when using the IO_IGNORE_SHARE_ACCESS_CHECK flag. </div>
<div> </div>
The <i>CreateDisposition</i> value FILE_SUPERSEDE requires that the caller have DELETE access to an existing file object. If so, a successful call to <b>FltCreateFile</b> with FILE_SUPERSEDE on an existing file effectively deletes that file and then recreates it. This implies that if the file has already been opened by another thread, it opened the file by specifying a <i>ShareAccess </i>parameter with the FILE_SHARE_DELETE flag set. Note that this type of disposition is consistent with the POSIX style of overwriting files. 

The <i>CreateDisposition</i> values FILE_OVERWRITE_IF and FILE_SUPERSEDE are similar. If <b>FltCreateFile</b> is called with an existing file and either of these <i>CreateDisposition</i> values, the file is replaced. 

Overwriting a file is semantically equivalent to a supersede operation, except for the following: 

<ul>
<li>
The caller must have write access to the file, rather than delete access. This implies that, if the file has already been opened by another thread, it opened the file with the FILE_SHARE_WRITE flag set in the input <i>ShareAccess</i>. 

</li>
<li>
The specified file attributes are logically ORed with those already on the file. This implies that if the file has already been opened by another thread, a subsequent caller of <b>FltCreateFile</b> cannot disable existing <i>FileAttributes</i> flags but can enable additional flags for the same file. Note that this style of overwriting files is consistent with MS-DOS, Windows 3.1, and OS/2. 

</li>
</ul>
The <i>CreateOptions</i> FILE_DIRECTORY_FILE value specifies that the file to be created or opened is a directory file. When a directory file is created, the file system creates an appropriate structure on the disk to represent an empty directory for that particular file system's on-disk structure. If this option was specified and the given file to be opened is not a directory file or if the caller specified an inconsistent <i>CreateOptions</i> or <i>CreateDisposition</i> value, the call to <b>FltCreateFile</b> fails. 

The <i>CreateOptions</i> FILE_NO_INTERMEDIATE_BUFFERING flag prevents the file system from performing any intermediate buffering on behalf of the caller. Specifying this value places certain restrictions on the caller's parameters to <b>Zw..File</b> routines, including the following: 

<ul>
<li>
Any byte <i>Offset</i> value passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff567072">ZwReadFile</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567121">ZwWriteFile</a> must be a multiple of the sector size. 

</li>
<li>
The <i>Length</i> passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff567072">ZwReadFile</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567121">ZwWriteFile</a> must be a multiple of the sector size. Note that specifying a read operation to a buffer whose length is exactly the sector size might result in fewer significant bytes being transferred to that buffer if the end of the file was reached during the transfer. 

</li>
<li>
Buffers must be aligned in accordance with the alignment requirement of the underlying storage device. This information can be obtained by calling <b>FltCreateFile</b> to get a handle for the file object that represents the physical device and then calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff567052">ZwQueryInformationFile</a> with that handle, specifying FileAlignmentInformation as the <i>FileInformationClass</i>. For more information about the system FILE_<i>XXX</i>_ALIGNMENT values, which are defined in ntifs.h, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff547807">Initializing a Device Object</a>. 

</li>
<li>
Calls to <a href="https://msdn.microsoft.com/library/windows/hardware/ff567096">ZwSetInformationFile</a> with the <i>FileInformationClass</i> parameter set to <b>FilePositionInformation</b> must specify an offset that is a multiple of the sector size. 

</li>
</ul>
The <i>CreateOptions</i> FILE_SYNCHRONOUS_IO_ALERT and FILE_SYNCHRONOUS_IO_NONALERT, which are mutually exclusive as their names suggest, specify that the file is being opened for synchronous I/O. This means that all I/O operations on the file are to be synchronous as long as they occur through the file object that the returned <i>FileHandle</i> refers to. All I/O on such a file is serialized across all threads by using the returned handle. With either of these <i>CreateOptions</i> set, the I/O Manager maintains the current file position offset in the file object's <b>CurrentByteOffset</b> field. This offset can be used in calls to <a href="https://msdn.microsoft.com/library/windows/hardware/ff567072">ZwReadFile</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff567121">ZwWriteFile</a>. It can also be queried or set by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff567052">ZwQueryInformationFile</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567096">ZwSetInformationFile</a>. 

If the <i>CreateOptions</i> FILE_OPEN_REPARSE_POINT flag is not specified and <b>FltCreateFile</b> attempts to open a file with a reparse point, normal reparse point processing occurs for the file.  If, on the other hand, the FILE_OPEN_REPARSE_POINT flag is specified, normal reparse processing does not occur and <b>FltCreateFile</b> attempts to directly open the reparse point file.  In either case, if the open operation was successful, <b>FltCreateFile</b> returns STATUS_SUCCESS; otherwise, the routine returns an NTSTATUS error code. <b>FltCreateFile</b> never returns STATUS_REPARSE.

The <i>CreateOptions</i> FILE_OPEN_REQUIRING_OPLOCK flag eliminates the time between when you open the file and request an oplock that could potentially enable a third party to open the file and get a sharing violation. An application can use the FILE_OPEN_REQUIRING_OPLOCK flag on <b>FltCreateFile</b> and then request any oplock. This ensures that an oplock owner will be notified of any later open request that causes a sharing violation. 

In Windows 7, if other handles exist on the file when an application uses the FILE_OPEN_REQUIRING_OPLOCK flag, the create operation will fail with STATUS_OPLOCK_NOT_GRANTED. This restriction no longer exists starting with Windows 8.

If this create operation would break an oplock that already exists on the file, then setting the FILE_OPEN_REQUIRING_OPLOCK flag will cause the create operation to fail with STATUS_CANNOT_BREAK_OPLOCK. The existing oplock will not be broken by this create operation.

 An application that uses this flag must request an oplock after this call succeeds, or all later attempts to open the file will be blocked without the benefit of typical oplock processing. Similarly, if this call succeeds but the later oplock request fails, an application that uses this flag must close its handle after it detects that the oplock request has failed.

<div class="alert"><b>Note</b>    The FILE_OPEN_REQUIRING_OPLOCK flag is available in Windows 7, Windows Server 2008 R2 and later Windows operating systems. The Microsoft file systems that implement this flag in Windows 7 are NTFS, FAT, and exFAT.</div>
<div> </div>
The <i>CreateOptions</i> flag FILE_RESERVE_OPFILTER allows an application to request a level 1, batch, or filter oplock to prevent other applications from getting share violations. However, FILE_RESERVE_OPFILTER is only practically useful for filter oplocks. To use it, you must complete the following steps:

<ol>
<li>Issue a create request with CreateOptions of FILE_RESERVE_OPFILTER, DesiredAccess of exactly FILE_READ_ATTRIBUTES, and ShareAccess of exactly FILE_SHARE_READ | FILE_SHARE_WRITE | FILE_SHARE_DELETE. <ul>
<li>If there are already open handles, the create request fails with STATUS_OPLOCK_NOT_GRANTED, and the next requested oplock also fails.  </li>
<li>If you open with more access or less sharing will also cause a failure of STATUS_OPLOCK_NOT_GRANTED.  </li>
</ul>
</li>
<li>
 If the create request succeeds, request an oplock. 

</li>
<li>
 Open another handle to the file to do I/O.  

</li>
</ol>
Step three makes this practical only for filter oplocks. The handle opened in step 3 can have a DesiredAccess that contains a maximum of FILE_READ_ATTRIBUTES | FILE_WRITE_ATTRIBUTES | FILE_READ_DATA | FILE_READ_EA | FILE_EXECUTE | SYNCHRONIZE | READ_CONTROL and still not break a filter oplock. However, any DesiredAccess greater than FILE_READ_ATTRIBUTES | FILE_WRITE_ATTRIBUTES | SYNCHRONIZE will break a level 1 or batch oplock and make the FILE_RESERVE_OPFILTER flag useless for those oplock types.

NTFS is the only Microsoft file system that implements FILE_RESERVE_OPFILTER. 

Minifilter drivers must use <a href="https://msdn.microsoft.com/library/windows/hardware/ff544516">FltSetInformationFile</a>, not <a href="https://msdn.microsoft.com/library/windows/hardware/ff567096">ZwSetInformationFile</a>, to rename a file. 

<div class="alert"><b>Note</b>    If you try to open a volume but only specify a combination of the following flags for the <i>DesiredAccess</i> parameter, <b>FltCreateFile</b> will open a handle, independent of the file system, that has direct access to the storage device for the volume.<dl>
<dd>
FILE_READ_ATTRIBUTES

</dd>
<dd>
READ_CONTROL

</dd>
<dd>
WRITE_DAC

</dd>
<dd>
WRITE_OWNER

</dd>
<dd>
SYNCHRONIZE

</dd>
</dl>
<p class="note">You must not use <b>FltCreateFile</b> to open a handle with direct access to the storage device for the volume or you will leak system resources. If you want to open a handle with direct access to a storage device, call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548283">IoCreateFileEx</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff548289">IoCreateFileSpecifyDeviceObjectHint</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff566424">ZwCreateFile</a> function instead.

</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538866">ACL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545793">FILE_FULL_EA_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541863">FltClose</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541937">FltCreateFileEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541939">FltCreateFileEx2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544286">FltReadFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544610">FltWriteFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547804">InitializeObjectAttributes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548418">IoCreateFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548289">IoCreateFileSpecifyDeviceObjectHint</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558679">ObReferenceObjectByHandle</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563689">SECURITY_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566424">ZwCreateFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567052">ZwQueryInformationFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567072">ZwReadFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567096">ZwSetInformationFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567121">ZwWriteFile</a>
 

 

