---
UID: NF:fltkernel.FltCreateFileEx2
title: FltCreateFileEx2 function
author: windows-driver-content
description: Minifilter drivers call FltCreateFileEx2 to create a new file or open an existing file. This routine also includes an optional create context parameter.
old-location: ifsk\fltcreatefileex2.htm
old-project: ifsk
ms.assetid: e662472d-4d72-449e-91d7-119bd59e0943
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: fltkernel/FltCreateFileEx2, FltCreateFileEx2 routine [Installable File System Drivers], FltCreateFileEx2, ifsk.fltcreatefileex2, FltApiRef_a_to_d_21436e16-822a-4250-abac-10346593435f.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in starting with Windows Vista.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Fltmgr.lib
-	Fltmgr.dll
apiname:
-	FltCreateFileEx2
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltCreateFileEx2 function


## -description


Minifilter drivers call <b>FltCreateFileEx2</b> to create a new file or open an existing file.  This routine also includes an optional create context parameter.


## -syntax


````
NTSTATUS FltCreateFileEx2(
  _In_      PFLT_FILTER               Filter,
  _In_opt_  PFLT_INSTANCE             Instance,
  _Out_     PHANDLE                   FileHandle,
  _Out_opt_ PFILE_OBJECT              *FileObject,
  _In_      ACCESS_MASK               DesiredAccess,
  _In_      POBJECT_ATTRIBUTES        ObjectAttributes,
  _Out_     PIO_STATUS_BLOCK          IoStatusBlock,
  _In_opt_  PLARGE_INTEGER            AllocationSize,
  _In_      ULONG                     FileAttributes,
  _In_      ULONG                     ShareAccess,
  _In_      ULONG                     CreateDisposition,
  _In_      ULONG                     CreateOptions,
  _In_opt_  PVOID                     EaBuffer,
  _In_      ULONG                     EaLength,
  _In_      ULONG                     Flags,
  _In_opt_  PIO_DRIVER_CREATE_CONTEXT DriverContext
);
````


## -parameters




### -param Filter [in]

An opaque filter pointer for the caller. 


### -param Instance [in, optional]

An opaque instance pointer for the minifilter driver instance that the create request is to be sent to. The instance must be attached to the volume where the file or directory resides. This parameter is optional and can be <b>NULL</b>. If this parameter is <b>NULL</b>, the request is sent to the device object at the top of the file system driver stack for the volume. If this parameter is non-<b>NULL</b>, the request is sent only to minifilter driver instances that are attached below the specified instance. 


### -param FileHandle [out]

A pointer to a caller-allocated variable that receives the file handle if the call to <b>FltCreateFileEx2</b> is successful. 


### -param FileObject [out, optional]

A pointer to a caller-allocated variable that receives the file object pointer if the call to <b>FltCreateFileEx2</b> is successful. This parameter is optional and can be <b>NULL</b>. 


### -param DesiredAccess [in]

A bitmask of flags that specify the type of access that the caller requires to the file or directory. The set of system-defined <i>DesiredAccess</i> flags determines the following specific access rights for file objects. 
<div class="alert"><b>Note</b>  Do not specify FILE_READ_DATA, FILE_WRITE_DATA, FILE_EXECUTE, or FILE_APPEND_DATA when creating or opening a directory.</div><div> </div><table>
<tr>
<th><i>DesiredAccess</i> flags</th>
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
<i>FileAttributes</i> flags can be read.  For additional information, see the table of valid flag values in the <i>FileAttributes</i> parameter description below.

</td>
</tr>
<tr>
<td>
FILE_READ_EA

</td>
<td>
Extended attributes that are associated with the file can be read. 

</td>
</tr>
<tr>
<td>
READ_CONTROL

</td>
<td>
The access control list (<a href="..\wdm\ns-wdm-_acl.md">ACL</a>) and ownership information that is associated with the file can be read.

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
Extended attributes that are associated with the file can be written. 

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
The discretionary access control list (<a href="..\wdm\ns-wdm-_acl.md">DACL</a>) that is associated with the file can be written.

</td>
</tr>
<tr>
<td>
WRITE_OWNER 

</td>
<td>
Ownership information that is associated with the file can be written.

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

