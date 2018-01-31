---
UID: NF:ntddk.IoCreateFileSpecifyDeviceObjectHint
title: IoCreateFileSpecifyDeviceObjectHint function
author: windows-driver-content
description: The IoCreateFileSpecifyDeviceObjectHint routine is used by file system filter drivers to send a create request only to the filters below a specified device object and to the file system.
old-location: ifsk\iocreatefilespecifydeviceobjecthint.htm
old-project: ifsk
ms.assetid: b7374625-6997-44db-b43b-748dab813fcd
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ntddk/IoCreateFileSpecifyDeviceObjectHint, ioref_729440cd-ded3-40cf-a0c9-c10f523cd774.xml, ifsk.iocreatefilespecifydeviceobjecthint, IoCreateFileSpecifyDeviceObjectHint, IoCreateFileSpecifyDeviceObjectHint routine [Installable File System Drivers]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: The IoCreateFileSpecifyDeviceObjectHint routine is available starting with Windows XP.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoCreateFileSpecifyDeviceObjectHint
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# IoCreateFileSpecifyDeviceObjectHint function


## -description


The <b>IoCreateFileSpecifyDeviceObjectHint</b> routine is used by file system filter drivers to send a create request only to the filters below a specified device object and to the file system.


## -syntax


````
NTSTATUS IoCreateFileSpecifyDeviceObjectHint(
  _Out_    PHANDLE            FileHandle,
  _In_     ACCESS_MASK        DesiredAccess,
  _In_     POBJECT_ATTRIBUTES ObjectAttributes,
  _Out_    PIO_STATUS_BLOCK   IoStatusBlock,
  _In_opt_ PLARGE_INTEGER     AllocationSize,
  _In_     ULONG              FileAttributes,
  _In_     ULONG              ShareAccess,
  _In_     ULONG              Disposition,
  _In_     ULONG              CreateOptions,
  _In_opt_ PVOID              EaBuffer,
  _In_     ULONG              EaLength,
  _In_     CREATE_FILE_TYPE   CreateFileType,
  _In_opt_ PVOID              InternalParameters,
  _In_     ULONG              Options,
  _In_opt_ PVOID              DeviceObject
);
````


## -parameters




#### - FileHandle [out]

A pointer to a variable that receives a handle for the file object if this call is successful. 


#### - DesiredAccess [in]

A bitmask of flags that specify the type of access that the caller requires to the file or directory. The set of system-defined <i>DesiredAccess</i> flags determines the following specific access rights for file objects.
<table>
<tr>
<th>DesiredAccess flags</th>
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
Extended attributes (EA) associated with the file can be read. 

</td>
</tr>
<tr>
<td>
READ_CONTROL

</td>
<td>
The access control list (<a href="..\wdm\ns-wdm-_acl.md">ACL</a>) and ownership information associated with the file can be read.

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
The discretionary access control list (<a href="..\wdm\ns-wdm-_acl.md">DACL</a>) associated with the file can be written.

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
Data can be read into memory from the file using system paging I/O. 

</td>
</tr>
</table> 

Callers of <b>IoCreateFileSpecifyDeviceObjectHint</b> can specify one or a combination of the following, possibly ORed with additional compatible flags from the preceding list of<i>DesiredAccess</i> flags, for any file object that does not represent a directory file. 


<table>
<tr>
<th>DesiredAccess to file values</th>
<th>Maps to DesiredAccess flags</th>
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
 



The STANDARD_RIGHTS_<i>XXX</i> are predefined system values used to enforce security on system objects.

If the FILE_DIRECTORY_FILE <i>CreateOptions</i> flag is set, callers of <b>IoCreateFileSpecifyDeviceObjectHint</b> can specify one or a combination of the following, possibly ORed with one or more compatible flags from the preceding list of<i>DesiredAccess</i> flags.


<table>
<tr>
<th>DesiredAccess to directory values</th>
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
 



The FILE_READ_DATA, FILE_WRITE_DATA, FILE_EXECUTE, and FILE_APPEND_DATA <i>DesiredAccess</i> flags are incompatible with creating or opening a directory file.


#### - ObjectAttributes [in]

