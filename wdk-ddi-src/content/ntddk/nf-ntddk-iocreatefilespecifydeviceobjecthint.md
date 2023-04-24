---
UID: NF:ntddk.IoCreateFileSpecifyDeviceObjectHint
title: IoCreateFileSpecifyDeviceObjectHint function (ntddk.h)
description: The IoCreateFileSpecifyDeviceObjectHint routine is used by file system filter drivers to send a create request only to the filters below a specified device object and to the file system.
tech.root: ifsk
ms.date: 12/06/2022
keywords: ["IoCreateFileSpecifyDeviceObjectHint function"]
ms.keywords: IoCreateFileSpecifyDeviceObjectHint, IoCreateFileSpecifyDeviceObjectHint routine [Installable File System Drivers], ifsk.iocreatefilespecifydeviceobjecthint, ioref_729440cd-ded3-40cf-a0c9-c10f523cd774.xml, ntddk/IoCreateFileSpecifyDeviceObjectHint
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h, FltKernel.h
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
 - IoCreateFileSpecifyDeviceObjectHint
 - ntddk/IoCreateFileSpecifyDeviceObjectHint
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoCreateFileSpecifyDeviceObjectHint
---

## -description

The **IoCreateFileSpecifyDeviceObjectHint** routine is used by file system filter drivers to send a create request only to the filters below a specified device object and to the file system.

## -parameters

### -param FileHandle [out]

A pointer to a variable that receives a handle for the file object if this call is successful.

### -param DesiredAccess [in]

A bitmask of flags that specify the type of access that the caller requires to the file or directory. The set of system-defined *DesiredAccess* flags determines the following specific access rights for file objects.

| DesiredAccess flags | Meaning |
|---|---|
| DELETE | The file can be deleted. |
| FILE_READ_DATA | Data can be read from the file. |
| FILE_READ_ATTRIBUTES | *FileAttributes* flags, described later, can be read. |
| FILE_READ_EA | Extended attributes (EA) associated with the file can be read. |
| READ_CONTROL | The access control list ([**ACL**](../wdm/ns-wdm-_acl.md)) and ownership information associated with the file can be read. |
| FILE_WRITE_DATA | Data can be written to the file. |
| FILE_WRITE_ATTRIBUTES | *FileAttributes* flags can be written. |
| FILE_WRITE_EA | Extended attributes associated with the file can be written. |
| FILE_APPEND_DATA | Data can be appended to the file. |
| WRITE_DAC | The discretionary access control list ([**DACL**](../wdm/ns-wdm-_acl.md)) associated with the file can be written. |
| WRITE_OWNER | Ownership information associated with the file can be written. |
| SYNCHRONIZE | The caller can synchronize the completion of an I/O operation by waiting for the returned *FileHandle* to be set to the Signaled state. This flag must be set if the *CreateOptions* FILE_SYNCHRONOUS_IO_ALERT or FILE_SYNCHRONOUS_IO_NONALERT flag is set. |
| FILE_EXECUTE | Data can be read into memory from the file using system paging I/O. |

Callers of **IoCreateFileSpecifyDeviceObjectHint** can specify one or a combination of the following, possibly ORed with additional compatible flags from the preceding list of*DesiredAccess* flags, for any file object that does not represent a directory file:

| DesiredAccess to file values | Maps to DesiredAccess flags |
|---|---|
| GENERIC_READ | STANDARD_RIGHTS_READ, FILE_READ_DATA, FILE_READ_ATTRIBUTES, FILE_READ_EA, and SYNCHRONIZE. |
| GENERIC_WRITE | STANDARD_RIGHTS_WRITE, FILE_WRITE_DATA, FILE_WRITE_ATTRIBUTES, FILE_WRITE_EA, FILE_APPEND_DATA, and SYNCHRONIZE. |
| GENERIC_EXECUTE | STANDARD_RIGHTS_EXECUTE, SYNCHRONIZE, FILE_READ_ATTRIBUTES, and FILE_EXECUTE. |

The STANDARD_RIGHTS_*XXX* are predefined system values used to enforce security on system objects.

If the FILE_DIRECTORY_FILE *CreateOptions* flag is set, callers of **IoCreateFileSpecifyDeviceObjectHint** can specify one or a combination of the following, possibly ORed with one or more compatible flags from the preceding list of*DesiredAccess* flags.