Alternatively, for any file object that does not represent a directory, you can specify one or more of the following generic <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> flags. The following table illustrates that a flag value in the left column is equivalent to the set of flag values in the right column. (The STANDARD_RIGHTS_<i>XXX</i> flags are predefined system values that are used to enforce security on system objects.) You can also combine these generic flags with additional flags from the preceding table. 
<table>
<tr>
<th><i>DesiredAccess</i> values</th>
<th>Maps to <i>DesiredAccess</i> flags</th>
</tr>
<tr>
<td>
GENERIC_READ

</td>
<td>
STANDARD_RIGHTS_READ, FILE_READ_DATA, FILE_READ_ATTRIBUTES, FILE_READ_EA, and SYNCHRONIZE 

</td>
</tr>
<tr>
<td>
GENERIC_WRITE

</td>
<td>
STANDARD_RIGHTS_WRITE, FILE_WRITE_DATA, FILE_WRITE_ATTRIBUTES, FILE_WRITE_EA, FILE_APPEND_DATA, and SYNCHRONIZE 

</td>
</tr>
<tr>
<td>
GENERIC_EXECUTE

</td>
<td>
STANDARD_RIGHTS_EXECUTE, SYNCHRONIZE, FILE_READ_ATTRIBUTES, and FILE_EXECUTE 

</td>
</tr>
</table> 

For directories, you can specify one or more of the following ACCESS_MASK flags, which you can also combine with any compatible flags that were described in the preceding tables. 
<table>
<tr>
<th><i>DesiredAccess</i> flags - for directories</th>
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

A pointer to an opaque <a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a> structure that is already initialized with <a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a>. If the caller is running in the system process context, this parameter can be <b>NULL</b>. Otherwise, the caller must set the OBJ_KERNEL_HANDLE attribute in the call to <b>InitializeObjectAttributes</b>. Members of this structure for a file object are listed in the following table. 
<table>
<tr>
<th>Member</th>
<th>Value</th>
</tr>
<tr>
<td>
<b>ULONG </b><b>Length</b>

</td>
<td>
The number of bytes of data that are contained in the structure pointed to by <i>ObjectAttributes</i>. This value must be at least <b>sizeof</b>(OBJECT_ATTRIBUTES).

</td>
</tr>
<tr>
<td>
<b>PUNICODE_STRING </b><b>ObjectName</b>

</td>
<td>
A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains the name of the file to be created or opened. This name must be a fully qualified file specification or the name of a device object unless it is the name of a file relative to the directory specified by <b>RootDirectory</b>. For example, "\Device\Floppy1\myfile.dat" or "\??\B:\myfile.dat" could both be valid file specifications, if the floppy driver and overlying file system are already loaded. (Note: "\??" replaces "\DosDevices" as the name of the Win32 object namespace. "\DosDevices" still works, but "\??" is translated faster by the object manager.)

</td>
</tr>
<tr>
<td>
<b>HANDLE </b><b>RootDirectory</b>

</td>
<td>
An optional handle to a directory, obtained by a preceding call to <b>FltCreateFileEx2</b>. If this value is <b>NULL</b>, the <i>ObjectName</i>member must be a fully qualified file specification that includes the full path to the target file. If this value is non-<b>NULL</b>, the <i>ObjectName</i> member specifies a file name that is relative to this directory.

</td>
</tr>
<tr>
<td>
<b>PSECURITY_DESCRIPTOR </b><b>SecurityDescriptor</b>

</td>
<td>
An optional security descriptor (<a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>) to be applied to a file. <a href="..\wdm\ns-wdm-_acl.md">ACLs</a> specified by such a security descriptor are only applied to the file when it is created. If the value is <b>NULL</b> when a file is created, the ACL placed on the file is file-system-dependent. Most file systems propagate some part of such an ACL from the parent directory file combined with the caller's default ACL. 

</td>
</tr>
<tr>
<td>
<b>ULONG </b><b>Attributes</b>

</td>
<td>
A set of flags that controls the file object attributes. If the caller is running in the system process context, this parameter can be zero. Otherwise, the caller must set the OBJ_KERNEL_HANDLE flag. The caller can also optionally set the OBJ_CASE_INSENSITIVE flag, which indicates that name-lookup code should ignore the case of <i>ObjectName</i> rather than performing an exact-match search. 

</td>
</tr>
</table> 


### -param IoStatusBlock [out]

