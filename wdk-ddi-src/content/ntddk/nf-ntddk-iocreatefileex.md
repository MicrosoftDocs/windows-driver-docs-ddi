---
UID: NF:ntddk.IoCreateFileEx
title: IoCreateFileEx function
author: windows-driver-content
description: The IoCreateFileEx routine either causes a new file or directory to be created, or opens an existing file, device, directory, or volume and gives the caller a handle for the file object.
old-location: ifsk\iocreatefileex.htm
old-project: ifsk
ms.assetid: 47d5e7e2-bc97-4413-b1ca-ef958288902c
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ifsk.iocreatefileex, ntddk/IoCreateFileEx, IoCreateFileEx routine [Installable File System Drivers], IoCreateFileEx, ioref_7e2e6fcc-6ec5-4329-a855-c9f4a06b5434.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available starting with Windows Vista.
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
-	IoCreateFileEx
product: Windows
targetos: Windows
req.typenames: *PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT
---

# IoCreateFileEx function


## -description


The <b>IoCreateFileEx</b> routine either causes a new file or directory to be created, or opens an existing file, device, directory, or volume and gives the caller a handle for the file object.  File system filter drivers (legacy filter drivers) call this routine.


## -syntax


````
NTSTATUS IoCreateFileEx(
  _Out_    PHANDLE                   FileHandle,
  _In_     ACCESS_MASK               DesiredAccess,
  _In_     POBJECT_ATTRIBUTES        ObjectAttributes,
  _Out_    PIO_STATUS_BLOCK          IoStatusBlock,
  _In_opt_ PLARGE_INTEGER            AllocationSize,
  _In_     ULONG                     FileAttributes,
  _In_     ULONG                     ShareAccess,
  _In_     ULONG                     Disposition,
  _In_     ULONG                     CreateOptions,
  _In_opt_ PVOID                     EaBuffer,
  _In_     ULONG                     EaLength,
  _In_     CREATE_FILE_TYPE          CreateFileType,
  _In_opt_ PVOID                     InternalParameters,
  _In_     ULONG                     Options,
  _In_opt_ PIO_DRIVER_CREATE_CONTEXT DriverContext
);
````


## -parameters




### -param FileHandle [out]

A pointer to a variable that receives the file handle if the call is successful. The driver must close the handle with <a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a> as soon as the handle is no longer being used.


### -param DesiredAccess [in]

A bitmask of flags (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>) that specifies the type of access that the caller requires to the file or directory. This set of system-defined <i>DesiredAccess</i> flags determines the following specific access rights for file objects.
<table>
<tr>
<th><i>DesiredAccess</i> flag</th>
<th>Access rights</th>
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

Callers of <b>IoCreateFileEx</b> can specify one or a combination of the following, possibly combined through a bitwise OR operation with additional compatible flags from the previous <i>DesiredAccess</i> flags list, for any file object that does not represent a directory file.
<table>
<tr>
<th>Desired access to file values</th>
<th>Maps to <i>DesiredAccess</i> flags</th>
</tr>
<tr>
<td>
GENERIC_READ

</td>
<td>
STANDARD_RIGHTS_READ, FILE_READ_DATA, FILE_READ_ATTRIBUTES, FILE_READ_EA, SYNCHRONIZE. 

</td>
</tr>
<tr>
<td>
GENERIC_WRITE

</td>
<td>
STANDARD_RIGHTS_WRITE, FILE_WRITE_DATA, FILE_WRITE_ATTRIBUTES, FILE_WRITE_EA, FILE_APPEND_DATA, SYNCHRONIZE. 

</td>
</tr>
<tr>
<td>
GENERIC_EXECUTE

</td>
<td>
STANDARD_RIGHTS_EXECUTE, SYNCHRONIZE, FILE_READ_ATTRIBUTES, FILE_EXECUTE. 

</td>
</tr>
</table> 

The STANDARD_RIGHTS_<i>XXX</i> are predefined system values that are used to enforce security on system objects.