| DesiredAccess to directory values | Meaning |
|---|---|
| FILE_LIST_DIRECTORY | Files in the directory can be listed. |
| FILE_TRAVERSE | The directory can be traversed: that is, it can be part of the pathname of a file. |

The FILE_READ_DATA, FILE_WRITE_DATA, FILE_EXECUTE, and FILE_APPEND_DATA *DesiredAccess* flags are incompatible with creating or opening a directory file.

### -param ObjectAttributes [in]

A pointer to an [**OBJECT_ATTRIBUTES**](/windows/win32/api/ntdef/ns-ntdef-_object_attributes) structure already initialized by the [InitializeObjectAttributes](/windows/win32/api/ntdef/nf-ntdef-initializeobjectattributes) routine. If the caller is running in the system process context, this parameter (*ObjectAttributes*) can be **NULL**. Otherwise, the caller must set the OBJ_KERNEL_HANDLE attribute in the call to the **InitializeObjectAttributes** routine. Members of the OBJECT_ATTRIBUTES structure for a file object include the following.

| Member | Value |
|---|---|
| **ULONGLength** | Specifies the number of bytes of *ObjectAttributes* data supplied. This value must be at least **sizeof**(OBJECT_ATTRIBUTES). |
| **PUNICODE_STRING ObjectName** | A pointer to a buffered Unicode string naming the file to be created or opened. This value must be a fully qualified file specification, unless it is the name of a file relative to the directory specified by **RootDirectory**. For example, \Device\Floppy1\myfile.dat or \\??\B:\myfile.dat could be the fully qualified file specification, provided that the floppy driver and overlying file system are already loaded. (Note that \\?? replaces \DosDevices as the name of the Win32 object namespace. \DosDevices will still work, but \\?? is translated faster by the object manager.) |
| **HANDLERootDirectory** | Optionally specifies a handle to a directory that was obtained by a preceding call to **IoCreateFileSpecifyDeviceObjectHint**. If this value is **NULL**, the **ObjectName** member must be a fully qualified file specification that includes the full path to the target file. If this value is non-**NULL**, the **ObjectName** member specifies a file name relative to this directory. |
| **PSECURITY_DESCRIPTOR SecurityDescriptor** | Optionally specifies a security descriptor to be applied to a file. ACLs specified by such a security descriptor are only applied to the file when it is created. If the value is **NULL** when a file is created, the ACL placed on the file is file-system-dependent; most file systems propagate some part of such an ACL from the parent directory file combined with the caller's default ACL. |
| **ULONGAttributes** | A set of flags that controls the file object attributes. If the caller is running in the system process context, this parameter can be zero. Otherwise, the caller must set the OBJ_KERNEL_HANDLE flag. The caller can also optionally set the OBJ_CASE_INSENSITIVE flag, which indicates that name-lookup code should ignore the case of **ObjectName** rather than performing an exact-match search. |

### -param IoStatusBlock [out]

A pointer to an [**IO_STATUS_BLOCK**](../wdm/ns-wdm-_io_status_block.md) structure that receives the final completion status and information about the requested operation. On return from **IoCreateFileSpecifyDeviceObjectHint**, the **Information** member contains one of the following values:

- FILE_CREATED

- FILE_OPENED

- FILE_OVERWRITTEN

- FILE_SUPERSEDED

- FILE_EXISTS

- FILE_DOES_NOT_EXIST

### -param AllocationSize [in, optional]

Optionally specifies the initial allocation size, in bytes, for the file. A nonzero value has no effect unless the file is being created, overwritten, or superseded.

### -param FileAttributes [in]

Explicitly specified attributes are applied only when the file is created, superseded, or, in some cases, overwritten. By default, this value is FILE_ATTRIBUTE_NORMAL, which can be overridden by any other flag or by an ORed combination of compatible flags. Possible *FileAttributes* flags include the following.

| FileAttributes flags | Meaning |
|---|---|
| FILE_ATTRIBUTE_NORMAL | A file with standard attributes should be created. |
| FILE_ATTRIBUTE_READONLY | A read-only file should be created. |
| FILE_ATTRIBUTE_HIDDEN | A hidden file should be created. |
| FILE_ATTRIBUTE_SYSTEM | A system file should be created. |
| FILE_ATTRIBUTE_ARCHIVE | The file should be marked so that it will be archived. |
| FILE_ATTRIBUTE_TEMPORARY | A temporary file should be created. |

### -param ShareAccess [in]