A pointer to an <a href="..\wdm\ns-wdm-_io_status_block.md">IO_STATUS_BLOCK</a> structure that receives the final completion status and information about the requested operation. On return from <b>FltCreateFileEx2</b>, the <b>Information</b> member of the variable contains one of the following values.

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
<th><i>FileAttributes</i> flags</th>
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

Specifies the type of share access to the file that the caller requires, as zero or one, or a combination of the following flags. If the IO_IGNORE_SHARE_ACCESS_CHECK flag is specified in the <i>Flags</i> parameter, the I/O manager ignores this parameter. However, the file system might still perform access checks. Thus, it is important to specify the sharing mode you would like for this parameter, even when using the IO_IGNORE_SHARE_ACCESS_CHECK flag. For the greatest chance of avoiding sharing violation errors, specify all of the following share access flags. 
<table>
<tr>
<th><i>ShareAccess</i> flags</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FILE_SHARE_READ

</td>
<td>
The file can be opened for read access by other threads' calls to <b>FltCreateFileEx2</b>.

</td>
</tr>
<tr>
<td>
FILE_SHARE_WRITE

</td>
<td>
The file can be opened for write access by other threads' calls to <b>FltCreateFileEx2</b>.

</td>
</tr>
<tr>
<td>
FILE_SHARE_DELETE

</td>
<td>
The file can be opened for delete access by other threads' calls to <b>FltCreateFileEx2</b>.

</td>
</tr>
</table> 


### -param CreateDisposition [in]

Specifies a value that determines the action to be taken, depending on whether the file already exists. The value can be any of those described in the following table. 
<table>
<tr>
<th><i>CreateDisposition</i> values</th>
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
<th><i>CreateOptions</i> flags</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FILE_DIRECTORY_FILE

</td>
<td>
The file that is being created or opened is a directory file. With this flag, the <i>CreateDisposition</i> parameter must be set to one of FILE_CREATE, FILE_OPEN, or FILE_OPEN_IF. With this flag, other compatible <i>CreateOptions</i> flags include only the following: FILE_SYNCHRONOUS_IO_ALERT, FILE_SYNCHRONOUS_IO_NONALERT, FILE_WRITE_THROUGH, FILE_OPEN_FOR_BACKUP_INTENT, and FILE_OPEN_BY_FILE_ID. 

</td>
</tr>
<tr>
<td>
FILE_NON_DIRECTORY_FILE

</td>
<td>
The file that is being opened must not be a directory file or this call fails. The file object that is being opened can represent a data file; a logical, virtual, or physical device; or a volume. 

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
The file cannot be cached or buffered in a driver's internal buffers. This flag is incompatible with the <i>DesiredAccess</i>FILE_APPEND_DATA flag. 

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
If the extended attributes on an existing file that is being opened indicate that the caller must understand extended attributes to properly interpret the file, fail this request because the caller does not understand how to deal with extended attributes. 

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
Delete the file when the last handle to it is passed to <a href="..\fltkernel\nf-fltkernel-fltclose.md">FltClose</a>. 

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
The file is being opened for backup intent. Therefore, the system should check for certain access rights and grant the caller the appropriate accesses to the file before checking the input <i>DesiredAccess</i> against the file's security descriptor. 

</td>
</tr>
<tr>
<td>
FILE_OPEN_REQUIRING_OPLOCK 

</td>
<td>
The file is being opened and an opportunistic lock (oplock) on the file is being requested as a single atomic operation. The file system checks for oplocks before it performs the create operation, and the create will fail with a return code of STATUS_CANNOT_BREAK_OPLOCK if the create would break an existing oplock. 

<div class="alert"><b>Note</b>    The FILE_OPEN_REQUIRING_OPLOCK flag is available in Windows 7, Windows Server 2008 R2 and later Windows operating systems.</div>
<div> </div>
</td>
</tr>
<tr>
<td>
FILE_RESERVE_OPFILTER 

</td>
<td>
This flag allows an application to request a Filter opportunistic lock (oplock) to prevent other applications from getting share violations.  If there are already open handles, the create request will fail with STATUS_OPLOCK_NOT_GRANTED.  For more information, see the following Remarks section.

</td>
</tr>
</table> 


### -param EaBuffer [in, optional]

A pointer to a caller-supplied <a href="..\wdm\ns-wdm-_file_full_ea_information.md">FILE_FULL_EA_INFORMATION</a> buffer that contains extended attribute (EA) information to be applied to the file. 


### -param EaLength [in]

Length, in bytes, of <i>EaBuffer</i>. 