A pointer to an <a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a> structure already initialized by the <a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a> routine. If the caller is running in the system process context, this parameter (<i>ObjectAttributes</i>) can be <b>NULL</b>. Otherwise, the caller must set the OBJ_KERNEL_HANDLE attribute in the call to the <b>InitializeObjectAttributes</b> routine. Members of the OBJECT_ATTRIBUTES structure for a file object include the following.
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
Specifies the number of bytes of <i>ObjectAttributes</i> data supplied. This value must be at least <b>sizeof</b>(OBJECT_ATTRIBUTES).

</td>
</tr>
<tr>
<td>
<b>PUNICODE_STRING ObjectName</b>

</td>
<td>
A pointer to a buffered Unicode string naming the file to be created or opened. This value must be a fully qualified file specification, unless it is the name of a file relative to the directory specified by <b>RootDirectory</b>. For example, \Device\Floppy1\myfile.dat or \??\B:\myfile.dat could be the fully qualified file specification, provided that the floppy driver and overlying file system are already loaded. (Note that \?? replaces \DosDevices as the name of the Win32 object namespace. \DosDevices will still work, but \?? is translated faster by the object manager.)

</td>
</tr>
<tr>
<td>
<b>HANDLERootDirectory</b>

</td>
<td>
Optionally specifies a handle to a directory that was obtained by a preceding call to <b>IoCreateFileSpecifyDeviceObjectHint</b>. If this value is <b>NULL</b>, the <b>ObjectName </b>member must be a fully qualified file specification that includes the full path to the target file. If this value is non-<b>NULL</b>, the <b>ObjectName</b> member specifies a file name relative to this directory.

</td>
</tr>
<tr>
<td>
<b>PSECURITY_DESCRIPTOR SecurityDescriptor </b>

</td>
<td>
Optionally specifies a security descriptor to be applied to a file. ACLs specified by such a security descriptor are only applied to the file when it is created. If the value is <b>NULL</b> when a file is created, the ACL placed on the file is file-system-dependent; most file systems propagate some part of such an ACL from the parent directory file combined with the caller's default ACL. 

</td>
</tr>
<tr>
<td>
<b>ULONGAttributes</b>

</td>
<td>
A set of flags that controls the file object attributes. If the caller is running in the system process context, this parameter can be zero. Otherwise, the caller must set the OBJ_KERNEL_HANDLE flag. The caller can also optionally set the OBJ_CASE_INSENSITIVE flag, which indicates that name-lookup code should ignore the case of <b>ObjectName</b> rather than performing an exact-match search. 

</td>
</tr>
</table> 


#### - IoStatusBlock [out]

A pointer to an <a href="..\wdm\ns-wdm-_io_status_block.md">IO_STATUS_BLOCK</a> structure that receives the final completion status and information about the requested operation. On return from <b>IoCreateFileSpecifyDeviceObjectHint</b>, the <b>Information</b> member contains one of the following values:

FILE_CREATED

FILE_OPENED

FILE_OVERWRITTEN

FILE_SUPERSEDED

FILE_EXISTS

FILE_DOES_NOT_EXIST


#### - AllocationSize [in, optional]

Optionally specifies the initial allocation size, in bytes, for the file. A nonzero value has no effect unless the file is being created, overwritten, or superseded. 


#### - FileAttributes [in]

Explicitly specified attributes are applied only when the file is created, superseded, or, in some cases, overwritten. By default, this value is FILE_ATTRIBUTE_NORMAL, which can be overridden by any other flag or by an ORed combination of compatible flags. Possible <i>FileAttributes</i> flags include the following. 
<table>
<tr>
<th>FileAttributes flags</th>
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
The file should be marked so that it will be archived.

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


#### - ShareAccess [in]

Specifies the type of share access to the file that the caller would like, as zero, or one, or a combination of the following flags. To request exclusive access, set this parameter to zero. If the IO_IGNORE_SHARE_ACCESS_CHECK flag is specified in the <i>Options</i> parameter, the I/O manager ignores this parameter. However, the file system might still perform access checks. Thus, it is important to specify the sharing mode you would like for this parameter, even when using the IO_IGNORE_SHARE_ACCESS_CHECK flag. For the greatest chance of avoiding sharing violation errors, specify all of the following share access flags. 
<table>
<tr>
<th>ShareAccess flags</th>
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