Specifies the type of share access to the file that the caller would like, as zero, or one, or a combination of the following flags. To request exclusive access, set this parameter to zero. If the IO_IGNORE_SHARE_ACCESS_CHECK flag is specified in the *Options* parameter, the I/O manager ignores this parameter. However, the file system might still perform access checks. Thus, it is important to specify the sharing mode you would like for this parameter, even when using the IO_IGNORE_SHARE_ACCESS_CHECK flag. For the greatest chance of avoiding sharing violation errors, specify all of the following share access flags.

| ShareAccess flags | Meaning |
|---|---|
| FILE_SHARE_READ | The file can be opened for read access by other threads. |
| FILE_SHARE_WRITE | The file can be opened for write access by other threads. |
| FILE_SHARE_DELETE | The file can be opened for delete access by other threads. |

### -param Disposition [in]

Specifies a value that determines the action to be taken, depending on whether the file already exists. The value can be any of those described following.

| Disposition values | Meaning |
|---|---|
| FILE_SUPERSEDE | If the file already exists, replace it with the given file. If it does not, create the given file. |
| FILE_CREATE | If the file already exists, fail the request and do not create or open the given file. If it does not, create the given file. |
| FILE_OPEN | If the file already exists, open it instead of creating a new file. If it does not, fail the request and do not create a new file. |
| FILE_OPEN_IF | If the file already exists, open it. If it does not, create the given file. |
| FILE_OVERWRITE | If the file already exists, open it and overwrite it. If it does not, fail the request. |
| FILE_OVERWRITE_IF | If the file already exists, open it and overwrite it. If it does not, create the given file. |

### -param CreateOptions [in]

Specifies the options to be applied when creating or opening the file. These options are specified as a compatible combination of the following flags.

| CreateOptions flags | Meaning |
|---|---|
| FILE_DIRECTORY_FILE | The file being created or opened is a directory file. If this flag is set, the *Disposition* parameter must be set to one of FILE_CREATE, FILE_OPEN, or FILE_OPEN_IF. This flag is compatible with the following *CreateOptions* flags: FILE_SYNCHRONOUS_IO_ALERT, FILE_SYNCHRONOUS_IO_NONALERT, FILE_WRITE_THROUGH, FILE_OPEN_FOR_BACKUP_INTENT, and FILE_OPEN_BY_FILE_ID. |
| FILE_NON_DIRECTORY_FILE | The file being opened must not be a directory file or this call will fail. The file object being opened must represent a data file. |
| FILE_WRITE_THROUGH | System services, FSDs, and drivers that write data to the file must actually transfer the data into the file before any requested write operation is considered complete. |
| FILE_SEQUENTIAL_ONLY | All accesses to the file will be sequential. |
| FILE_RANDOM_ACCESS | Accesses to the file can be random, so no sequential read-ahead operations should be performed on the file by FSDs or the system. |
| FILE_NO_INTERMEDIATE_BUFFERING | The file cannot be cached or buffered in a driver's internal buffers. This flag is incompatible with the *DesiredAccess* FILE_APPEND_DATA flag. |
| FILE_SYNCHRONOUS_IO_ALERT | All operations on the file are performed synchronously. Any wait on behalf of the caller is subject to premature termination from alerts. This flag also causes the I/O system to maintain the file position context. If this flag is set, the *DesiredAccess* SYNCHRONIZE flag also must be set. |
| FILE_SYNCHRONOUS_IO_NONALERT | All operations on the file are performed synchronously. Waits that exist in the system to synchronize I/O queuing and completion are not subject to alerts. This flag also causes the I/O system to maintain the file position context. If this flag is set, the *DesiredAccess* SYNCHRONIZE flag also must be set. |
| FILE_CREATE_TREE_CONNECTION | Create a tree connection for this file in order to open it over the network. |
| FILE_COMPLETE_IF_OPLOCKED | Complete this operation immediately with an alternate success code if the target file is oplocked, rather than blocking the caller's thread. If the file is oplocked, another caller already has access to the file over the network. |
| FILE_NO_EA_KNOWLEDGE | If the extended attributes on an existing file being opened indicate that the caller must understand EAs to properly interpret the file, fail this request because the caller does not understand how to deal with EAs. |
| FILE_OPEN_REPARSE_POINT | Open a file with a reparse point and bypass normal reparse point processing for the file.  For more information, see the **Remarks** section below. |
| FILE_DELETE_ON_CLOSE | Delete the file when the last handle to it is passed to [ZwClose](../ntifs/nf-ntifs-ntclose.md). |
| FILE_OPEN_BY_FILE_ID | The file name specified in the *ObjectAttributes* parameter includes the 8-byte file reference number for the file. This number is assigned by the file system and is file-system-specific. If the file is a reparse point, the file name also includes the name of a device. Note: The FAT file system does not support FILE_OPEN_BY_FILE_ID. |
| FILE_OPEN_FOR_BACKUP_INTENT | The file is being opened for backup intent, hence, the system should check for certain access rights and grant the caller the appropriate accesses to the file before checking the input *DesiredAccess* against the file's security descriptor. |
| FILE_OPEN_REQUIRING_OPLOCK | The file is being opened and an opportunistic lock (oplock) on the file is being requested as a single atomic operation. The file system checks for oplocks before it performs the create operation, and the create operation fails with a return code of STATUS_CANNOT_BREAK_OPLOCK if the create would break an existing oplock. |
| FILE_RESERVE_OPFILTER | This flag allows an application to request a filter opportunistic lock (oplock) to prevent other applications from getting share violations.  If there are already open handles, the create request fails with STATUS_OPLOCK_NOT_GRANTED.  For more information, see the following Remarks section. |