### -param Flags [in]

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
<tr>
<td>
IO_STOP_ON_SYMLINK

</td>
<td>
The I/O manager or the file system will return STATUS_STOPPED_ON_SYMLINK if a symbolic link is encountered while opening or creating the file.

</td>
</tr>
<tr>
<td>
IO_NO_PARAMETER_CHECKING

</td>
<td>
Indicates that the parameters for this call should not be validated before attempting to issue the create request. Minifilter writers should use this flag with caution as certain invalid parameters can cause a system failure. For more information, see Remarks.

</td>
</tr>
</table> 


### -param DriverContext [in, optional]

Optional pointer to an <a href="..\ntddk\ns-ntddk-_io_driver_create_context.md">IO_DRIVER_CREATE_CONTEXT</a> structure already initialized by <a href="..\ntddk\nf-ntddk-ioinitializedrivercreatecontext.md">IoInitializeDriverCreateContext</a>.


## -returns


<b>FltCreateFileEx2</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 
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
The filter or instance specified in the <i>Filter</i> or <i>Instance</i> parameters is being torn down. This status code can be received if the open request crosses a volume mount point and the <i>Instance</i> parameter is non-<b>NULL</b>. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>FltCreateFileEx2</b> encountered a pool allocation failure. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_MOUNT_POINT_NOT_RESOLVED</b></dt>
</dl>
</td>
<td width="60%">
The file or directory name contains a mount point that resolves to a volume other than the one that the specified minifilter driver instance is attached to. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_PATH_SYNTAX_BAD</b></dt>
</dl>
</td>
<td width="60%">
The <i>ObjectAttributes</i> parameter did not contain a <b>RootDirectory</b> member, but the <b>ObjectName</b> member in the OBJECT_ATTRIBUTES structure was an empty string or did not contain an OBJECT_NAME_PATH_SEPARATOR character. This error code indicates incorrect syntax for the object path. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
This value will be returned if the <i>DriverContext</i> parameter points to a valid IO_DRIVER_CREATE_CONTEXT structure and the <b>DeviceObjectHint</b> member of this structure is not <b>NULL</b>. This is an error code.

</td>
</tr>
</table> 
<div class="alert"><b>Note</b>  <b>FltCreateFileEx2</b> might return STATUS_FILE_LOCK_CONFLICT as the return value or in the <b>Status</b> member of the IO_STATUS_BLOCK structure that is pointed to by the IoStatusBlock parameter. This would occur only if the NTFS log file is full, and an error occurs while <b>FltCreateFileEx2</b> tries to handle this situation.</div><div> </div>


## -remarks


<b>FltCreateFileEx2</b> is similar to <a href="..\fltkernel\nf-fltkernel-fltcreatefile.md">FltCreateFile</a> and <a href="..\fltkernel\nf-fltkernel-fltcreatefileex.md">FltCreateFileEx</a>, except that it supports the new <i>DriverContext</i> input parameter.

To specify an extra create parameter (ECP) as part of a create operation, initialize the <b>ExtraCreateParameter</b> member of the IO_DRIVER_CREATE_CONTEXT structure with the <a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameterlist.md">FltAllocateExtraCreateParameterList</a> routine.  If ECPs are used, they must be created, manipulated, and freed using the appropriate routines - the following <i>See Also</i> section lists these routines.  Upon returning from the call of <b>FltCreateFileEx2</b>, the ECP list is unchanged and may be passed to additional calls of <b>FltCreateFileEx2</b> for other create operations.  Note that the operating system does not automatically deallocate the ECP list structure - the caller of <b>FltCreateFileEx2</b> must deallocate this structure by calling the <a href="..\fltkernel\nf-fltkernel-fltfreeextracreateparameterlist.md">FltFreeExtraCreateParameterList</a> routine.

To create/open a file in the context of a transaction, set the <b>TxnParameters</b> member of the IO_DRIVER_CREATE_CONTEXT structure to the value returned by the <a href="..\ntddk\nf-ntddk-iogettransactionparameterblock.md">IoGetTransactionParameterBlock</a> routine.

For additional information regarding transactions, see <a href="http://go.microsoft.com/fwlink/p/?linkid=66161">Transaction Management (TxF)</a>.

<b>FltCreateFileEx2</b> sends the create request only to the instances attached below the specified minifilter driver instance and to the file system. The specified instance and the instances attached above it do not receive the create request. If no instance is specified, the request goes to the top of the stack and is received by all instances and the file system. 