If the FILE_DIRECTORY_FILE <i>CreateOptions</i> flag is set, callers of <b>IoCreateFileEx</b>can specify one or a combination of the following, possibly combined through a bitwise OR operation with one or more compatible flags from the previous <i>DesiredAccess</i> flags list.
<table>
<tr>
<th>Desired access to directory values</th>
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
The directory can be traversed, that is, it can be part of the pathname of a file.

</td>
</tr>
</table> 

The FILE_READ_DATA, FILE_WRITE_DATA, FILE_EXECUTE, and FILE_APPEND_DATA <i>DesiredAccess</i> flags are incompatible with creating or opening a directory file.


### -param ObjectAttributes [in]


      A pointer to an <a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a> structure already initialized by the <a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a> routine. If the caller is running in the system process context, this parameter can be <b>NULL</b>. Otherwise, the caller must set the OBJ_KERNEL_HANDLE attribute in the call to <b>InitializeObjectAttributes</b>. Members of this structure for a file object include the following.
      
<table>
<tr>
<th>Member</th>
<th>Value</th>
</tr>
<tr>
<td>
<b>ULONG</b> <b>Length</b>

</td>
<td>
The number of bytes of the supplied <i>ObjectAttributes</i> data. This value must be at least <code>sizeof(OBJECT_ATTRIBUTES)</code>.

</td>
</tr>
<tr>
<td>
<b>PUNICODE_STRING</b> <b>ObjectName</b>

</td>
<td>
A pointer to a buffered Unicode string that contains the name of the file to be created or opened. This value must be a fully qualified file specification, unless it is the name of a file relative to the directory specified by <b>RootDirectory</b>. For example, <i>\Device\Floppy1\myfile.dat</i> or <i>\??\B:\myfile.dat</i> could be the fully qualified file specification, as long as the floppy disk drive driver and overlying file system are already loaded.

</td>
</tr>
<tr>
<td>
<b>HANDLE</b> <b>RootDirectory</b>

</td>
<td>
Optional handle to a directory that was obtained by a previous call to <b>IoCreateFileEx</b>. If this value is <b>NULL</b>, the <b>ObjectName</b> member must be a fully qualified file specification that includes the full path to the target file. If this value is non-<b>NULL</b>, the <b>ObjectName</b> member specifies a file name relative to this directory.

</td>
</tr>
<tr>
<td>
<b>PSECURITY_DESCRIPTOR</b> <b>SecurityDescriptor</b>

</td>
<td>
Optional security descriptor to be applied to a file. ACLs specified by such a security descriptor are only applied to the file when it is created. If the value is <b>NULL</b> when a file is created, the ACL placed on the file is file-system-dependent; most file systems propagate some part of such an ACL from the parent directory file combined with the caller's default ACL.

</td>
</tr>
<tr>
<td>
<b>ULONG</b> <b>Attributes</b>

</td>
<td>
A set of flags that controls the file object attributes. If the caller is running in the system process context, this parameter can be zero. Otherwise, the caller must set the <b>OBJ_KERNEL_HANDLE</b> flag. The caller can also optionally set the <b>OBJ_CASE_INSENSITIVE</b> flag, which indicates that name-lookup code should ignore the case of <b>ObjectName</b> instead of performing an exact-match search.

</td>
</tr>
</table> 


### -param IoStatusBlock [out]

A pointer to a variable of type <a href="..\wdm\ns-wdm-_io_status_block.md">IO_STATUS_BLOCK</a> that receives the final completion status and information about the requested operation. On return from <b>IoCreateFileEx</b>, the <b>Information</b> member of the variable contains one of the following values:
<ul>
<li>FILE_CREATED</li>
<li>FILE_OPENED</li>
<li>FILE_OVERWRITTEN</li>
<li>FILE_SUPERSEDED</li>
<li>FILE_EXISTS</li>
<li>FILE_DOES_NOT_EXIST</li>
</ul>

### -param AllocationSize [in, optional]

Optionally specifies the initial allocation size, in bytes, for the file. A nonzero value has no effect unless the file is being created, overwritten, or superseded.


### -param FileAttributes [in]

