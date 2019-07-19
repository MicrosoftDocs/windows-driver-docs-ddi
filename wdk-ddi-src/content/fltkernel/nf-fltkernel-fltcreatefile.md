---
UID: NF:fltkernel.FltCreateFile
title: FltCreateFile function (fltkernel.h)
description: Minifilter drivers call FltCreateFile to create a new file or open an existing file.
old-location: ifsk\fltcreatefile.htm
tech.root: ifsk
ms.assetid: fd7e1f27-e492-4402-ae9e-4ce52c3420d0
ms.date: 07/16/2019
ms.keywords: FltApiRef_a_to_d_2059a625-6d9e-4083-9c2e-d92e76c7539a.xml, FltCreateFile, FltCreateFile function [Installable File System Drivers], fltkernel/FltCreateFile, ifsk.fltcreatefile
ms.topic: function
f1_keywords:
 - "fltkernel/FltCreateFile"
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Fltmgr.lib
- Fltmgr.dll
api_name:
- FltCreateFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltCreateFile function

## -description

Minifilter drivers call **FltCreateFile** to create a new file or open an existing file.

## -parameters

### -param Filter [in]

An opaque filter pointer for the caller.

### -param Instance [in, optional]

An opaque instance pointer for the minifilter driver instance that the create request is to be sent to. The instance must be attached to the volume where the file or directory resides. This parameter is optional and can be **NULL**. If this parameter is **NULL**, the request is sent to the device object at the top of the file system driver stack for the volume. If it is non-**NULL**, the request is sent only to minifilter driver instances that are attached below the specified instance.

### -param FileHandle [out]

A pointer to a caller-allocated variable that receives the file handle if the call to **FltCreateFile** is successful.

### -param DesiredAccess [in]

A bitmask of flags specifying the type of access that the caller requires to the file or directory. The set of system-defined *DesiredAccess* flags determines the following specific access rights for file objects.

Do not specify FILE_READ_DATA, FILE_WRITE_DATA, FILE_EXECUTE, or FILE_APPEND_DATA when creating or opening a directory.

| DesiredAccess Flags   | Meaning |
| -------------------   | ------- |
| DELETE                | The file can be deleted. |
| FILE_READ_DATA        | Data can be read from the file. |
| FILE_READ_ATTRIBUTES  | *FileAttributes* flags, described later, can be read. |
| FILE_READ_EA          | Extended attributes associated with the file can be read. |
| READ_CONTROL          | The access control list ([ACL](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_acl)) and ownership information associated with the file can be read. |
| FILE_WRITE_DATA       | Data can be written to the file. |
| FILE_WRITE_ATTRIBUTES | *FileAttributes* flags can be written. |
| FILE_WRITE_EA         | Extended attributes associated with the file can be written. |
| FILE_APPEND_DATA      | Data can be appended to the file. |
| WRITE_DAC             | The discretionary access control list ([DACL](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_acl)) associated with the file can be written. |
| WRITE_OWNER           | Ownership information associated with the file can be written. |
| SYNCHRONIZE           | The caller can synchronize the completion of an I/O operation by waiting for the returned *FileHandle* to be set to the Signaled state. This flag must be set if the *CreateOptions* FILE_SYNCHRONOUS_IO_ALERT or FILE_SYNCHRONOUS_IO_NONALERT flag is set. |
| FILE_EXECUTE          | Use system paging I/O to read data from the file into system memory. |

Alternatively, for any file object that does not represent a directory, you can specify one or more of the following generic [ACCESS_MASK](https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask) flags. (The STANDARD_RIGHTS_*XXX* flags are predefined system values that are used to enforce security on system objects.) You can also combine these generic flags with additional flags from the preceding table.