There are two alternate ways to specify the name of the file to be created or opened with <b>FltCreateFileEx2</b>: 
<ul>
<li>
As a fully qualified pathname, supplied in the <b>ObjectName</b> member of the input <i>ObjectAttributes</i>. 

</li>
<li>
As a pathname that is relative to the directory file represented by the handle in the <b>RootDirectory</b> member of the input <i>ObjectAttributes</i>. 

</li>
</ul>Any <i>FileHandle</i> that is obtained from <b>FltCreateFileEx2</b> must eventually be released by calling <a href="..\fltkernel\nf-fltkernel-fltclose.md">FltClose</a>. In addition, any returned <i>FileObject</i> pointer must be dereferenced when it is no longer needed by calling <a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a>. 

Driver routines that do not run in the system process context must set the OBJ_KERNEL_HANDLE attribute for the <i>ObjectAttributes</i> parameter of <b>FltCreateFileEx2</b>. Setting this attribute restricts the use of the handle that is returned by <b>FltCreateFileEx2</b> to processes running in kernel mode. Otherwise, the handle can be accessed by the process in whose context the driver is running. 

Certain <i>DesiredAccess</i> flags and combinations of flags have the following effects: 
<ul>
<li>
For a caller to synchronize an I/O completion by waiting for the returned <i>FileHandle</i> to be set to the Signaled state, the SYNCHRONIZE flag must be set. 

</li>
<li>
If only the FILE_APPEND_DATA and SYNCHRONIZE flags are set, the caller can write only to the end of the file, and any offset information about write requests to the file is ignored. However, the file is automatically extended as necessary for this type of write operation. 

</li>
<li>
Setting the FILE_WRITE_DATA flag for a file also allows write requests beyond the end of the file to occur. The file is automatically extended for this type of write request, as well. 

</li>
<li>
If only the FILE_EXECUTE and SYNCHRONIZE flags are set, the caller cannot use the handle returned in the <i>FileHandle</i> parameter to directly read or write any data to or from the file. That is, all operations on the file must use system paging I/O to read or write file data. 

</li>
</ul>The <i>ShareAccess</i> parameter determines whether separate threads can access the same file, possibly simultaneously. If both file openers have the privilege to access a file in the specified manner, the file can be successfully opened and shared. If the original caller of <b>FltCreateFileEx2</b> does not specify FILE_SHARE_READ, FILE_SHARE_WRITE, or FILE_SHARE_DELETE, no other open operations can be performed on the file because the original caller is given exclusive access to the file. 

For a shared file to be successfully opened, the requested <i>DesiredAccess</i> to the file must be compatible with both the <i>DesiredAccess</i> and <i>ShareAccess</i> specifications of all preceding open requests that have not yet been released with <a href="..\fltkernel\nf-fltkernel-fltclose.md">FltClose</a>. That is, the <i>DesiredAccess</i> parameter that is specified to <b>FltCreateFileEx2</b> for a given file must not conflict with the accesses that other openers of the file have disallowed. 
<div class="alert"><b>Note</b>    If IO_IGNORE_SHARE_ACCESS_CHECK is specified in the <i>Flags</i> parameter, the I/O manager ignores the <i>ShareAccess</i> parameter. However, the file system might still perform access checks. Thus, it is important to specify the sharing mode you would like for the <i>ShareAccess</i>parameter, even when using the IO_IGNORE_SHARE_ACCESS_CHECK flag. </div><div> </div>The <i>CreateDisposition</i> value FILE_SUPERSEDE requires that the caller have DELETE access to an existing file object. If so, a successful call to <b>FltCreateFileEx2</b> with FILE_SUPERSEDE on an existing file effectively deletes that file and then recreates it. This implies that if the file has already been opened by another thread, it opened the file by specifying a <i>ShareAccess</i>parameter with the FILE_SHARE_DELETE flag set. Note that this type of disposition is consistent with the POSIX style of overwriting files. 

The <i>CreateDisposition</i> values FILE_OVERWRITE_IF and FILE_SUPERSEDE are similar. If <b>FltCreateFileEx2</b> is called with an existing file and either of these <i>CreateDisposition</i> values, the file is replaced. 