Explicitly specified attributes are applied only when the file is created, superseded, or, in some cases, overwritten. By default, this value is FILE_ATTRIBUTE_NORMAL, which can be overridden by any other flag or by a combination (through a bitwise OR operation) of compatible flags. Possible <i>FileAttributes</i> flags include the following.
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
A file that has standard attributes should be created.

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


### -param ShareAccess [in]

Specifies the type of share access to the file that the caller would like, as zero, or one, or a combination of the following flags. To request exclusive access, set this parameter to zero. If the IO_IGNORE_SHARE_ACCESS_CHECK flag is specified in the <i>Options</i> parameter, the I/O manager ignores the <i>ShareAccess</i> parameter. However, the file system might still perform access checks. Thus, it is important to specify the sharing mode you would like for this parameter, even when you use the IO_IGNORE_SHARE_ACCESS_CHECK flag. To help you avoid sharing violation errors, specify all the following share access flags.
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
The file can be opened for read access by other threads' calls to <b>IoCreateFileEx</b>.

</td>
</tr>
<tr>
<td>
FILE_SHARE_WRITE

</td>
<td>
The file can be opened for write access by other threads' calls to <b>IoCreateFileEx</b>.

</td>
</tr>
<tr>
<td>
FILE_SHARE_DELETE

</td>
<td>
The file can be opened for delete access by other threads' calls to <b>IoCreateFileEx</b>.

</td>
</tr>
</table> 

Device drivers and intermediate drivers usually set <i>ShareAccess</i> to zero, which gives the caller exclusive access to the open file.


### -param Disposition [in]

One of the following values can be used to specify how the file should be handled when the file already exists.
<table>
<tr>
<th><i>Disposition</i> values</th>
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
The file being created or opened is a directory file. With this flag, the <i>Disposition</i> parameter must be set to one of FILE_CREATE, FILE_OPEN, or FILE_OPEN_IF. <i>CreateOptions</i> flags that are compatible with this flag are as follows: FILE_SYNCHRONOUS_IO_ALERT, FILE_SYNCHRONOUS_IO_NONALERT, FILE_WRITE_THROUGH, FILE_OPEN_FOR_BACKUP_INTENT, and FILE_OPEN_BY_FILE_ID. 

</td>
</tr>
<tr>
<td>
FILE_NON_DIRECTORY_FILE

</td>
<td>
The file being opened must not be a directory file or this call will fail. The file object being opened can represent a data file, a logical, virtual, a physical device, or a volume. 

</td>
</tr>
<tr>
<td>
FILE_WRITE_THROUGH

</td>
<td>
System services, file system drivers (FSDs), and drivers that write data to the file must actually transfer the data into the file before any requested write operation is considered complete. 

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
The file cannot be cached or buffered in a driver's internal buffers. This flag is incompatible with the <i>DesiredAccess</i>FILE_APPEND_DATA flag.

</td>
</tr>
<tr>
<td>
FILE_SYNCHRONOUS_IO_ALERT

</td>
<td>
All operations on the file are performed synchronously. Any wait on behalf of the caller is subject to premature termination from alerts. This flag also causes the I/O system to maintain the file position context. If this flag is set, the <i>DesiredAccess</i> SYNCHRONIZE flag must also be set. 

</td>
</tr>
<tr>
<td>
FILE_SYNCHRONOUS_IO_NONALERT

</td>
<td>
All operations on the file are performed synchronously. Wait requests in the system to synchronize I/O queuing and completion are not subject to alerts. This flag also causes the I/O system to maintain the file position context. If this flag is set, the <i>DesiredAccess</i> SYNCHRONIZE flag must also be set.

</td>
</tr>
<tr>
<td>
FILE_CREATE_TREE_CONNECTION

</td>
<td>
Create a tree connection for this file to open it over the network.

</td>
</tr>
<tr>
<td>
FILE_COMPLETE_IF_OPLOCKED

</td>
<td>
Complete this operation immediately with an alternate success code if the target file is oplocked, instead of blocking the caller's thread. If the file is oplocked, another caller already has access to the file over the network. 