#### - Disposition [in]

Specifies a value that determines the action to be taken, depending on whether the file already exists. The value can be any of those described following.
<table>
<tr>
<th>Disposition values</th>
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


#### - CreateOptions [in]

Specifies the options to be applied when creating or opening the file. These options are specified as a compatible combination of the following flags.
<table>
<tr>
<th>CreateOptions flags</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FILE_DIRECTORY_FILE

</td>
<td>
The file being created or opened is a directory file. If this flag is set, the <i>Disposition </i>parameter must be set to one of FILE_CREATE, FILE_OPEN, or FILE_OPEN_IF. This flag is compatible with the following <i>CreateOptions</i> flags: FILE_SYNCHRONOUS_IO_ALERT, FILE_SYNCHRONOUS_IO_NONALERT, FILE_WRITE_THROUGH, FILE_OPEN_FOR_BACKUP_INTENT, and FILE_OPEN_BY_FILE_ID. 

</td>
</tr>
<tr>
<td>
FILE_NON_DIRECTORY_FILE

</td>
<td>
The file being opened must not be a directory file or this call will fail. The file object being opened must represent a data file. 

</td>
</tr>
<tr>
<td>
FILE_WRITE_THROUGH

</td>
<td>
System services, FSDs, and drivers that write data to the file must actually transfer the data into the file before any requested write operation is considered complete. 

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
Accesses to the file can be random, so no sequential read-ahead operations should be performed on the file by FSDs or the system.

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
All operations on the file are performed synchronously. Any wait on behalf of the caller is subject to premature termination from alerts. This flag also causes the I/O system to maintain the file position context. If this flag is set, the <i>DesiredAccess</i> SYNCHRONIZE flag also must be set. 

</td>
</tr>
<tr>
<td>
FILE_SYNCHRONOUS_IO_NONALERT

</td>
<td>
All operations on the file are performed synchronously. Waits that exist in the system to synchronize I/O queuing and completion are not subject to alerts. This flag also causes the I/O system to maintain the file position context. If this flag is set, the <i>DesiredAccess</i> SYNCHRONIZE flag also must be set.

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
If the extended attributes on an existing file being opened indicate that the caller must understand EAs to properly interpret the file, fail this request because the caller does not understand how to deal with EAs. 

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
Delete the file when the last handle to it is passed to <a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a>. 

</td>
</tr>
<tr>
<td>
FILE_OPEN_BY_FILE_ID

</td>
<td>
The file name specified in the <i>ObjectAttributes</i> parameter includes the 8-byte file reference number for the file. This number is assigned by the file system and is file-system-specific. If the file is a reparse point, the file name also includes the name of a device. Note: The FAT file system does not support FILE_OPEN_BY_FILE_ID. 

</td>
</tr>
<tr>
<td>
FILE_OPEN_FOR_BACKUP_INTENT

</td>
<td>
The file is being opened for backup intent, hence, the system should check for certain access rights and grant the caller the appropriate accesses to the file before checking the input <i>DesiredAccess</i> against the file's security descriptor. 

</td>
</tr>
<tr>
<td>
FILE_OPEN_REQUIRING_OPLOCK 

</td>
<td>
The file is being opened and an opportunistic lock (oplock) on the file is being requested as a single atomic operation. The file system checks for oplocks before it performs the create operation, and the create operation fails with a return code of STATUS_CANNOT_BREAK_OPLOCK if the create would break an existing oplock. 

<div class="alert"><b>Note</b>    The FILE_OPEN_REQUIRING_OPLOCK flag is available in Windows 7, Windows Server 2008 R2 and later Windows operating systems.</div>
<div> </div>
</td>
</tr>
<tr>
<td>
FILE_RESERVE_OPFILTER 

</td>
<td>
This flag allows an application to request a filter opportunistic lock (oplock) to prevent other applications from getting share violations.  If there are already open handles, the create request fails with STATUS_OPLOCK_NOT_GRANTED.  For more information, see the following Remarks section.

</td>
</tr>
</table> 


#### - EaBuffer [in, optional]

A pointer to a caller-supplied <a href="..\wdm\ns-wdm-_file_full_ea_information.md">FILE_FULL_EA_INFORMATION</a>-structured buffer containing extended attribute (EA) information to be applied to the file. 