Overwriting a file is semantically equivalent to a supersede operation, except for the following: 
<ul>
<li>
The caller must have write access to the file, rather than delete access. This implies that, if the file has already been opened by another thread, it opened the file with the FILE_SHARE_WRITE flag set in the input <i>ShareAccess</i> parameter. 

</li>
<li>
The specified file attributes are combined with those attributes that are already applied to the file by using a bitwise OR operation. This implies that if the file has already been opened by another thread, a subsequent caller of <b>FltCreateFileEx2</b> cannot disable existing <i>FileAttributes</i> flags but can enable additional flags for the same file. Note that this style of overwriting files is consistent with MS-DOS, Windows 3.1, and OS/2.

</li>
</ul>The <i>CreateOptions</i> FILE_DIRECTORY_FILE value specifies that the file to be created or opened is a directory file. When a directory file is created, the file system creates an appropriate structure on the disk to represent an empty directory for that particular file system's on-disk structure. If this option was specified and the given file to be opened is not a directory file or if the caller specified an inconsistent <i>CreateOptions</i> or <i>CreateDisposition</i> value, the call to <b>FltCreateFileEx2</b> fails. 

The <i>CreateOptions</i> FILE_NO_INTERMEDIATE_BUFFERING flag prevents the file system from performing any intermediate buffering on behalf of the caller. Specifying this value places certain restrictions on the caller's parameters to other <b>Flt..File</b> routines or <b>Zw..File</b> routines, including the following: 
<ul>
<li>
Any byte offset value passed to the <i>ByteOffset</i> parameter of <a href="..\fltkernel\nf-fltkernel-fltreadfile.md">FltReadFile</a>, <a href="..\wdm\nf-wdm-zwreadfile.md">ZwReadFile</a>, <a href="..\fltkernel\nf-fltkernel-fltwritefile.md">FltWriteFile</a>, or <a href="..\wdm\nf-wdm-zwwritefile.md">ZwWriteFile</a> must be a multiple of the sector size. 

</li>
<li>
The <i>Length</i> parameter passed to <a href="..\fltkernel\nf-fltkernel-fltreadfile.md">FltReadFile</a>, <a href="..\wdm\nf-wdm-zwreadfile.md">ZwReadFile</a>, <a href="..\fltkernel\nf-fltkernel-fltwritefile.md">FltWriteFile</a>, or <a href="..\wdm\nf-wdm-zwwritefile.md">ZwWriteFile</a> must be a multiple of the sector size. Note that specifying a read operation to a buffer whose length is exactly the sector size might result in fewer significant bytes being transferred to that buffer if the end of the file was reached during the transfer.

</li>
<li>
Buffers must be aligned in accordance with the alignment requirement of the underlying storage device. This information can be obtained by calling <b>FltCreateFileEx2</b> to get a handle for the file object that represents the physical device and then calling <a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a> with that handle, specifying <b>FileAlignmentInformation</b> as the value for <i>FileInformationClass</i> parameter. For more information about the system FILE_<i>XXX</i>_ALIGNMENT values, which are defined in <i>Ntifs.h</i>, see <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff547807">Initializing a Device Object</a>. 

</li>
<li>
Calls to <a href="..\fltkernel\nf-fltkernel-fltsetinformationfile.md">FltSetInformationFile</a> or <a href="..\wdm\nf-wdm-zwsetinformationfile.md">ZwSetInformationFile</a> with the <i>FileInformationClass</i> parameter set to <b>FilePositionInformation</b> must specify an offset that is a multiple of the sector size.

</li>
</ul>The <i>CreateOptions</i> FILE_SYNCHRONOUS_IO_ALERT and FILE_SYNCHRONOUS_IO_NONALERT flags, which are mutually exclusive as their names suggest, specify that the file is being opened for synchronous I/O. This means that all I/O operations on the file are to be synchronous as long as they occur through the file object that the returned <i>FileHandle</i> refers to. All I/O on such a file is serialized across all threads by using the returned handle. With either of these <i>CreateOptions</i> flags set, the I/O Manager maintains the current file position offset in the file object's <b>CurrentByteOffset</b> field. This offset can be used in calls to <a href="..\wdm\nf-wdm-zwreadfile.md">ZwReadFile</a> and <a href="..\wdm\nf-wdm-zwwritefile.md">ZwWriteFile</a>. It can also be queried or set by calling <a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a> or <a href="..\wdm\nf-wdm-zwsetinformationfile.md">ZwSetInformationFile</a>. 