</td>
</tr>
<tr>
<td>
FILE_NO_EA_KNOWLEDGE

</td>
<td>
If the extended attributes (EAs) on an existing file being opened indicate that the caller must process EAs to interpret the file, fail this request because the caller cannot correctly process EAs.

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
The file name that is specified in the <i>ObjectAttributes</i> parameter includes the 8-byte file reference number for the file.  This number is assigned by the file system and is file-system-specific.  If the file is a reparse point, the file name also includes the name of a device.  Note: The FAT file system does not support FILE_OPEN_BY_FILE_ID.  

</td>
</tr>
<tr>
<td>
FILE_OPEN_FOR_BACKUP_INTENT

</td>
<td>
The file is being opened for backup. Therefore, the system should check for certain access rights and grant the caller the appropriate accesses to the file before checking the input <i>DesiredAccess</i> against the file's security descriptor.

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


### -param EaBuffer [in, optional]

A pointer to a caller-supplied variable of type <a href="..\wdm\ns-wdm-_file_full_ea_information.md">FILE_FULL_EA_INFORMATION</a> that contains extended attribute (EA) information to be applied to the file.  For device and intermediate drivers, this parameter must be <b>NULL</b>.


### -param EaLength [in]

Length, in bytes, of <i>EaBuffer</i>.  For device drivers and intermediate drivers, this parameter must be zero.


### -param CreateFileType [in]

Drivers must set this parameter to CreateFileTypeNone.


### -param InternalParameters [in, optional]

Drivers must set this parameter to <b>NULL</b>.


### -param Options [in]

Specifies options to be used during the generation of the create request. Zero or more of the following bit flag values can be used.
<table>
<tr>
<th><i>Options</i> flags</th>
<th>Meaning</th>
</tr>
<tr>
<td>
IO_NO_PARAMETER_CHECKING

</td>
<td>
The parameters for this call should not be validated before attempting to issue the create request. Driver writers should use this flag with caution as certain invalid parameters can cause a system failure. For more information, see Remarks.

</td>
</tr>
<tr>
<td>
IO_FORCE_ACCESS_CHECK

</td>
<td>
The I/O manager must check the create request against the file's security descriptor.

</td>
</tr>
<tr>
<td>
IO_IGNORE_SHARE_ACCESS_CHECK

</td>
<td>
The I/O manager should not perform share-access checks on the file object after it is created. However, the file system might still perform these checks.

</td>
</tr>
<tr>
<td>
IO_STOP_ON_SYMLINK

</td>
<td>
The I/O manager or the file system will return STATUS_STOPPED_ON_SYMLINK if a symbolic link is encountered while  opening or creating the file.

</td>
</tr>
<tr>
<td>
IO_OPEN_TARGET_DIRECTORY

</td>
<td>
Open the file's parent directory.

</td>
</tr>
</table> 


### -param DriverContext [in, optional]

An optional pointer to an <a href="..\ntddk\ns-ntddk-_io_driver_create_context.md">IO_DRIVER_CREATE_CONTEXT</a> structure that was previously initialized by the <a href="..\ntddk\nf-ntddk-ioinitializedrivercreatecontext.md">IoInitializeDriverCreateContext</a> routine.  The IO_DRIVER_CREATE_CONTEXT structure can be used to pass additional parameters to the <b>IoCreateFileEx</b> and <a href="..\fltkernel\nf-fltkernel-fltcreatefileex2.md">FltCreateFileEx2</a> routines.  See the following Remarks section for more information.


## -returns


<b>IoCreateFileEx</b> either returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following:
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

<a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a> returns this status value if the <i>DriverContext</i> parameter is not <b>NULL</b> and if the specified device object is not attached to the file system driver stack for the volume specified in the file or directory name.  This device object is specified by the <b>DeviceObjectHint</b> member of the IO_DRIVER_CREATE_CONTEXT structure.  For more information, see <a href="..\ntddk\ns-ntddk-_io_driver_create_context.md">IO_DRIVER_CREATE_CONTEXT</a>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_MOUNT_POINT_NOT_RESOLVED</b></dt>
</dl>
</td>
<td width="60%">