| DesiredAccess to File Values | Maps to DesiredAccess Flags |
| ---------------------------- | --------------------------- |
| GENERIC_READ                 | STANDARD_RIGHTS_READ, FILE_READ_DATA, FILE_READ_ATTRIBUTES, FILE_READ_EA, and SYNCHRONIZE. |
| GENERIC_WRITE                | STANDARD_RIGHTS_WRITE, FILE_WRITE_DATA, FILE_WRITE_ATTRIBUTES, FILE_WRITE_EA, FILE_APPEND_DATA, and SYNCHRONIZE. |
| GENERIC_EXECUTE              | STANDARD_RIGHTS_EXECUTE, SYNCHRONIZE, FILE_READ_ATTRIBUTES, and FILE_EXECUTE. |

For directories, you can specify one or more of the following ACCESS_MASK flags, which you can also combine with any compatible flags that were described earlier.

| DesiredAccess to Directory Values | Meaning |
| --------------------------------- | ------- |
| FILE_LIST_DIRECTORY               | Files in the directory can be listed. |
| FILE_TRAVERSE                     | The directory can be traversed: that is, it can be part of the pathname of a file. |

### -param ObjectAttributes [in]

A pointer to a structure already initialized with [**InitializeObjectAttributes**](https://docs.microsoft.com/windows/desktop/api/ntdef/nf-ntdef-initializeobjectattributes). If the caller is running in the system process context, this parameter can be **NULL**. Otherwise, the caller must set the OBJ_KERNEL_HANDLE attribute in the call to **InitializeObjectAttributes**. Members of this structure for a file object include the following.

| Member | Value |
| ------ | ----- |
| **ULONGLength** | Specifies the number of bytes of *ObjectAttributes* data supplied. This value must be at least **sizeof(**OBJECT_ATTRIBUTES**)**. |
| **PUNICODE_STRING ObjectName** | Pointer to a [UNICODE_STRING](https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string) structure containing the name of the file to be created or opened. This name must be a fully qualified file specification or the name of a device object unless it is the name of a file relative to the directory specified by **RootDirectory**. For example, \Device\Floppy1\myfile.dat or \??\B:\myfile.dat could be the fully qualified file specification, if the floppy driver and overlying file system are already loaded. (Note: \?? replaces \DosDevices as the name of the Win32 object namespace. \DosDevices still works, but \?? is translated faster by the object manager.) |
| **HANDLERootDirectory** | Optionally specifies a handle to a directory obtained by a preceding call to **FltCreateFile**. If this value is **NULL**, the **ObjectName **member must be a fully qualified file specification that includes the full path to the target file. If this value is non-**NULL**, the **ObjectName** member specifies a file name relative to this directory. |
| **PSECURITY_DESCRIPTOR SecurityDescriptor** | Optionally specifies a security descriptor ([SECURITY_DESCRIPTOR](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_security_descriptor)) to be applied to a file. [ACLs](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_acl) specified by such a security descriptor are only applied to the file when it is created. If the value is **NULL** when a file is created, the ACL placed on the file is file-system-dependent; most file systems propagate some part of such an ACL from the parent directory file combined with the caller's default ACL. |
| **ULONGAttributes** | Is a set of flags that controls the file object attributes. If the caller is running in the system process context, this parameter can be zero. Otherwise, the caller must set the OBJ_KERNEL_HANDLE flag. The caller can also optionally set the OBJ_CASE_INSENSITIVE flag, which indicates that name-lookup code should ignore the case of **ObjectName** rather than performing an exact-match search. |

### -param IoStatusBlock [out]

A pointer to an [IO_STATUS_BLOCK](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_io_status_block) structure that receives the final completion status and information about the requested operation. On return from **FltCreateFile**, the **Information** member contains one of the following values.

* FILE_CREATED
* FILE_OPENED
* FILE_OVERWRITTEN
* FILE_SUPERSEDED
* FILE_EXISTS
* FILE_DOES_NOT_EXIST

### -param AllocationSize [in, optional]

Optionally specifies the initial allocation size, in bytes, for the file stream. A nonzero value has no effect unless the file is being created, overwritten, or superseded.

### -param FileAttributes [in]

Specifies one or more of the following FILE_ATTRIBUTE_*XXX* flags, which represent the file attributes to set if you are creating, superseding, or overwriting a file. Normally, you specify FILE_ATTRIBUTE_NORMAL, which sets the default attributes.

| FileAttributes Flags | Meaning |
| -------------------- | ------- |
| FILE_ATTRIBUTE_NORMAL    | A file with standard attributes should be created. |
| FILE_ATTRIBUTE_READONLY  | A read-only file should be created. |
| FILE_ATTRIBUTE_HIDDEN    | A hidden file should be created. |
| FILE_ATTRIBUTE_SYSTEM    | A system file should be created. |
| FILE_ATTRIBUTE_ARCHIVE   | An archive file should be created. This attribute is used to mark files for backup or removal. |
| FILE_ATTRIBUTE_TEMPORARY | A temporary file should be created. |

### -param ShareAccess [in]

Specifies the type of share access to the file that the caller requires, as zero or one, or a combination of the following flags. To request exclusive access, set this parameter to zero. If the IO_IGNORE_SHARE_ACCESS_CHECK flag is specified in the *Flags* parameter, the I/O manager ignores this parameter. However, the file system might still perform access checks. Thus, it is important to specify the sharing mode you would like for this parameter, even when using the IO_IGNORE_SHARE_ACCESS_CHECK flag. For the greatest chance of avoiding sharing violation errors, specify all of the following share access flags.

| ShareAccess Flags | Meaning |
| ----------------- | ------- |
| FILE_SHARE_READ   | The file can be opened for read access by other threads. |
| FILE_SHARE_WRITE  | The file can be opened for write access by other threads. |
| FILE_SHARE_DELETE | The file can be opened for delete access by other threads. |

### -param CreateDisposition [in]

Specifies a value that determines the action to be taken, depending on whether the file already exists. The value can be any of those described following.

| CreateDisposition Values | Meaning |
| ------------------------ | ------- |
| FILE_SUPERSEDE           | If the file already exists, replace it with the given file. If it does not, create the given file. |
| FILE_CREATE              | If the file already exists, fail the request and do not create or open the given file. If it does not, create the given file. |
| FILE_OPEN                | If the file already exists, open it instead of creating a new file. If it does not, fail the request and do not create a new file. |
| FILE_OPEN_IF             | If the file already exists, open it. If it does not, create the given file. |
| FILE_OVERWRITE           | If the file already exists, open it and overwrite it. If it does not, fail the request. |
| FILE_OVERWRITE_IF        | If the file already exists, open it and overwrite it. If it does not, create the given file. |

### -param CreateOptions [in]

Specifies the options to be applied when creating or opening the file, as a compatible combination of the following flags.

| CreateOptions Flags | Meaning |
| ------------------- | ------- |
| FILE_DIRECTORY_FILE (0x00000001)  | The file being created or opened is a directory file. With this flag, the *CreateDisposition* parameter must be set to one of FILE_CREATE, FILE_OPEN, or FILE_OPEN_IF. With this flag, other compatible *CreateOptions* flags include only the following: FILE_SYNCHRONOUS_IO_ALERT, FILE_SYNCHRONOUS_IO_NONALERT, FILE_WRITE_THROUGH, FILE_OPEN_FOR_BACKUP_INTENT, and FILE_OPEN_BY_FILE_ID. |
| FILE_WRITE_THROUGH (0x00000002) | System services, file systems, and drivers that write data to the file must actually transfer the data into the file before any requested write operation is considered complete. |
| FILE_SEQUENTIAL_ONLY (0x00000004) | All accesses to the file will be sequential. |
| FILE_NO_INTERMEDIATE_BUFFERING (0x00000008) | The file cannot be cached or buffered in a driver's internal buffers. This flag is incompatible with the *DesiredAccess *FILE_APPEND_DATA flag. |
| FILE_SYNCHRONOUS_IO_ALERT (0x00000010) | All operations on the file are performed synchronously. Any wait on behalf of the caller is subject to premature termination from alerts. This flag also causes the I/O system to maintain the file position context. If this flag is set, the *DesiredAccess* SYNCHRONIZE flag also must be set so that the I/O Manager uses the file object as a synchronization object. |
| FILE_SYNCHRONOUS_IO_NONALERT (0x00000020) | All operations on the file are performed synchronously. Waits in the system to synchronize I/O queuing and completion are not subject to alerts. This flag also causes the I/O system to maintain the file position context. If this flag is set, the *DesiredAccess* SYNCHRONIZE flag also must be set so that the I/O Manager uses the file object as a synchronization object. |
| FILE_NON_DIRECTORY_FILE (0x00000040) | The file being opened must not be a directory file or this call fails. The file object being opened can represent a data file; a logical, virtual, or physical device; or a volume. |
| FILE_CREATE_TREE_CONNECTION (0x00000080) | Create a tree connection for this file in order to open it over the network. |
| FILE_COMPLETE_IF_OPLOCKED (0x00000100) | Complete this operation immediately with an alternate success code if the target file is oplocked, rather than blocking the caller's thread. If the file is oplocked, another caller already has access to the file over the network. |
| FILE_NO_EA_KNOWLEDGE (0x00000200) | If the extended attributes on an existing file being opened indicate that the caller must understand extended attributes to properly interpret the file, fail this request because the caller does not understand how to deal with extended attributes. |
| FILE_OPEN_REMOTE_INSTANCE (0x00000400) | Reserved for system use; do not use. |
| FILE_RANDOM_ACCESS (0x00000800) | Accesses to the file can be random, so no sequential read-ahead operations should be performed on the file by file systems or the operating system. |
| FILE_DELETE_ON_CLOSE (0x00001000) | Delete the file when the last handle to it is passed to [**FltClose**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltclose). |
| FILE_OPEN_BY_FILE_ID (0x00002000) | The file is being opened by ID. The file name contains the name of a device and a 64-bit ID to be used to open the file. |
| FILE_OPEN_FOR_BACKUP_INTENT (0x000004000) | The file is being opened for backup intent; therefore, the system should check for certain access rights and grant the caller the appropriate accesses to the file before checking the input *DesiredAccess* against the file's security descriptor. |
| FILE_NO_COMPRESSION (0x00008000) | Suppress inheritance of FILE_ATTRIBUTE_COMPRESSED from the parent directory. This allows creation of a non-compressed file in a directory that is marked compressed. |
| FILE_OPEN_REQUIRING_OPLOCK (0x00010000) | The file is being opened and an opportunistic lock (oplock) on the file is being requested as a single atomic operation. The file system checks for oplocks before it performs the create operation, and the create operation will fail with a return code of STATUS_CANNOT_BREAK_OPLOCK if the create operation would break an existing oplock. This flag is available in Windows 7, Windows Server 2008 R2 and later Windows operating systems. |
| FILE_DISALLOW_EXCLUSIVE (0x00020000) | When opening an existing file, if FILE_SHARE_READ is not specified and file system access checks would not grant the caller write access to the file, fail this open with STATUS_ACCESS_DENIED. This was default behavior prior to Windows 7. |
| FILE_SESSION_AWARE (0x00040000) | The file or device is being opened with session awareness. If this flag is not specified, then per-session devices (such as a device using RemoteFX USB Redirection) cannot be opened by processes running in session 0. This flag has no effect for callers not in session 0. This flag is supported only on server editions of Windows. This flag is not supported before Windows Server 2012. |
| FILE_RESERVE_OPFILTER (0x00100000) | This flag allows an application to request a filter opportunistic lock (oplock) to prevent other applications from getting share violations. If there are already open handles, the create request will fail with STATUS_OPLOCK_NOT_GRANTED. For more information, see the following Remarks section. |
| FILE_OPEN_REPARSE_POINT (0x00200000) | Open a file with a reparse point and bypass normal reparse point processing for the file. For more information, see the following Remarks section. |
| FILE_OPEN_NO_RECALL (0x00400000) | Instructs any filters that perform offline storage or virtualization to not recall the contents of the file as a result of this open. |
| FILE_OPEN_FOR_FREE_SPACE_QUERY (0x00800000) | |

### -param EaBuffer [in, optional]

A pointer to a caller-supplied [FILE_FULL_EA_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_file_full_ea_information)-structured buffer containing extended attribute (EA) information to be applied to the file.

### -param EaLength [in]

Length, in bytes, of *EaBuffer*.

### -param Flags [in]

Specifies options to be used during the creation of the create request. The following table lists the available options.

| Options Flags | Meaning |
| ------------- | ------- |
| IO_FORCE_ACCESS_CHECK | Indicates that the I/O manager must check the create request against the file's security descriptor. |
| IO_IGNORE_SHARE_ACCESS_CHECK | Indicates that the I/O manager should not perform share-access checks on the file object after it is created. However, the file system might still perform these checks. |

## -returns

**FltCreateFile** returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_FLT_DELETING_OBJECT | The specified *Filter* or *Instance* is being torn down. This status code can be received if the open crosses a volume mount point and the *Instance* parameter is non-**NULL**. This is an error code. |
| STATUS_INSUFFICIENT_RESOURCES | [FltCreateFile](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcreatefile) encountered a pool allocation. This is an error code. |
| STATUS_MOUNT_POINT_NOT_RESOLVED | The file or directory name contains a mount point that resolves to a volume other than the one that the specified minifilter driver instance is attached to. |
| STATUS_OBJECT_PATH_SYNTAX_BAD | The *ObjectAttributes* parameter did not contain a **RootDirectory** member, but the **ObjectName** member in the OBJECT_ATTRIBUTES structure was an empty string or did not contain an OBJECT_NAME_PATH_SEPARATOR character. This indicates incorrect syntax for the object path. |

> [!NOTE]
>
> **FltCreateFile** might return STATUS_FILE_LOCK_CONFLICT as the return value or in the **Status** member of the IO_STATUS_BLOCK structure that is pointed to by the IoStatusBlock parameter. This would occur only if the NTFS log file is full, and an error occurs while **FltCreateFile** tries to handle this situation.

## -remarks

On versions of Windows earlier than Microsoft Windows Update Rollup for Windows 2000 SP4 and Windows Server 2003 SP1, minifilter drivers should call **FltCreateFile** instead of [**IoCreateFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iocreatefile), [**IoCreateFileSpecifyDeviceObjectHint**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-iocreatefilespecifydeviceobjecthint), or [**ZwCreateFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntcreatefile) to obtain a file handle for use with **Zw***Xxx* I/O routines such as [**ZwReadFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntreadfile) and [**ZwQueryInformationFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntqueryinformationfile).

On Microsoft Windows Update Rollup for Windows 2000 SP4, Windows Server 2003 SP1 and later, minifilter drivers can use [**FltCreateFileEx**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcreatefileex) to obtain a file object pointer for use with **Flt*Xxx*File** routines such as [**FltReadFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltreadfile) and [**FltWriteFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltwritefile). On earlier versions of Windows, the handle obtained from **FltCreateFile** can be converted into a file object pointer by calling [**ObReferenceObjectByHandle**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-obreferenceobjectbyhandle) as follows:

```NTSTATUS status;
status = ObReferenceObjectByHandle(
           handle,                 //Handle
           0,                      //DesiredAccess
           NULL,                   //ObjectType
           KernelMode,             //AccessMode
           &handleFileObject,      //Object
           NULL);                  //HandleInformation</pre>
```

**FltCreateFile** sends the create request only to the instances attached below the specified minifilter driver instance and to the file system. The specified instance and the instances attached above it do not receive the create request. If no instance is specified, the request goes to the top of the stack and is received by all instances and the file system.

There are two alternate ways to specify the name of the file to be created or opened with **FltCreateFile**:

* As a fully qualified pathname, supplied in the **ObjectName** member of the input *ObjectAttributes*
* As a pathname relative to the directory file represented by the handle in the **RootDirectory **member of the input *ObjectAttributes*
* Any handle that is obtained from **FltCreateFile** must eventually be released by calling [**FltClose**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltclose).

Driver routines that do not run in the system process context must set the OBJ_KERNEL_HANDLE attribute for the *ObjectAttributes* parameter of **FltCreateFile**. Setting this attribute restricts the use of the handle that is returned by **FltCreateFile** to processes running in kernel mode. Otherwise, the handle can be accessed by the process in whose context the driver is running.

> [!NOTE]
> Do not call this routine with a non-NULL top level IRP value, as this can cause a system deadlock.

Certain *DesiredAccess* flags and combinations of flags have the following effects:

* For a caller to synchronize an I/O completion by waiting for the returned *FileHandle* to be set to the Signaled state, the SYNCHRONIZE flag must be set.
* Setting the FILE_WRITE_DATA flag for a file also allows writes beyond the end of the file to occur. The file is automatically extended for this type of write, as well.
* If only the FILE_EXECUTE and SYNCHRONIZE flags are set, the caller cannot use the returned *FileHandle* to directly read or write any data to or from the file. That is, all operations on the file must use system paging I/O to read or write file data.

The *ShareAccess* parameter determines whether separate threads can access the same file, possibly simultaneously. If both file openers have the privilege to access a file in the specified manner, the file can be successfully opened and shared. If the original caller of **FltCreateFile** does not specify FILE_SHARE_READ, FILE_SHARE_WRITE, or FILE_SHARE_DELETE, no other open operations can be performed on the file because the original caller is given exclusive access to the file.

For a shared file to be successfully opened, the requested *DesiredAccess* to the file must be compatible with both the *DesiredAccess* and *ShareAccess* specifications of all preceding opens that have not yet been released with [FltClose](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltclose). That is, the *DesiredAccess* specified to **FltCreateFile** for a given file must not conflict with the accesses that other openers of the file have disallowed.

> [!NOTE]
> If IO_IGNORE_SHARE_ACCESS_CHECK is specified in the *Flags* parameter, the I/O manager ignores the *ShareAccess* parameter. However, the file system might still perform access checks. Thus, it is important to specify the sharing mode you would like for the *ShareAccess *parameter, even when using the IO_IGNORE_SHARE_ACCESS_CHECK flag.

The *CreateDisposition* value FILE_SUPERSEDE requires that the caller have DELETE access to an existing file object. If so, a successful call to **FltCreateFile** with FILE_SUPERSEDE on an existing file effectively deletes that file and then recreates it. This implies that if the file has already been opened by another thread, it opened the file by specifying a *ShareAccess *parameter with the FILE_SHARE_DELETE flag set. Note that this type of disposition is consistent with the POSIX style of overwriting files.

The *CreateDisposition* values FILE_OVERWRITE_IF and FILE_SUPERSEDE are similar. If **FltCreateFile** is called with an existing file and either of these *CreateDisposition* values, the file is replaced.

Overwriting a file is semantically equivalent to a supersede operation, except for the following:

* The caller must have write access to the file, rather than delete access. This implies that, if the file has already been opened by another thread, it opened the file with the FILE_SHARE_WRITE flag set in the input *ShareAccess*.
* The specified file attributes are logically ORed with those already on the file. This implies that if the file has already been opened by another thread, a subsequent caller of **FltCreateFile** cannot disable existing *FileAttributes* flags but can enable additional flags for the same file. Note that this style of overwriting files is consistent with MS-DOS, Windows 3.1, and OS/2.

The *CreateOptions* FILE_DIRECTORY_FILE value specifies that the file to be created or opened is a directory file. When a directory file is created, the file system creates an appropriate structure on the disk to represent an empty directory for that particular file system's on-disk structure. If this option was specified and the given file to be opened is not a directory file or if the caller specified an inconsistent *CreateOptions* or *CreateDisposition* value, the call to **FltCreateFile** fails.

The *CreateOptions* FILE_NO_INTERMEDIATE_BUFFERING flag prevents the file system from performing any intermediate buffering on behalf of the caller. Specifying this value places certain restrictions on the caller's parameters to **Zw..File** routines, including the following:

* Any byte *Offset* value passed to [**ZwReadFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntreadfile) or [**ZwWriteFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntwritefile) must be a multiple of the sector size.
* The *Length* passed to **ZwReadFile** or **ZwWriteFile** must be a multiple of the sector size. Note that specifying a read operation to a buffer whose length is exactly the sector size might result in fewer significant bytes being transferred to that buffer if the end of the file was reached during the transfer.
* Buffers must be aligned in accordance with the alignment requirement of the underlying storage device. This information can be obtained by calling **FltCreateFile** to get a handle for the file object that represents the physical device and then calling [**ZwQueryInformationFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntqueryinformationfile) with that handle, specifying FileAlignmentInformation as the *FileInformationClass*. For more information about the system FILE_*XXX*_ALIGNMENT values, which are defined in ntifs.h, see [DEVICE_OBJECT](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_device_object) and [Initializing a Device Object](https://docs.microsoft.com/windows-hardware/drivers/kernel/initializing-a-device-object).
* Calls to [**ZwSetInformationFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntsetinformationfile) with the *FileInformationClass* parameter set to **FilePositionInformation** must specify an offset that is a multiple of the sector size.

The *CreateOptions* FILE_SYNCHRONOUS_IO_ALERT and FILE_SYNCHRONOUS_IO_NONALERT, which are mutually exclusive as their names suggest, specify that the file is being opened for synchronous I/O. This means that all I/O operations on the file are to be synchronous as long as they occur through the file object that the returned *FileHandle* refers to. All I/O on such a file is serialized across all threads by using the returned handle. With either of these *CreateOptions* set, the I/O Manager maintains the current file position offset in the file object's **CurrentByteOffset** field. This offset can be used in calls to [**ZwReadFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntreadfile) and [**ZwWriteFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntwritefile). It can also be queried or set by calling [**ZwQueryInformationFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntqueryinformationfile) or [**ZwSetInformationFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntsetinformationfile).

If the *CreateOptions* FILE_OPEN_REPARSE_POINT flag is not specified and **FltCreateFile** attempts to open a file with a reparse point, normal reparse point processing occurs for the file.  If, on the other hand, the FILE_OPEN_REPARSE_POINT flag is specified, normal reparse processing does not occur and **FltCreateFile** attempts to directly open the reparse point file.  In either case, if the open operation was successful, **FltCreateFile** returns STATUS_SUCCESS; otherwise, the routine returns an NTSTATUS error code. **FltCreateFile** never returns STATUS_REPARSE.

The *CreateOptions* FILE_OPEN_REQUIRING_OPLOCK flag eliminates the time between when you open the file and request an oplock that could potentially enable a third party to open the file and get a sharing violation. An application can use the FILE_OPEN_REQUIRING_OPLOCK flag on **FltCreateFile** and then request any oplock. This ensures that an oplock owner will be notified of any later open request that causes a sharing violation.

In Windows 7, if other handles exist on the file when an application uses the FILE_OPEN_REQUIRING_OPLOCK flag, the create operation will fail with STATUS_OPLOCK_NOT_GRANTED. This restriction no longer exists starting with Windows 8.

If this create operation would break an oplock that already exists on the file, then setting the FILE_OPEN_REQUIRING_OPLOCK flag will cause the create operation to fail with STATUS_CANNOT_BREAK_OPLOCK. The existing oplock will not be broken by this create operation.

 An application that uses this flag must request an oplock after this call succeeds, or all later attempts to open the file will be blocked without the benefit of typical oplock processing. Similarly, if this call succeeds but the later oplock request fails, an application that uses this flag must close its handle after it detects that the oplock request has failed.

> [!NOTE]
> The FILE_OPEN_REQUIRING_OPLOCK flag is available in Windows 7, Windows Server 2008 R2 and later Windows operating systems. The Microsoft file systems that implement this flag in Windows 7 are NTFS, FAT, and exFAT.

The *CreateOptions* flag FILE_RESERVE_OPFILTER allows an application to request a level 1, batch, or filter oplock to prevent other applications from getting share violations. However, FILE_RESERVE_OPFILTER is only practically useful for filter oplocks. To use it, you must complete the following steps:

1. Issue a create request with CreateOptions of FILE_RESERVE_OPFILTER, DesiredAccess of exactly FILE_READ_ATTRIBUTES, and ShareAccess of exactly FILE_SHARE_READ | FILE_SHARE_WRITE | FILE_SHARE_DELETE.
   * If there are already open handles, the create request fails with STATUS_OPLOCK_NOT_GRANTED, and the next requested oplock also fails.
   * If you open with more access or less sharing will also cause a failure of STATUS_OPLOCK_NOT_GRANTED.
2. If the create request succeeds, request an oplock.
3. Open another handle to the file to do I/O.  

Step three makes this practical only for filter oplocks. The handle opened in step 3 can have a DesiredAccess that contains a maximum of FILE_READ_ATTRIBUTES | FILE_WRITE_ATTRIBUTES | FILE_READ_DATA | FILE_READ_EA | FILE_EXECUTE | SYNCHRONIZE | READ_CONTROL and still not break a filter oplock. However, any DesiredAccess greater than FILE_READ_ATTRIBUTES | FILE_WRITE_ATTRIBUTES | SYNCHRONIZE will break a level 1 or batch oplock and make the FILE_RESERVE_OPFILTER flag useless for those oplock types.

NTFS is the only Microsoft file system that implements FILE_RESERVE_OPFILTER.

Minifilter drivers must use [**FltSetInformationFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltsetinformationfile), not [**ZwSetInformationFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntsetinformationfile), to rename a file.

> [!NOTE]
> If you try to open a volume but only specify a combination of the following flags for the *DesiredAccess* parameter, **FltCreateFile** will open a handle, independent of the file system, that has direct access to the storage device for the volume.
>
> * FILE_READ_ATTRIBUTES
> * READ_CONTROL
> * WRITE_DAC
> * WRITE_OWNER
> * SYNCHRONIZE
>
> You must not use **FltCreateFile** to open a handle with direct access to the storage device for the volume or you will leak system resources. If you want to open a handle with direct access to a storage device, call the [**IoCreateFileEx**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-iocreatefileex), [**IoCreateFileSpecifyDeviceObjectHint**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-iocreatefilespecifydeviceobjecthint), or [**ZwCreateFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntcreatefile) function instead.

## -see-also

[ACCESS_MASK](https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask)

[ACL](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_acl)

[DEVICE_OBJECT](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_device_object)

[FILE_FULL_EA_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_file_full_ea_information)

[**FltClose**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltclose)

[**FltCreateFileEx**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcreatefileex)

[**FltCreateFileEx2**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcreatefileex2)

[**FltReadFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltreadfile)

[**FltWriteFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltwritefile)

[**InitializeObjectAttributes**](https://docs.microsoft.com/windows/desktop/api/ntdef/nf-ntdef-initializeobjectattributes)

[**IoCreateFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iocreatefile)

[**IoCreateFileSpecifyDeviceObjectHint**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-iocreatefilespecifydeviceobjecthint)

[**ObReferenceObjectByHandle**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-obreferenceobjectbyhandle)

[SECURITY_DESCRIPTOR](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_security_descriptor)

[UNICODE_STRING](https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string)

[**ZwCreateFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntcreatefile)

[**ZwQueryInformationFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntqueryinformationfile)

[**ZwReadFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntreadfile)

[**ZwSetInformationFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntsetinformationfile)

[**ZwWriteFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntwritefile)