### -param EaBuffer [in, optional]

A pointer to a caller-supplied [**FILE_FULL_EA_INFORMATION**](../wdm/ns-wdm-_file_full_ea_information.md)-structured buffer containing extended attribute (EA) information to be applied to the file.

### -param EaLength [in]

The length, in bytes, of *EaBuffer*.

### -param CreateFileType [in]

Drivers must set this parameter to CreateFileTypeNone.

### -param InternalParameters [in, optional]

Drivers must set this parameter to **NULL**.

### -param Options [in]

Specifies options to be used during the creation of the create request. The following table lists the available options.

| Options flags | Meaning |
|---|---|
| IO_FORCE_ACCESS_CHECK | Indicates that the I/O manager must check the create request against the file's security descriptor. |
| IO_IGNORE_SHARE_ACCESS_CHECK | Indicates that the I/O manager should not perform share-access checks on the file object after it is created. However, the file system might still perform these checks. |

### -param DeviceObject [in, optional]

A pointer to the device object to which the create request is to be sent. The device object must be a filter or file system device object in the file system driver stack for the volume on which the file or directory resides. This parameter is optional and can be **NULL**. If this parameter is **NULL**, the request will be sent to the device object at the top of the driver stack.

## -returns

**IoCreateFileSpecifyDeviceObjectHint** returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following:

| Return code | Description |
|---|---|
| **STATUS_INVALID_DEVICE_OBJECT_PARAMETER** | The specified *DeviceObject* is not attached to the file system driver stack for the volume specified in the file or directory name. This error can also occur if the name contains a reparse point other than a mount point. |
| **STATUS_MOUNT_POINT_NOT_RESOLVED** | The file or directory name contains a mount point that resolves to a volume other than the one to which the specified *DeviceObject* is attached. |
| **STATUS_OBJECT_PATH_SYNTAX_BAD** |  |

**IoCreateFileSpecifyDeviceObjectHint** might return STATUS_FILE_LOCK_CONFLICT as the return value or in the **Status** member of the IO_STATUS_BLOCK structure that is pointed to by the IoStatusBlock parameter. This would occur only if the NTFS log file is full, and an error occurs while **IoCreateFileSpecifyDeviceObjectHint** tries to handle this situation.

## -remarks

This routine is used by file system filter drivers to send a create request only to the filters below a specified device object and to the file system. Filters that are attached above the specified device object in the driver stack do not receive the create request.  

The Windows Vista [IoCreateFileEx](./nf-ntddk-iocreatefileex.md) routine is similar to the **IoCreateFileSpecifyDeviceObjectHint** routine but provides greater functionality than the **IoCreateFileSpecifyDeviceObjectHint** routine, including access to extra create parameters (ECPs) and transaction information.

If you use the [IoCreateFileEx](./nf-ntddk-iocreatefileex.md) routine instead of the **IoCreateFileSpecifyDeviceObjectHint** routine, note that the *DriverContext* parameter of the **IoCreateFileSpecifyDeviceObjectHint** routine has been moved to the **DeviceObjectHint** member of the [**IO_DRIVER_CREATE_CONTEXT**](./ns-ntddk-_io_driver_create_context.md) structure.  The IO_DRIVER_CREATE_CONTEXT structure is passed into the **IoCreateFileEx** routine through its *DriverContext* parameter.