<a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a> returns this status value if the <i>DriverContext</i> parameter is not <b>NULL</b> and if the file or directory name contains a mount point that resolves to a volume other than the one to which the specified device object is attached.  This device object is specified by the <b>DeviceObjectHint</b> member of the IO_DRIVER_CREATE_CONTEXT structure.  For more information, see <a href="..\ntddk\ns-ntddk-_io_driver_create_context.md">IO_DRIVER_CREATE_CONTEXT</a>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_PATH_SYNTAX_BAD</b></dt>
</dl>
</td>
<td width="60%">

<a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a> returns this status value if the <i>ObjectAttributes</i> parameter did not contain a <b>RootDirectory</b> member, but the <b>ObjectName</b> member in the OBJECT_ATTRIBUTES structure was an empty string or did not contain an OBJECT_NAME_PATH_SEPARATOR character. This indicates incorrect syntax for the object path.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_STOPPED_ON_SYMLINK </b></dt>
</dl>
</td>
<td width="60%">

<a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a> returns this status value if the <i>Options</i> parameter flag <b>IO_STOP_ON_SYMLINK</b> is set and a symbolic link is encountered while opening or creating the file.

</td>
</tr>
</table> 

If the <b>IoCreateFileEx</b> routine returns an error status, the caller can find additional information about the cause of the failure by checking the <i>IoStatusBlock</i> parameter.



<div class="alert"><b>Note</b>  <b>IoCreateFileEx</b> might return STATUS_FILE_LOCK_CONFLICT as the return value or in the <b>Status</b> member of the IO_STATUS_BLOCK structure that is pointed to by the IoStatusBlock parameter. This would occur only if the NTFS log file is full, and an error occurs while <b>IoCreateFileEx</b> tries to handle this situation.</div><div> </div>


## -remarks


The <b>IoCreateFileEx</b> routine is similar to both the <a href="..\wdm\nf-wdm-iocreatefile.md">IoCreateFile</a> routine and the <a href="..\ntddk\nf-ntddk-iocreatefilespecifydeviceobjecthint.md">IoCreateFileSpecifyDeviceObjectHint</a> routine but offers additional functionality including access to extra create parameters (ECPs), device objects hints, and transaction information through the <b>IoCreateFileEx</b> routine's <i>DriverContext</i> parameter.  For more information about these structure based parameters, see <a href="..\ntddk\ns-ntddk-_io_driver_create_context.md">IO_DRIVER_CREATE_CONTEXT</a>.

File system filter drivers call <b>IoCreateFileEx</b> to send a create request only to a specified device object, the filters attached below it, and the file system. Filters attached above the specified device object in the driver stack do not receive the create request.  However, if the <b>DeviceObjectHint</b> member of the IO_DRIVER_CREATE_CONTEXT structure (passed through the <i>DriverContext</i> parameter) is <b>NULL</b>, the request goes to the top of the stack and is received by all filters and the file system.

The handle, obtained by <b>IoCreateFileEx</b>, can be used by subsequent calls to manipulate data within the file or the state or attributes of the file object.  Any handle that is obtained from <b>IoCreateFileEx</b> must eventually be released by calling <a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a>.

There are two alternate ways to specify the name of the file to be created or opened with <b>IoCreateFileEx</b>:
<ul>
<li>
As a fully qualified pathname, supplied in the <b>ObjectName</b> member of the input <i>ObjectAttributes</i> parameter.

</li>
<li>
As a pathname relative to the handle in the <b>RootDirectory</b> member of the input <i>ObjectAttributes</i> parameter. (This handle can represent a directory file.)

</li>
</ul>Driver routines that run in a process context other than that of the system process must set the OBJ_KERNEL_HANDLE attribute for the <i>ObjectAttributes</i> parameter of <b>IoCreateFileEx</b>. This restricts the use of the handle that is returned by <b>IoCreateFileEx</b> to processes running in kernel mode. Otherwise, the handle can be accessed by the process in whose context the driver is running.  Drivers can call <a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a> to set the OBJ_KERNEL_HANDLE attribute.