If the <i>CreateOptions</i> FILE_OPEN_REPARSE_POINT flag is <i>not</i> specified and <b>FltCreateFileEx2</b> attempts to open a file with a reparse point, normal reparse point processing occurs for the file.  If, on the other hand, the FILE_OPEN_REPARSE_POINT flag is specified, normal reparse processing does <i>not</i> occur and <b>FltCreateFileEx2</b> attempts to directly open the reparse point file.  In either case, if the open operation was successful, <b>FltCreateFileEx2</b> returns STATUS_SUCCESS; otherwise, the routine returns an NTSTATUS error code. <b>FltCreateFileEx2</b> never returns STATUS_REPARSE.

The <i>CreateOptions</i> FILE_OPEN_REQUIRING_OPLOCK flag eliminates the time between when you open the file and request an oplock that could potentially enable a third party to open the file and get a sharing violation. An application can use the FILE_OPEN_REQUIRING_OPLOCK flag on <b>FltCreateFileEx2</b> and then request any oplock. This ensures that an oplock owner will be notified of any later open request that causes a sharing violation. 

In Windows 7, if other handles exist on the file when an application uses the FILE_OPEN_REQUIRING_OPLOCK flag, the create operation will fail with STATUS_OPLOCK_NOT_GRANTED. This restriction no longer exists starting with Windows 8.

If this create operation would break an oplock that already exists on the file, then setting the FILE_OPEN_REQUIRING_OPLOCK flag will cause the create operation to fail with STATUS_CANNOT_BREAK_OPLOCK. The existing oplock will not be broken by this create operation.

 An application that uses this flag must request an oplock after this call succeeds, or all later attempts to open the file will be blocked without the benefit of typical oplock processing. Similarly, if this call succeeds but the later oplock request fails, an application that uses this flag must close its handle after it detects that the oplock request has failed.
<div class="alert"><b>Note</b>    The FILE_OPEN_REQUIRING_OPLOCK flag is available in Windows 7, Windows Server 2008 R2 and later Windows operating systems. The Microsoft file systems that implement this flag in Windows 7 are NTFS, FAT, and exFAT.</div><div> </div>The <i>CreateOptions</i> flag FILE_RESERVE_OPFILTER allows an application to request a level 1, batch, or filter oplock to prevent other applications from getting share violations. However, FILE_RESERVE_OPFILTER is only practically useful for filter oplocks. To use it, you must complete the following steps:
<ol>
<li>Issue a create request with <i>CreateOptions</i> of FILE_RESERVE_OPFILTER, <i>DesiredAccess</i> of exactly FILE_READ_ATTRIBUTES, and <i>ShareAccess</i> of exactly FILE_SHARE_READ | FILE_SHARE_WRITE | FILE_SHARE_DELETE. <ul>
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
</ol>Step three makes this practical only for filter oplocks. The handle opened in step 3 can have a DesiredAccess that contains a maximum of FILE_READ_ATTRIBUTES | FILE_WRITE_ATTRIBUTES | FILE_READ_DATA | FILE_READ_EA | FILE_EXECUTE | SYNCHRONIZE | READ_CONTROL and still not break a filter oplock. However, any DesiredAccess greater than FILE_READ_ATTRIBUTES | FILE_WRITE_ATTRIBUTES | SYNCHRONIZE will break a level 1 or batch oplock and make the FILE_RESERVE_OPFILTER flag useless for those oplock types.

The <i>Options</i> IO_NO_PARAMETER_CHECKING flag can be useful if a kernel-mode create request is issued in the context of an operation initiated by a user-mode application. Because the request occurs within a user-mode context, the I/O manager, by default, probes the supplied parameter values, which can cause an access violation if the parameters are kernel-mode addresses. This flag enables the caller to override this default behavior and avoid the access violation.

NTFS is the only Microsoft file system that implements FILE_RESERVE_OPFILTER. 

Minifilter drivers must use <a href="..\fltkernel\nf-fltkernel-fltsetinformationfile.md">FltSetInformationFile</a>, not <a href="..\wdm\nf-wdm-zwsetinformationfile.md">ZwSetInformationFile</a>, to rename a file. 
<div class="alert"><b>Note</b>    If you try to open a volume but only specify a combination of the following flags for the <i>DesiredAccess</i> parameter, <b>FltCreateFileEx2</b> will open a handle, independent of the file system, that has direct access to the storage device for the volume.<dl>
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
<p class="note">You must not use <b>FltCreateFileEx2</b> to open a handle with direct access to the storage device for the volume or you will leak system resources. If you want to open a handle with direct access to a storage device, call the <a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a>, <a href="..\ntddk\nf-ntddk-iocreatefilespecifydeviceobjecthint.md">IoCreateFileSpecifyDeviceObjectHint</a>, or <a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a> function instead.