File system filter drivers call **IoCreateFileSpecifyDeviceObjectHint** to send a create request only to a specified device object, the filters attached below it, and the file system. Filters attached above the specified device object in the driver stack do not receive the create request. The same is **true** for any cleanup or close requests on the file object that is created by **IoCreateFileSpecifyDeviceObjectHint**.

There are two alternate ways to specify the name of the file to be created or opened using **IoCreateFileSpecifyDeviceObjectHint**:

1. As a fully qualified pathname, supplied in the **ObjectName** member of the input *ObjectAttributes*

1. As a pathname relative to the directory file that is represented by the handle in the **RootDirectory** member of the input *ObjectAttributes*

Any handle that is obtained from **IoCreateFileSpecifyDeviceObjectHint** must eventually be released by calling [ZwClose](../ntifs/nf-ntifs-ntclose.md).

Driver routines that run in a process context other than that of the system process must set the OBJ_KERNEL_HANDLE attribute for the *ObjectAttributes* parameter of **IoCreateFileSpecifyDeviceObjectHint**. This restricts the use of the handle that is returned by **IoCreateFileSpecifyDeviceObjectHint** to processes running in kernel mode. Otherwise, the handle can be accessed by the process in whose context the driver is running.

Certain *DesiredAccess* flags and combinations of flags have the following effects:

- For a caller to synchronize an I/O completion by waiting for the returned *FileHandle* to be set to the Signaled state, the SYNCHRONIZE flag must be set.

- If only the FILE_APPEND_DATA and SYNCHRONIZE flags are set, the caller can write only to the end of the file, and any offset information about writes to the file is ignored. However, the file will automatically be extended as necessary for this type of write operation.

- Setting the FILE_WRITE_DATA flag for a file also allows writes beyond the end of the file to occur. The file is automatically extended for this type of write, as well.

- If only the FILE_EXECUTE and SYNCHRONIZE flags are set, the caller cannot directly read or write any data in the file using the returned *FileHandle*; that is, all operations on the file occur through the system pager in response to instruction and data accesses.

The *ShareAccess* parameter determines whether separate threads can access the same file, possibly simultaneously. Provided that both file openers have the privilege to access a file in the specified manner, the file can be successfully opened and shared. If the original caller of **IoCreateFileSpecifyDeviceObjectHint** does not specify FILE_SHARE_READ, FILE_SHARE_WRITE, or FILE_SHARE_DELETE, no other open operations can be performed on the file: that is, the original caller is given exclusive access to the file.

In order for a shared file to be successfully opened, the requested *DesiredAccess* to the file must be compatible with both the *DesiredAccess* and *ShareAccess* specifications of all preceding opens that have not yet been released with [ZwClose](../ntifs/nf-ntifs-ntclose.md). That is, the *DesiredAccess* specified to **IoCreateFileSpecifyDeviceObjectHint** for a given file must not conflict with the accesses that other openers of the file have disallowed.

If IO_IGNORE_SHARE_ACCESS_CHECK is specified in the *Options* parameter, the I/O manager ignores the *ShareAccess* parameter. However, the file system might still perform access checks. Thus, it is important to specify the sharing mode you would like for the *ShareAccess* parameter, even when using the IO_IGNORE_SHARE_ACCESS_CHECK flag.

The *Disposition* value FILE_SUPERSEDE requires that the caller have DELETE access to a existing file object. If so, a successful call to **IoCreateFileSpecifyDeviceObjectHint** with FILE_SUPERSEDE on an existing file effectively deletes that file, and then recreates it. This implies that if the file has already been opened by another thread, it opened the file by specifying a *ShareAccess* parameter with the FILE_SHARE_DELETE flag set. Note that this type of disposition is consistent with the POSIX style of overwriting files.

The *Disposition* values FILE_OVERWRITE_IF and FILE_SUPERSEDE are similar. If **IoCreateFileSpecifyDeviceObjectHint** is called with an existing file and either of these *Disposition* values, the file will be replaced.

Overwriting a file is semantically equivalent to a supersede operation, except for the following:

- The caller must have write access to the file, rather than delete access. This implies that if the file has already been opened by another thread, it opened the file with the FILE_SHARE_WRITE flag set in the input *ShareAccess*.