Certain <i>DesiredAccess</i> flags and combinations of flags have the following effects:
<ul>
<li>
  For a caller to synchronize an I/O completion by waiting for the returned <i>FileHandle</i> to be set to the Signaled state, the SYNCHRONIZE flag must be set. Otherwise, a caller that is a device or intermediate driver must synchronize an I/O completion by using an event object.

</li>
<li>
  If only the FILE_APPEND_DATA and SYNCHRONIZE flags are set, the caller can write only to the end of the file, and any offset information about writes to the file is ignored. However, the file will automatically be extended as necessary for this kind of write operation.

</li>
<li>
  Setting the FILE_WRITE_DATA flag for a file also allows writes beyond the end of the file to occur. The file is automatically extended for this kind of write, as well.

</li>
<li>
  If only the FILE_EXECUTE and SYNCHRONIZE flags are set, the caller cannot directly read or write any data in the file using the returned <i>FileHandle</i>: that is, all operations on the file occur through the system pager in response to instruction and data accesses. Device and intermediate drivers should not set the FILE_EXECUTE flag in <i>DesiredAccess</i>.

</li>
</ul>The <i>ShareAccess</i> parameter determines whether separate threads can access the same file, possibly simultaneously. Provided that both file openers have the privilege to access a file in the specified manner, the file can be successfully opened and shared. If the original caller of <b>IoCreateFileEx</b> does not specify FILE_SHARE_READ, FILE_SHARE_WRITE, or FILE_SHARE_DELETE, no other open operations can be performed on the file: that is, the original caller is given exclusive access to the file.

For a shared file to be successfully opened, the requested <i>DesiredAccess</i> value for the file must be compatible with both the <i>DesiredAccess</i> and <i>ShareAccess</i> specifications of all previous open requests that have not yet been released with <a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a>. That is, the <i>DesiredAccess</i> value that is specified to <b>IoCreateFileEx</b> for a given file must not conflict with the accesses that other openers of the file have disallowed.
<div class="alert"><b>Note</b>    If  IO_IGNORE_SHARE_ACCESS_CHECK is specified in the <i>Options</i> parameter, the I/O manager ignores the <i>ShareAccess</i> parameter. However, the file system might still perform access checks. Thus, it is important to specify the sharing mode you would like for the <i>ShareAccess</i> parameter, even when using the IO_IGNORE_SHARE_ACCESS_CHECK flag.</div><div> </div>The <i>Disposition</i> value FILE_SUPERSEDE requires that the caller have DELETE access to an existing file object. If so, a successful call to <b>IoCreateFileEx</b> with FILE_SUPERSEDE on an existing file effectively deletes that file, and then recreates it. This implies that, if the file has already been opened by another thread, the thread opened the file by specifying a <i>ShareAccess</i>parameter with the FILE_SHARE_DELETE flag set. Notice that this type of disposition is consistent with the POSIX style of overwriting files.

The <i>Disposition</i> values FILE_OVERWRITE_IF and FILE_SUPERSEDE are similar. If <b>IoCreateFileEx</b> is called with an existing file and either of these <i>Disposition</i> values, the file will be replaced.

Overwriting a file is semantically equivalent to a supersede operation, except for the following:
<ul>
<li>
 The caller must have write access to the file, instead of delete access. This implies that, if the file has already been opened by another thread, it opened the file with the FILE_SHARE_WRITE flag set in the input <i>ShareAccess</i>.

</li>
<li>
 The specified file attributes are logically ORed with those already on the file. This implies that if the file has already been opened by another thread, a subsequent caller of <b>IoCreateFileEx</b> cannot disable existing <i>FileAttributes</i> flags but can enable additional flags for the same file. Notice that this style of overwriting files is consistent with MS-DOS, Windows 3.1, and with OS/2.