</div><div> </div>When a caller of <b>FltCreateFileEx2</b> wishes to  enable reparsing for a volume target, a <a href="..\fltkernel\ns-fltkernel-_flt_createfile_target_ecp_context.md">FLT_CREATEFILE_TARGET_ECP_CONTEXT</a> can be included as an ECP to the ECP list in the <i>DriverContext</i> parameter.  If this ECP is present, <b>FltCreateFileEx2</b> will adjust the target device for the create operation and attempt for find a filtered instance  of a volume appropriate for the given file information. Use of this ECP is available starting with Windows 8.



## -see-also

<a href="..\wdm\ns-wdm-_file_full_ea_information.md">FILE_FULL_EA_INFORMATION</a>

<a href="..\fltkernel\nf-fltkernel-fltgetnextextracreateparameter.md">FltGetNextExtraCreateParameter</a>

<a href="..\fltkernel\nf-fltkernel-fltsetecplistintocallbackdata.md">FltSetEcpListIntoCallbackData</a>

<a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a>

<a href="..\fltkernel\nf-fltkernel-fltclose.md">FltClose</a>

<a href="..\fltkernel\nf-fltkernel-fltreadfile.md">FltReadFile</a>

<a href="..\wdm\nf-wdm-zwwritefile.md">ZwWriteFile</a>

<a href="..\fltkernel\nf-fltkernel-fltsetinformationfile.md">FltSetInformationFile</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>

<a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>

<a href="..\ntddk\nf-ntddk-ioinitializedrivercreatecontext.md">IoInitializeDriverCreateContext</a>

<a href="..\wdm\nf-wdm-zwsetinformationfile.md">ZwSetInformationFile</a>

<a href="..\ntddk\ns-ntddk-_io_driver_create_context.md">IO_DRIVER_CREATE_CONTEXT</a>

<a href="..\wdm\nf-wdm-zwreadfile.md">ZwReadFile</a>

<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>

<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameterlist.md">FltAllocateExtraCreateParameterList</a>

<a href="..\fltkernel\nf-fltkernel-fltwritefile.md">FltWriteFile</a>

<a href="..\wdm\nf-wdm-iocreatefile.md">IoCreateFile</a>

<a href="..\fltkernel\nf-fltkernel-fltfreeextracreateparameter.md">FltFreeExtraCreateParameter</a>

<a href="..\wdm\ns-wdm-_acl.md">ACL</a>

<a href="..\fltkernel\nf-fltkernel-fltinsertextracreateparameter.md">FltInsertExtraCreateParameter</a>

<a href="..\fltkernel\nf-fltkernel-fltqueryinformationfile.md">FltQueryInformationFile</a>

<a href="..\fltkernel\nf-fltkernel-fltacknowledgeecp.md">FltAcknowledgeEcp</a>

<a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a>

<a href="..\fltkernel\nf-fltkernel-fltisecpfromusermode.md">FltIsEcpFromUserMode</a>

<a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a>

<a href="..\fltkernel\nf-fltkernel-fltisecpacknowledged.md">FltIsEcpAcknowledged</a>

<a href="..\fltkernel\nf-fltkernel-fltfindextracreateparameter.md">FltFindExtraCreateParameter</a>

<a href="..\fltkernel\nf-fltkernel-fltgetecplistfromcallbackdata.md">FltGetEcpListFromCallbackData</a>

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>

<a href="..\ntddk\nf-ntddk-iocreatefilespecifydeviceobjecthint.md">IoCreateFileSpecifyDeviceObjectHint</a>

<a href="..\fltkernel\nf-fltkernel-fltfreeextracreateparameterlist.md">FltFreeExtraCreateParameterList</a>

<a href="..\fltkernel\nf-fltkernel-fltremoveextracreateparameter.md">FltRemoveExtraCreateParameter</a>

<a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a>

<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameter.md">FltAllocateExtraCreateParameter</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltCreateFileEx2 routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