- The specified file attributes are logically ORed with those already on the file. This implies that if the file has already been opened by another thread, a subsequent caller of **IoCreateFileSpecifyDeviceObjectHint** cannot disable existing *FileAttributes* flags but can enable additional flags for the same file.

The *CreateOptions* FILE_DIRECTORY_FILE value specifies that the file to be created or opened is a directory file. When a directory file is created, the file system creates an appropriate structure on the disk to represent an empty directory for that particular file system's on-disk structure. If this option was specified and the given file to be opened is not a directory file, or if the caller specified an inconsistent *CreateOptions* or **Disposition** value, the call to **IoCreateFileSpecifyDeviceObjectHint** will fail.

The *CreateOptions* FILE_NO_INTERMEDIATE_BUFFERING flag prevents the file system from performing any intermediate buffering on behalf of the caller. Specifying this value places certain restrictions on the caller's parameters to other **Zw..File** routines, including the following:

- Any byte *Offset* value that is passed to [ZwReadFile](../ntifs/nf-ntifs-ntreadfile.md) or [ZwWriteFile](../ntifs/nf-ntifs-ntwritefile.md) must be a multiple of the sector size of the underlying device.

- The *Length* that is passed to [ZwReadFile](../ntifs/nf-ntifs-ntreadfile.md) or [ZwWriteFile](../ntifs/nf-ntifs-ntwritefile.md) must be a multiple of the sector size. Note that specifying a read operation to a buffer whose length is exactly the sector size might result in a lesser number of significant bytes being transferred to that buffer if the end of the file was reached during the transfer.

- Buffers must be aligned in accordance with the alignment requirement of the underlying device. This information can be obtained by calling **IoCreateFileSpecifyDeviceObjectHint** to get a handle for the file object that represents the physical device and then calling [ZwQueryInformationFile](../ntifs/nf-ntifs-ntqueryinformationfile.md) with that handle. For a list of the system FILE_*XXX*_ALIGNMENT values, see [**DEVICE_OBJECT**](../wdm/ns-wdm-_device_object.md).

- Calls to [ZwSetInformationFile](../ntifs/nf-ntifs-ntsetinformationfile.md) with the *FileInformationClass* parameter set to **FilePositionInformation** must specify an offset that is a multiple of the sector size.

The mutually exclusive *CreateOptions*, FILE_SYNCHRONOUS_IO_ALERT and FILE_SYNCHRONOUS_IO_NONALERT, specify that all I/O operations on the file are to be synchronous as long as they occur through the file object referred to by the returned *FileHandle*. All I/O on such a file is serialized across all threads using the returned handle. With either of these *CreateOptions*, the *DesiredAccess* SYNCHRONIZE flag must be set so that the I/O Manager will use the file object as a synchronization object. With either of these *CreateOptions* set, the I/O Manager maintains the "file position context" for the file object, an internal, current file position offset. This offset can be used in calls to [ZwReadFile](../ntifs/nf-ntifs-ntreadfile.md) and [ZwWriteFile](../ntifs/nf-ntifs-ntwritefile.md). Its position also can be queried by calling [ZwQueryInformationFile](../ntifs/nf-ntifs-ntqueryinformationfile.md), or set by calling [ZwSetInformationFile](../ntifs/nf-ntifs-ntsetinformationfile.md).  

If the *CreateOptions* FILE_OPEN_REPARSE_POINT flag is not specified and **IoCreateFileSpecifyDeviceObjectHint** attempts to open a file with a reparse point, normal reparse point processing occurs for the file.  If, on the other hand, the FILE_OPEN_REPARSE_POINT flag is specified, normal reparse processing does not occur and **IoCreateFileSpecifyDeviceObjectHint** attempts to directly open the reparse point file.  In either case, if the open operation was successful, **IoCreateFileSpecifyDeviceObjectHint** returns STATUS_SUCCESS; otherwise, the routine returns an NTSTATUS error code. **IoCreateFileSpecifyDeviceObjectHint** never returns STATUS_REPARSE.

The *CreateOptions* FILE_OPEN_REQUIRING_OPLOCK flag eliminates the time between when you open the file and request an oplock that could potentially enable a third party to open the file and get a sharing violation. An application can use the FILE_OPEN_REQUIRING_OPLOCK flag on **IoCreateFileSpecifyDeviceObjectHint** and then request any oplock. This ensures that an oplock owner will be notified of any later open request that causes a sharing violation.