</li>
</ul>The <i>CreateOptions</i> FILE_DIRECTORY_FILE value specifies that the file to be created or opened is a directory file. When a directory file is created, the file system creates an appropriate structure on the disk to represent an empty directory for that particular file system's on-disk structure. If this option was specified and the given file to be opened is not a directory file, or if the caller specified an inconsistent <i>CreateOptions</i> or <i>Disposition</i> value, the call to <b>IoCreateFileEx</b> will fail.

The <i>CreateOptions</i> FILE_NO_INTERMEDIATE_BUFFERING flag prevents the file system from performing any intermediate buffering on behalf of the caller. Specifying this value places certain restrictions on the caller's parameters to the <b>Zw..File</b> routines, including the following:
<ul>
<li>
  Any optional <i>ByteOffset</i> passed to <a href="..\wdm\nf-wdm-zwreadfile.md">ZwReadFile</a> or <a href="..\wdm\nf-wdm-zwwritefile.md">ZwWriteFile</a> must be an integral (integer multiple) of the sector size.

</li>
<li>
  The <i>Length</i> passed to <a href="..\wdm\nf-wdm-zwreadfile.md">ZwReadFile</a> or <a href="..\wdm\nf-wdm-zwwritefile.md">ZwWriteFile</a>, must be an integral of the sector size. Notice that specifying a read operation to a buffer whose length is exactly the sector size might result in a lesser number of significant bytes being transferred to that buffer if the end of the file was reached during the transfer.

</li>
<li>
  Buffers must be aligned in accordance with the alignment requirement of the underlying device. This information can be obtained by calling <b>IoCreateFileEx</b> to get a handle for the file object that represents the physical device, and, then, calling <a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a> with that handle. For a list of the system FILE_<i>XXX</i>_ALIGNMENT values, see <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>.

</li>
<li>
  Calls to <a href="..\wdm\nf-wdm-zwsetinformationfile.md">ZwSetInformationFile</a> with the <i>FileInformationClass</i> parameter set to <b>FilePositionInformation</b> must specify an offset that is an integral of the sector size.

</li>
</ul>The mutually exclusive <i>CreateOptions</i>, FILE_SYNCHRONOUS_IO_ALERT and FILE_SYNCHRONOUS_IO_NONALERT flags, specify that all I/O operations on the file are to be synchronous as long as they occur through the file object referred to by the returned <i>FileHandle</i>. All I/O on such a file is serialized across all threads by using the returned handle. With either of these <i>CreateOptions</i> values, the <i>DesiredAccess</i> SYNCHRONIZE flag must be set so that the I/O Manager will use the file object as a synchronization object. With either of these <i>CreateOptions</i> values set, the I/O Manager maintains the "file position context" for the file object, an internal, current file position offset. This offset can be used in calls to <a href="..\wdm\nf-wdm-zwreadfile.md">ZwReadFile</a> and <a href="..\wdm\nf-wdm-zwwritefile.md">ZwWriteFile</a>. Its position can also be queried by calling <a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a>, or set by calling <a href="..\wdm\nf-wdm-zwsetinformationfile.md">ZwSetInformationFile</a>.

If the <i>CreateOptions</i> FILE_OPEN_REPARSE_POINT flag is <i>not</i> specified and <b>IoCreateFileEx</b> attempts to open a file with a reparse point, normal reparse point processing occurs for the file.  If, on the other hand, the FILE_OPEN_REPARSE_POINT flag is specified, normal reparse processing does <i>not</i> occur and <b>IoCreateFileEx</b> attempts to directly open the reparse point file.  In either case, if the open operation was successful, <b>IoCreateFileEx</b> returns STATUS_SUCCESS; otherwise, the routine returns an NTSTATUS error code. <b>IoCreateFileEx</b> never returns STATUS_REPARSE.

The <i>CreateOptions</i> FILE_OPEN_REQUIRING_OPLOCK flag eliminates the time between when you open the file and request an oplock that could potentially enable a third party to open the file and get a sharing violation. An application can use the FILE_OPEN_REQUIRING_OPLOCK flag on <b>IoCreateFileEx</b> and then request any oplock. This ensures that an oplock owner will be notified of any later open request that causes a sharing violation.  