#### - EaLength [in]

The length, in bytes, of <i>EaBuffer</i>. 


#### - CreateFileType [in]

Drivers must set this parameter to CreateFileTypeNone. 


#### - InternalParameters [in, optional]

Drivers must set this parameter to <b>NULL</b>. 


#### - Options [in]

Specifies options to be used during the creation of the create request. The following table lists the available options.
<table>
<tr>
<th>Options flags</th>
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
</table> 


#### - DeviceObject [in, optional]

A pointer to the device object to which the create request is to be sent. The device object must be a filter or file system device object in the file system driver stack for the volume on which the file or directory resides. This parameter is optional and can be <b>NULL</b>. If this parameter is <b>NULL</b>, the request will be sent to the device object at the top of the driver stack. 


## -returns


<b>IoCreateFileSpecifyDeviceObjectHint</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_OBJECT_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The specified <i>DeviceObject</i> is not attached to the file system driver stack for the volume specified in the file or directory name.  This error can also occur if the name contains a reparse point other than a mount point.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_MOUNT_POINT_NOT_RESOLVED</b></dt>
</dl>
</td>
<td width="60%">
The file or directory name contains a mount point that resolves to a volume other than the one to which the specified <i>DeviceObject</i> is attached. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_PATH_SYNTAX_BAD</b></dt>
</dl>
</td>
<td width="60%"></td>
</tr>
</table> 
<div class="alert"><b>Note</b>  <b>IoCreateFileSpecifyDeviceObjectHint</b> might return STATUS_FILE_LOCK_CONFLICT as the return value or in the <b>Status</b> member of the IO_STATUS_BLOCK structure that is pointed to by the IoStatusBlock parameter. This would occur only if the NTFS log file is full, and an error occurs while <b>IoCreateFileSpecifyDeviceObjectHint</b> tries to handle this situation.

</div><div> </div>


## -remarks


This routine is used by file system filter drivers to send a create request only to the filters below a specified device object and to the file system. Filters that are attached above the specified device object in the driver stack do not receive the create request.  
<div class="alert"><b>Note</b>  The Windows Vista <a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a> routine is similar to the <b>IoCreateFileSpecifyDeviceObjectHint</b> routine but provides greater functionality than the <b>IoCreateFileSpecifyDeviceObjectHint</b> routine, including access to extra create parameters (ECPs) and transaction information.</div><div> </div>If you use the <a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a> routine instead of the <b>IoCreateFileSpecifyDeviceObjectHint</b> routine, note that the <i>DriverContext</i> parameter of the <b>IoCreateFileSpecifyDeviceObjectHint</b> routine has been moved to the <b>DeviceObjectHint</b> member of the <a href="..\ntddk\ns-ntddk-_io_driver_create_context.md">IO_DRIVER_CREATE_CONTEXT</a> structure.  The IO_DRIVER_CREATE_CONTEXT structure is passed into the <b>IoCreateFileEx</b> routine through its <i>DriverContext</i> parameter.

File system filter drivers call <b>IoCreateFileSpecifyDeviceObjectHint</b> to send a create request only to a specified device object, the filters attached below it, and the file system. Filters attached above the specified device object in the driver stack do not receive the create request. The same is <b>true</b> for any cleanup or close requests on the file object that is created by <b>IoCreateFileSpecifyDeviceObjectHint</b>. 

There are two alternate ways to specify the name of the file to be created or opened using <b>IoCreateFileSpecifyDeviceObjectHint</b>: 
<ol>
<li>
As a fully qualified pathname, supplied in the <b>ObjectName</b> member of the input <i>ObjectAttributes </i>

</li>
<li>
As a pathname relative to the directory file that is represented by the handle in the <b>RootDirectory</b> member of the input <i>ObjectAttributes </i>

</li>
</ol>Any handle that is obtained from <b>IoCreateFileSpecifyDeviceObjectHint</b> must eventually be released by calling <a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a>. 