In Windows 7, if other handles exist on the file when an application uses the FILE_OPEN_REQUIRING_OPLOCK flag, the create operation will fail with STATUS_OPLOCK_NOT_GRANTED. This restriction no longer exists starting with Windows 8.

If this create operation would break an oplock that already exists on the file, then setting the FILE_OPEN_REQUIRING_OPLOCK flag will cause the create operation to fail with STATUS_CANNOT_BREAK_OPLOCK. The existing oplock will not be broken by this create operation.

 An application that uses this flag must request an oplock after this call succeeds, or all later attempts to open the file will be blocked without the benefit of typical oplock processing. Similarly, if this call succeeds but the later oplock request fails, an application that uses this flag must close its handle after it detects that the oplock request has failed.

The FILE_OPEN_REQUIRING_OPLOCK flag is available in Windows 7, Windows Server 2008 R2 and later Windows operating systems. The Microsoft file systems that implement this flag in Windows 7 are NTFS, FAT, and exFAT.

The *CreateOptions* flag FILE_RESERVE_OPFILTER allows an application to request a level 1, batch, or filter oplock to prevent other applications from getting share violations. However, FILE_RESERVE_OPFILTER is only practically useful for filter oplocks. To use it, you must complete the following steps:

1. Issue a create request with *CreateOptions* of FILE_RESERVE_OPFILTER, *DesiredAccess* of exactly FILE_READ_ATTRIBUTES, and *ShareAccess* of exactly FILE_SHARE_READ | FILE_SHARE_WRITE | FILE_SHARE_DELETE.

    - If there are already open handles, the create request will fail with STATUS_OPLOCK_NOT_GRANTED, and the next requested oplock also fails.

    - If you open with more access or less sharing will also cause a failure of STATUS_OPLOCK_NOT_GRANTED.

1. If the create request succeeds, request an oplock.

1. Open another handle to the file to do I/O.  

Step three makes this practical only for filter oplocks. The handle opened in step 3 can have a *DesiredAccess* that contains a maximum of FILE_READ_ATTRIBUTES | FILE_WRITE_ATTRIBUTES | FILE_READ_DATA | FILE_READ_EA | FILE_EXECUTE | SYNCHRONIZE | READ_CONTROL and still not break a filter oplock. However, any *DesiredAccess* greater than FILE_READ_ATTRIBUTES | FILE_WRITE_ATTRIBUTES | SYNCHRONIZE will break a level 1 or batch oplock and make the FILE_RESERVE_OPFILTER flag useless for those oplock types.

NTFS is the only Microsoft file system that implements FILE_RESERVE_OPFILTER.

**IoCreateFileSpecifyDeviceObjectHint** cannot be used to obtain a handle to a volume.

If the file name path that is passed to **IoCreateFileSpecifyDeviceObjectHint** contains a reparse point, the reparse point must resolve to the same volume where the file or directory resides.  If it does not, either the error STATUS_INVALID_DEVICE_OBJECT_PARAMETER or STATUS_MOUNT_POINT_NOT_RESOLVED is returned.

## -see-also

[ACCESS_MASK](/windows-hardware/drivers/kernel/access-mask)

[**ACL**](../wdm/ns-wdm-_acl.md)

[**FILE_FULL_EA_INFORMATION**](../wdm/ns-wdm-_file_full_ea_information.md)

[**IO_DRIVER_CREATE_CONTEXT**](./ns-ntddk-_io_driver_create_context.md)

[InitializeObjectAttributes](/windows/win32/api/ntdef/nf-ntdef-initializeobjectattributes)

[IoCheckEaBufferValidity](../ntifs/nf-ntifs-iocheckeabuffervalidity.md)

[IoCreateFile](../wdm/nf-wdm-iocreatefile.md)

[IoCreateFileEx](./nf-ntddk-iocreatefileex.md)

[**UNICODE_STRING**](/windows/win32/api/ntdef/ns-ntdef-_unicode_string)

[ZwClose](../ntifs/nf-ntifs-ntclose.md)

[ZwCreateFile](../ntifs/nf-ntifs-ntcreatefile.md)

[ZwQueryInformationFile](../ntifs/nf-ntifs-ntqueryinformationfile.md)

[ZwReadFile](../ntifs/nf-ntifs-ntreadfile.md)

[ZwSetInformationFile](../ntifs/nf-ntifs-ntsetinformationfile.md)

[ZwWriteFile](../ntifs/nf-ntifs-ntwritefile.md)