In Windows 7, if other handles exist on the file when an application uses the FILE_OPEN_REQUIRING_OPLOCK flag, the create operation will fail with STATUS_OPLOCK_NOT_GRANTED. This restriction no longer exists starting with Windows 8.

If this create operation would break an oplock that already exists on the file, then setting the FILE_OPEN_REQUIRING_OPLOCK flag will cause the create operation to fail with STATUS_CANNOT_BREAK_OPLOCK. The existing oplock will not be broken by this create operation.

 An application that uses this flag must request an oplock after this call succeeds, or all later attempts to open the file will be blocked without the benefit of typical oplock processing. Similarly, if this call succeeds but the later oplock request fails, an application that uses this flag must close its handle after it detects that the oplock request has failed.
<div class="alert"><b>Note</b>    The FILE_OPEN_REQUIRING_OPLOCK flag is available in Windows 7, Windows Server 2008 R2and later Windows operating systems. The Microsoft file systems that implement this flag are NTFS, FAT, and exFAT.</div><div> </div>The <i>CreateOptions</i> flag, FILE_RESERVE_OPFILTER, allows an application to request a level 1, batch, or filter oplock to prevent other applications from getting share violations. However, FILE_RESERVE_OPFILTER is only practically useful for filter oplocks. To use it, you must follow these steps:
<ol>
<li>Issue a create request with <i>CreateOptions</i> of FILE_RESERVE_OPFILTER, DesiredAccess of exactly FILE_READ_ATTRIBUTES, and ShareAccess of exactly FILE_SHARE_READ | FILE_SHARE_WRITE | FILE_SHARE_DELETE. <ul>
<li> If there are already open handles, the create request fails with STATUS_OPLOCK_NOT_GRANTED, and the next requested oplock also fails.  </li>
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

<b>IoCreateFileEx</b> can be used to obtain a handle to a volume. 

If the I/O request does not go to the top of the driver stack, that is if the <i>DriverContext</i> parameter is not <b>NULL</b> and a valid device object is specified by the <b>DeviceObjectHint</b> member of the IO_DRIVER_CREATE_CONTEXT structure, the following restriction applies:
<ul>
<li>
 If the file name path that is passed to the <b>IoCreateFileEx</b> routine contains a mount point, the mount point must resolve to the same volume where the file or directory resides.

</li>
</ul>


## -see-also

<a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>

<a href="..\ntddk\nf-ntddk-iocreatefilespecifydeviceobjecthint.md">IoCreateFileSpecifyDeviceObjectHint</a>

<a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a>

<a href="..\wdm\nf-wdm-zwsetinformationfile.md">ZwSetInformationFile</a>

<a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a>

<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameterfromlookasidelist.md">FltAllocateExtraCreateParameterFromLookasideList</a>

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>

<a href="..\ntddk\ns-ntddk-_io_driver_create_context.md">IO_DRIVER_CREATE_CONTEXT</a>

<a href="..\wdm\ns-wdm-_file_full_ea_information.md">FILE_FULL_EA_INFORMATION</a>

<a href="..\wdm\nf-wdm-zwwritefile.md">ZwWriteFile</a>

<a href="..\fltkernel\nf-fltkernel-fltcreatefileex2.md">FltCreateFileEx2</a>

<a href="..\wdm\nf-wdm-zwreadfile.md">ZwReadFile</a>

<a href="..\wdm\nf-wdm-iocreatefile.md">IoCreateFile</a>

<a href="..\ntifs\nc-ntifs-pfsrtl_extra_create_parameter_cleanup_callback.md">PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK</a>

<a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>

<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameterlist.md">FltAllocateExtraCreateParameterList</a>

<a href="..\ntifs\nf-ntifs-iocheckeabuffervalidity.md">IoCheckEaBufferValidity</a>

<a href="..\wdm\ns-wdm-_acl.md">ACL</a>

<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameter.md">FltAllocateExtraCreateParameter</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IoCreateFileEx routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