Driver routines that run in a process context other than that of the system process must set the OBJ_KERNEL_HANDLE attribute for the <i>ObjectAttributes</i> parameter of <b>IoCreateFileSpecifyDeviceObjectHint</b>. This restricts the use of the handle that is returned by <b>IoCreateFileSpecifyDeviceObjectHint</b> to processes running in kernel mode. Otherwise, the handle can be accessed by the process in whose context the driver is running. 

Certain <i>DesiredAccess</i> flags and combinations of flags have the following effects: 
<ul>
<li>
For a caller to synchronize an I/O completion by waiting for the returned <i>FileHandle</i> to be set to the Signaled state, the SYNCHRONIZE flag must be set. 

</li>
<li>
If only the FILE_APPEND_DATA and SYNCHRONIZE flags are set, the caller can write only to the end of the file, and any offset information about writes to the file is ignored. However, the file will automatically be extended as necessary for this type of write operation. 

</li>
<li>
Setting the FILE_WRITE_DATA flag for a file also allows writes beyond the end of the file to occur. The file is automatically extended for this type of write, as well. 

</li>
<li>
If only the FILE_EXECUTE and SYNCHRONIZE flags are set, the caller cannot directly read or write any data in the file using the returned <i>FileHandle</i>; that is, all operations on the file occur through the system pager in response to instruction and data accesses. 

</li>
</ul>The <i>ShareAccess</i> parameter determines whether separate threads can access the same file, possibly simultaneously. Provided that both file openers have the privilege to access a file in the specified manner, the file can be successfully opened and shared. If the original caller of <b>IoCreateFileSpecifyDeviceObjectHint</b> does not specify FILE_SHARE_READ, FILE_SHARE_WRITE, or FILE_SHARE_DELETE, no other open operations can be performed on the file: that is, the original caller is given exclusive access to the file. 

In order for a shared file to be successfully opened, the requested <i>DesiredAccess</i> to the file must be compatible with both the <i>DesiredAccess</i> and <i>ShareAccess</i> specifications of all preceding opens that have not yet been released with <a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a>. That is, the <i>DesiredAccess</i> specified to <b>IoCreateFileSpecifyDeviceObjectHint</b> for a given file must not conflict with the accesses that other openers of the file have disallowed. 


<div class="alert"><b>Note</b>    If IO_IGNORE_SHARE_ACCESS_CHECK is specified in the <i>Options</i> parameter, the I/O manager ignores the <i>ShareAccess</i> parameter. However, the file system might still perform access checks. Thus, it is important to specify the sharing mode you would like for the <i>ShareAccess </i>parameter, even when using the IO_IGNORE_SHARE_ACCESS_CHECK flag. </div>
<div> </div>


The <i>Disposition</i> value FILE_SUPERSEDE requires that the caller have DELETE access to a existing file object. If so, a successful call to <b>IoCreateFileSpecifyDeviceObjectHint</b> with FILE_SUPERSEDE on an existing file effectively deletes that file, and then recreates it. This implies that if the file has already been opened by another thread, it opened the file by specifying a <i>ShareAccess </i>parameter with the FILE_SHARE_DELETE flag set. Note that this type of disposition is consistent with the POSIX style of overwriting files. 

The <i>Disposition</i> values FILE_OVERWRITE_IF and FILE_SUPERSEDE are similar. If <b>IoCreateFileSpecifyDeviceObjectHint</b> is called with an existing file and either of these <i>Disposition</i> values, the file will be replaced. 

Overwriting a file is semantically equivalent to a supersede operation, except for the following: 
<ul>
<li>
The caller must have write access to the file, rather than delete access. This implies that if the file has already been opened by another thread, it opened the file with the FILE_SHARE_WRITE flag set in the input <i>ShareAccess</i>. 

</li>
<li>
The specified file attributes are logically ORed with those already on the file. This implies that if the file has already been opened by another thread, a subsequent caller of <b>IoCreateFileSpecifyDeviceObjectHint</b> cannot disable existing <i>FileAttributes</i> flags but can enable additional flags for the same file. Note that this style of overwriting files is consistent with MS-DOS, Windows 3.1, and with OS/2. 

</li>
</ul>The <i>CreateOptions</i> FILE_DIRECTORY_FILE value specifies that the file to be created or opened is a directory file. When a directory file is created, the file system creates an appropriate structure on the disk to represent an empty directory for that particular file system's on-disk structure. If this option was specified and the given file to be opened is not a directory file, or if the caller specified an inconsistent <i>CreateOptions</i> or <b>Disposition</b> value, the call to <b>IoCreateFileSpecifyDeviceObjectHint</b> will fail. 

The <i>CreateOptions</i> FILE_NO_INTERMEDIATE_BUFFERING flag prevents the file system from performing any intermediate buffering on behalf of the caller. Specifying this value places certain restrictions on the caller's parameters to other <b>Zw..File</b> routines, including the following: 
<ul>
<li>
Any byte <i>Offset</i> value that is passed to <a href="..\wdm\nf-wdm-zwreadfile.md">ZwReadFile</a> or <a href="..\wdm\nf-wdm-zwwritefile.md">ZwWriteFile</a> must be a multiple of the sector size of the underlying device. 

</li>
<li>
The <i>Length</i> that is passed to <a href="..\wdm\nf-wdm-zwreadfile.md">ZwReadFile</a> or <a href="..\wdm\nf-wdm-zwwritefile.md">ZwWriteFile</a> must be a multiple of the sector size. Note that specifying a read operation to a buffer whose length is exactly the sector size might result in a lesser number of significant bytes being transferred to that buffer if the end of the file was reached during the transfer. 

</li>
<li>
Buffers must be aligned in accordance with the alignment requirement of the underlying device. This information can be obtained by calling <b>IoCreateFileSpecifyDeviceObjectHint</b> to get a handle for the file object that represents the physical device and then calling <a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a> with that handle. For a list of the system FILE_<i>XXX</i>_ALIGNMENT values, see <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>. 

</li>
<li>
Calls to <a href="..\wdm\nf-wdm-zwsetinformationfile.md">ZwSetInformationFile</a> with the <i>FileInformationClass</i> parameter set to <b>FilePositionInformation</b> must specify an offset that is a multiple of the sector size. 

</li>
</ul>The mutually exclusive <i>CreateOptions</i>, FILE_SYNCHRONOUS_IO_ALERT and FILE_SYNCHRONOUS_IO_NONALERT, specify that all I/O operations on the file are to be synchronous as long as they occur through the file object referred to by the returned <i>FileHandle</i>. All I/O on such a file is serialized across all threads using the returned handle. With either of these <i>CreateOptions</i>, the <i>DesiredAccess</i> SYNCHRONIZE flag must be set so that the I/O Manager will use the file object as a synchronization object. With either of these <i>CreateOptions</i> set, the I/O Manager maintains the "file position context" for the file object, an internal, current file position offset. This offset can be used in calls to <a href="..\wdm\nf-wdm-zwreadfile.md">ZwReadFile</a> and <a href="..\wdm\nf-wdm-zwwritefile.md">ZwWriteFile</a>. Its position also can be queried by calling <a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a>, or set by calling <a href="..\wdm\nf-wdm-zwsetinformationfile.md">ZwSetInformationFile</a>.  

If the <i>CreateOptions</i> FILE_OPEN_REPARSE_POINT flag is not specified and <b>IoCreateFileSpecifyDeviceObjectHint</b> attempts to open a file with a reparse point, normal reparse point processing occurs for the file.  If, on the other hand, the FILE_OPEN_REPARSE_POINT flag is specified, normal reparse processing does not occur and <b>IoCreateFileSpecifyDeviceObjectHint</b> attempts to directly open the reparse point file.  In either case, if the open operation was successful, <b>IoCreateFileSpecifyDeviceObjectHint</b> returns STATUS_SUCCESS; otherwise, the routine returns an NTSTATUS error code. <b>IoCreateFileSpecifyDeviceObjectHint</b> never returns STATUS_REPARSE.

The <i>CreateOptions</i> FILE_OPEN_REQUIRING_OPLOCK flag eliminates the time between when you open the file and request an oplock that could potentially enable a third party to open the file and get a sharing violation. An application can use the FILE_OPEN_REQUIRING_OPLOCK flag on <b>IoCreateFileSpecifyDeviceObjectHint</b> and then request any oplock. This ensures that an oplock owner will be notified of any later open request that causes a sharing violation. 

In Windows 7, if other handles exist on the file when an application uses the FILE_OPEN_REQUIRING_OPLOCK flag, the create operation will fail with STATUS_OPLOCK_NOT_GRANTED. This restriction no longer exists starting with Windows 8.

If this create operation would break an oplock that already exists on the file, then setting the FILE_OPEN_REQUIRING_OPLOCK flag will cause the create operation to fail with STATUS_CANNOT_BREAK_OPLOCK. The existing oplock will not be broken by this create operation.

 An application that uses this flag must request an oplock after this call succeeds, or all later attempts to open the file will be blocked without the benefit of typical oplock processing. Similarly, if this call succeeds but the later oplock request fails, an application that uses this flag must close its handle after it detects that the oplock request has failed.
<div class="alert"><b>Note</b>    The FILE_OPEN_REQUIRING_OPLOCK flag is available in Windows 7, Windows Server 2008 R2 and later Windows operating systems. The Microsoft file systems that implement this flag in Windows 7 are NTFS, FAT, and exFAT.</div><div> </div>The <i>CreateOptions</i> flag FILE_RESERVE_OPFILTER allows an application to request a level 1, batch, or filter oplock to prevent other applications from getting share violations. However, FILE_RESERVE_OPFILTER is only practically useful for filter oplocks. To use it, you must complete the following steps:
<ol>
<li>Issue a create request with <i>CreateOptions</i> of FILE_RESERVE_OPFILTER, <i>DesiredAccess</i> of exactly FILE_READ_ATTRIBUTES, and <i>ShareAccess</i> of exactly FILE_SHARE_READ | FILE_SHARE_WRITE | FILE_SHARE_DELETE. <ul>
<li>If there are already open handles, the create request will fail with STATUS_OPLOCK_NOT_GRANTED, and the next requested oplock also fails.  </li>
<li>If you open with more access or less sharing will also cause a failure of STATUS_OPLOCK_NOT_GRANTED.  </li>
</ul>
</li>
<li>
 If the create request succeeds, request an oplock. 

</li>
<li>
 Open another handle to the file to do I/O.  

</li>
</ol>Step three makes this practical only for filter oplocks. The handle opened in step 3 can have a <i>DesiredAccess</i> that contains a maximum of FILE_READ_ATTRIBUTES | FILE_WRITE_ATTRIBUTES | FILE_READ_DATA | FILE_READ_EA | FILE_EXECUTE | SYNCHRONIZE | READ_CONTROL and still not break a filter oplock. However, any <i>DesiredAccess</i> greater than FILE_READ_ATTRIBUTES | FILE_WRITE_ATTRIBUTES | SYNCHRONIZE will break a level 1 or batch oplock and make the FILE_RESERVE_OPFILTER flag useless for those oplock types.

NTFS is the only Microsoft file system that implements FILE_RESERVE_OPFILTER. 

<b>IoCreateFileSpecifyDeviceObjectHint</b> cannot be used to obtain a handle to a volume. 

If the file name path that is passed to <b>IoCreateFileSpecifyDeviceObjectHint</b> contains a reparse point, the reparse point must resolve to the same volume where the file or directory resides.  If it does not, either the error STATUS_INVALID_DEVICE_OBJECT_PARAMETER or STATUS_MOUNT_POINT_NOT_RESOLVED is returned.



## -see-also

<a href="..\wdm\ns-wdm-_file_full_ea_information.md">FILE_FULL_EA_INFORMATION</a>

<a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a>

<a href="..\wdm\nf-wdm-zwwritefile.md">ZwWriteFile</a>

<a href="..\wdm\nf-wdm-iocreatefile.md">IoCreateFile</a>

<a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a>

<a href="..\wdm\ns-wdm-_acl.md">ACL</a>

<a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a>

<a href="..\ntifs\nf-ntifs-iocheckeabuffervalidity.md">IoCheckEaBufferValidity</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>

<a href="..\wdm\nf-wdm-zwreadfile.md">ZwReadFile</a>

<a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a>

<a href="..\wdm\nf-wdm-zwsetinformationfile.md">ZwSetInformationFile</a>

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>

<a href="..\ntddk\ns-ntddk-_io_driver_create_context.md">IO_DRIVER_CREATE_CONTEXT</a>

<a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IoCreateFileSpecifyDeviceObjectHint routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

