---
UID: NF:ntifs.NtCreateFile
title: NtCreateFile function (ntifs.h)
description: The NtCreateFile routine creates a new file or opens an existing file.
old-location: kernel\zwcreatefile.htm
tech.root: kernel
ms.date: 05/24/2022
keywords: ["NtCreateFile function"]
ms.keywords: NtCreateFile, ZwCreateFile, ZwCreateFile routine [Kernel-Mode Driver Architecture], k111_80b1882a-8617-45d4-a783-dbc3bfc9aad4.xml, kernel.zwcreatefile, wdm/NtCreateFile, wdm/ZwCreateFile
req.header: ntifs.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows 2000
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
targetos: Windows
req.typenames: 
f1_keywords:
 - NtCreateFile
 - ntifs/NtCreateFile
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - NtCreateFile
---

# NtCreateFile function

## -description

The **NtCreateFile** routine creates a new file or opens an existing file.

## -parameters

### -param FileHandle [out]

A pointer to a HANDLE variable that receives a handle to the file.

### -param DesiredAccess [in]

Specifies an [ACCESS_MASK](/windows-hardware/drivers/kernel/access-mask) value that determines the requested access to the object.

In addition to the *standard* access rights that are defined for all types of objects, the caller can specify any of the following *specific* access rights; that is, rights that are specific to files.

| ACCESS_MASK flag      | Allows caller to do this |
| ----------------      | ------------------------ |
| FILE_READ_DATA        | Read data from the file. |
| FILE_READ_ATTRIBUTES  | Read the attributes of the file. For more information, see the description of the *FileAttributes* parameter. |
| FILE_READ_EA          | Read the extended attributes (EAs) of the file. This flag is irrelevant for device and intermediate drivers. |
| FILE_WRITE_DATA       | Write data to the file. |
| FILE_WRITE_ATTRIBUTES | Write the attributes of the file. For more information, see the description of the *FileAttributes* parameter. |
| FILE_WRITE_EA         | Change the extended attributes (EAs) of the file. This flag is irrelevant for device and intermediate drivers. |
| FILE_APPEND_DATA      | Append data to the file. |
| FILE_EXECUTE          | Use system paging I/O to read data from the file into memory. This flag is irrelevant for device and intermediate drivers. |

> [!NOTE]
> Do not specify FILE_READ_DATA, FILE_WRITE_DATA, FILE_APPEND_DATA, or FILE_EXECUTE when you create or open a directory.

The caller can also specify the following *generic* access rights (rights that apply to all object types, where the meaning of each generic access right is specific to the object type). Generic access rights for file objects correspond to specific access rights as shown in the following table. (Note that "correspond" means "maps to" and does not mean that the value of the generic right is "equal to" the value of the bitwise OR of its specific rights mapping). The I/O manager defines the actual mapping.

| Generic access right | Maps to these specific access rights |
| -------------------- | ------------------------------------ |
| GENERIC_READ    | STANDARD_RIGHTS_READ, FILE_READ_DATA, FILE_READ_ATTRIBUTES, FILE_READ_EA, and SYNCHRONIZE |
| GENERIC_WRITE   | STANDARD_RIGHTS_WRITE, FILE_WRITE_DATA, FILE_WRITE_ATTRIBUTES, FILE_WRITE_EA, FILE_APPEND_DATA, and SYNCHRONIZE |
| GENERIC_EXECUTE | STANDARD_RIGHTS_EXECUTE, FILE_EXECUTE, FILE_READ_ATTRIBUTES, and SYNCHRONIZE. This value is irrelevant for device and intermediate drivers. |
| GENERIC_ALL     | FILE_ALL_ACCESS |

> [!NOTE]
> *Generic* access rights can only be specified for a file; they cannot be specified for a directory.
>
> Some **CreateOptions** flags require that certain access flags be set in **DesiredAccess** when **NtCreateFile** is called. See the **CreateOptions** parameter for these details.

For example, if you specify GENERIC_READ for a file object, the routine maps this value to the FILE_GENERIC_READ bitmask of specific access rights. In the preceding table, the specific access rights that are listed for GENERIC_READ correspond to (but are not equal to) the access flags that are contained in the FILE_GENERIC_READ bitmask.

If the file is actually a directory, the caller can also specify the following generic access rights.

|*DesiredAccess* flag | Allows caller to do this |
|-------------------- | ------------------------ |
|FILE_LIST_DIRECTORY  | List the files in the directory. |
|FILE_TRAVERSE        | Traverse the directory, in other words, include the directory in the path of a file. |

For more information about access rights, see [ACCESS_MASK](/windows-hardware/drivers/kernel/access-mask) and [Access Rights](/windows-hardware/drivers/kernel/access-rights).

### -param ObjectAttributes [in]

A pointer to an [OBJECT_ATTRIBUTES](/windows-hardware/drivers/ddi/wudfwdm/ns-wudfwdm-_object_attributes) structure that specifies the object name and other attributes. Use [InitializeObjectAttributes](/windows-hardware/drivers/ddi/wudfwdm/nf-wudfwdm-initializeobjectattributes) to initialize this structure. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE attribute when it calls **InitializeObjectAttributes**.

### -param IoStatusBlock [out]

A pointer to an [IO_STATUS_BLOCK](../wdm/ns-wdm-_io_status_block.md) structure that receives the final completion status and other information about the requested operation. In particular, the **Information** member receives one of the following values:

* FILE_CREATED
* FILE_OPENED
* FILE_OVERWRITTEN
* FILE_SUPERSEDED
* FILE_EXISTS
* FILE_DOES_NOT_EXIST

### -param AllocationSize [in, optional]

A pointer to a LARGE_INTEGER that contains the initial allocation size, in bytes, for a file that is created or overwritten. If *AllocationSize* is **NULL**, no allocation size is specified. If no file is created or overwritten, *AllocationSize* is ignored.

### -param FileAttributes [in]

Specifies one or more FILE_ATTRIBUTE_*XXX* flags, which represent the file attributes to set if you create or overwrite a file. The caller usually specifies FILE_ATTRIBUTE_NORMAL, which sets the default attributes. For a list of valid FILE_ATTRIBUTE_*XXX* flags, see the [CreateFile](/windows/win32/api/fileapi/nf-fileapi-createfilea) routine in the Microsoft Windows SDK documentation. If no file is created or overwritten, *FileAttributes* is ignored.

### -param ShareAccess [in]

Type of share access, which is specified as zero or any combination of the following flags.

| *ShareAccess* flag | Allows other threads to do this |
| ------------------ | ------------------------------- |
| FILE_SHARE_READ    | Read the file                   |
| FILE_SHARE_WRITE   | Write the file                  |
| FILE_SHARE_DELETE  | Delete the file                 |

Device and intermediate drivers usually set *ShareAccess* to zero, which gives the caller exclusive access to the open file.

### -param CreateDisposition [in]

Specifies the action to perform if the file does or does not exist. *CreateDisposition* can be one of the values in the following table.

| *CreateDisposition* value | Action if file exists            | Action if file does not exist |
| ------------------------- | ---------------------            | ----------------------------- |
| FILE_SUPERSEDE            | Replace the file.                | Create the file. |
| FILE_CREATE               | Return an error.                 | Create the file. |
| FILE_OPEN                 | Open the file.                   | Return an error. |
| FILE_OPEN_IF              | Open the file.                   | Create the file. |
| FILE_OVERWRITE            | Open the file, and overwrite it. | Return an error. |
| FILE_OVERWRITE_IF         | Open the file, and overwrite it. | Create the file. |

### -param CreateOptions [in]

Specifies the options to apply when the driver creates or opens the file. Use one or more of the flags in the following table.

| CreateOptions flag | Meaning |
| -------------------- | ------- |
| FILE_DIRECTORY_FILE (0x00000001) | The file is a directory. Compatible **CreateOptions** flags are FILE_SYNCHRONOUS_IO_ALERT, FILE_SYNCHRONOUS_IO_NONALERT, FILE_WRITE_THROUGH, FILE_OPEN_FOR_BACKUP_INTENT, and FILE_OPEN_BY_FILE_ID. The **CreateDisposition** parameter must be set to FILE_CREATE, FILE_OPEN, or FILE_OPEN_IF. |
| FILE_WRITE_THROUGH (0x00000002) | System services, file-system drivers, and drivers that write data to the file must actually transfer the data to the file before any requested write operation is considered complete. |
| FILE_SEQUENTIAL_ONLY (0x00000004) | All access to the file will be sequential. |
| FILE_NO_INTERMEDIATE_BUFFERING (0x00000008) | The file cannot be cached or buffered in a driver's internal buffers. This flag is incompatible with the **DesiredAccess** parameter's FILE_APPEND_DATA flag. |
| FILE_SYNCHRONOUS_IO_ALERT (0x00000010) | All operations on the file are performed synchronously. Any wait on behalf of the caller is subject to premature termination from alerts. This flag also causes the I/O system to maintain the file-position pointer. If this flag is set, the SYNCHRONIZE flag must be set in the **DesiredAccess** parameter. |
| FILE_SYNCHRONOUS_IO_NONALERT (0x00000020) | All operations on the file are performed synchronously. Waits in the system that synchronize I/O queuing and completion are not subject to alerts. This flag also causes the I/O system to maintain the file-position context. If this flag is set, the SYNCHRONIZE flag must be set in the **DesiredAccess** parameter. |
| FILE_NON_DIRECTORY_FILE (0x00000040) | The file is *not* a directory. The file object to open can represent a data file; a logical, virtual, or physical device; or a volume. |
| FILE_CREATE_TREE_CONNECTION (0x00000080) | Create a tree connection for this file in order to open it over the network. This flag is not used by device and intermediate drivers. |
| FILE_COMPLETE_IF_OPLOCKED (0x00000100) | Complete this operation immediately with an alternate success code of STATUS_OPLOCK_BREAK_IN_PROGRESS if the target file is oplocked, rather than blocking the caller's thread. If the file is oplocked, another caller already has access to the file. This flag is not used by device and intermediate drivers. |
| FILE_NO_EA_KNOWLEDGE (0x00000200) | If the extended attributes (EAs) for an existing file being opened indicate that the caller must understand EAs to properly interpret the file, **NtCreateFile** should return an error. This flag is irrelevant for device and intermediate drivers. |
| FILE_OPEN_REMOTE_INSTANCE (0x00000400) | Reserved for system use; do not use. |
| FILE_RANDOM_ACCESS (0x00000800) | Access to the file can be random, so no sequential read-ahead operations should be performed by file-system drivers or by the system. |
| FILE_DELETE_ON_CLOSE (0x00001000) | The system deletes the file when the last handle to the file is passed to [**NtClose**](nf-ntifs-ntclose.md). If this flag is set, the DELETE flag must be set in the **DesiredAccess** parameter. |
| FILE_OPEN_BY_FILE_ID (0x00002000) | The file name that is specified by the **ObjectAttributes** parameter includes a binary 8-byte or 16-byte file reference number or object ID for the file, depending on the file system. Optionally, a device name followed by a backslash character may proceed these binary values. See Remarks for additional details and an example. |
| FILE_OPEN_FOR_BACKUP_INTENT (0x00004000) | The file is being opened for backup intent. Therefore, the system should check for certain access rights and grant the caller the appropriate access to the file—before checking the **DesiredAccess** parameter against the file's security descriptor. This flag not used by device and intermediate drivers. |
| FILE_NO_COMPRESSION (0x00008000) | Suppress inheritance of FILE_ATTRIBUTE_COMPRESSED from the parent directory. This allows creation of a non-compressed file in a directory that is marked compressed. |
| FILE_OPEN_REQUIRING_OPLOCK (0x00010000) | The file is being opened and an opportunistic lock (oplock) on the file is being requested as a single atomic operation. The file system checks for oplocks before it performs the create operation, and will fail the create with a return code of STATUS_CANNOT_BREAK_OPLOCK if the result would be to break an existing oplock. This flag is available starting with Windows 7 and Windows Server 2008 R2. |
| FILE_DISALLOW_EXCLUSIVE (0x00020000) | When opening an existing file, if FILE_SHARE_READ is not specified and file system access checks would not grant the caller write access to the file, fail this open with STATUS_ACCESS_DENIED. This was default behavior prior to Windows 7. This flag is available starting with Windows 7 and Windows Server 2008 R2. |
| FILE_SESSION_AWARE (0x00040000) | The client opening the file or device is session aware and per session access is validated if necessary. This flag is available starting with Windows 8. |
| FILE_RESERVE_OPFILTER (0x00100000) | This flag allows an application to request a Filter opportunistic lock (oplock) to prevent other applications from getting share violations. If there are already open handles, the create request will fail with STATUS_OPLOCK_NOT_GRANTED. For more information, see the following Remarks section. |
| FILE_OPEN_REPARSE_POINT (0x00200000) | Open a file with a reparse point and bypass normal reparse point processing for the file. For more information, see the following Remarks section. |
| FILE_OPEN_NO_RECALL (0x00400000) | Instructs any filters that perform offline storage or virtualization to not recall the contents of the file as a result of this open. |
| FILE_OPEN_FOR_FREE_SPACE_QUERY (0x00800000) | This flag instructs the file system to capture the user associated with the calling thread. Any subsequent calls to FltQueryVolumeInformation or ZwQueryVolumeInformationFile using the returned handle will assume the captured user, rather than the calling user at the time, for purposes of computing the free space available to the caller. This applies to the following FsInformationClass values: FileFsSizeInformation, FileFsFullSizeInformation, and FileFsFullSizeInformationEx. |
| FILE_CONTAINS_EXTENDED_CREATE_INFORMATION (0x10000000) | Interpret the **EaBuffer** parameter as an instance of [**EXTENDED_CREATE_INFORMATION**](/windows-hardware/drivers/ifs/ns-ntifs-extended_create_information). This flag is available starting in Windows 11, version 22H2. |

### -param EaBuffer [in, optional]

For device and intermediate drivers, this parameter must be a **NULL** pointer.

### -param EaLength [in]

For device and intermediate drivers, this parameter must be zero.

## -returns

**NtCreateFile** returns STATUS_SUCCESS on success or an appropriate NTSTATUS error code on failure. In the latter case, the caller can determine the cause of the failure by checking the *IoStatusBlock* parameter.

> [!NOTE]
> **NtCreateFile** might return STATUS_FILE_LOCK_CONFLICT as the return value or in the **Status** member of the **IO_STATUS_BLOCK** structure that is pointed to by the *IoStatusBlock* parameter. This would occur only if the NTFS log file is full, and an error occurs while **NtCreateFile** tries to handle this situation.

## -remarks

**NtCreateFile** supplies a handle that the caller can use to manipulate a file's data, or the file object's state and attributes. For more information, see [Using Files in a Driver](/windows-hardware/drivers/kernel/using-files-in-a-driver).

Once the handle pointed to by *FileHandle* is no longer in use, the driver must call [NtClose](./nf-ntifs-ntclose.md) to close it.

If the caller is not running in a system thread context, it must ensure that any handles it creates are private handles. Otherwise, the handle can be accessed by the process in whose context the driver is running. For more information, see [Object Handles](/windows-hardware/drivers/kernel/object-handles).

There are two alternate ways to specify the name of the file to be created or opened with **NtCreateFile**:

* As a fully qualified pathname, supplied in the **ObjectName** member of the input *ObjectAttributes.*
* As pathname relative to the directory file represented by the handle in the **RootDirectory** member of the input *ObjectAttributes*.

Setting certain flags in the *DesiredAccess* parameter results in the following effects:

* For a caller to synchronize an I/O completion by waiting for the returned *FileHandle*, the SYNCHRONIZE flag must be set. Otherwise, a caller that is a device or intermediate driver must synchronize an I/O completion by using an event object.
* If the caller sets only the FILE_APPEND_DATA and SYNCHRONIZE flags, it can write only to the end of the file, and any offset information about write operations to the file is ignored. The file will automatically be extended as necessary for this type of operation.
* Setting the FILE_WRITE_DATA flag for a file also allows the caller to write beyond the end of the file. Again, the file is automatically extended as necessary.
* If the caller sets only the FILE_EXECUTE and SYNCHRONIZE flags, it cannot directly read or write any data to the file using the returned *FileHandle*. That is, all operations on the file occur through the system pager in response to instruction and data-access operations. Device and intermediate drivers should not set the FILE_EXECUTE flag.

The *ShareAccess* parameter determines whether separate threads can access the same file, possibly simultaneously. Provided that both callers have the appropriate access privileges, the file can be successfully opened and shared. If the original caller of **NtCreateFile** does not specify FILE_SHARE_READ, FILE_SHARE_WRITE, or FILE_SHARE_DELETE, no other caller can open the file—that is, the original caller is granted exclusive access.

To successfully open a shared file, the *DesiredAccess* flags must be compatible with the *DesiredAccess* and *ShareAccess* flags of all the previous open operations that have not yet been released through . That is, the *DesiredAccess* specified to **NtCreateFile** for a given file must not conflict with the accesses that other openers of the file have disallowed.

The *CreateDisposition* value FILE_SUPERSEDE requires that the caller have DELETE access to a existing file object. If so, a successful call to **NtCreateFile** with FILE_SUPERSEDE on an existing file effectively deletes that file, and then recreates it. This implies that, if the file has already been opened by another thread, it opened the file by specifying a *ShareAccess* parameter with the FILE_SHARE_DELETE flag set. Note that this type of disposition is consistent with the POSIX style of overwriting files.

The *CreateDisposition* values FILE_OVERWRITE_IF and FILE_SUPERSEDE are similar. If **NtCreateFile** is called with a existing file and either of these *CreateDisposition* values, the file will be replaced.

Overwriting a file is semantically equivalent to a supersede operation, except for the following:

* The caller must have write access to the file, rather than delete access. This implies that, if the file has already been opened by another thread, it opened the file with the FILE_SHARE_WRITE flag set in the input *ShareAccess*.
* The specified file attributes are logically ORed with those already on the file. This implies that, if the file has already been opened by another thread, a subsequent caller of **NtCreateFile** cannot disable existing *FileAttributes* flags but can enable additional flags for the same file. Note that this style of overwriting files is consistent with MS-DOS, Microsoft Windows 3.1, and OS/2.

The FILE_DIRECTORY_FILE *CreateOptions* value specifies that the file to be created or opened is a directory. When a directory file is created, the file system creates an appropriate structure on the disk to represent an empty directory for that particular file system's on-disk structure. If this option was specified and the given file to be opened is not a directory file, or if the caller specified an inconsistent *CreateOptions* or *CreateDisposition* value, the call to **NtCreateFile** will fail.

The FILE_NO_INTERMEDIATE_BUFFERING *CreateOptions* flag prevents the file system from performing any intermediate buffering on behalf of the caller. Specifying this flag places the following restrictions on the caller's parameters to other **Zw*Xxx*File** routines.

* Any optional *ByteOffset* passed to [NtReadFile](./nf-ntifs-ntreadfile.md) or [NtWriteFile](./nf-ntifs-ntwritefile.md) must be a multiple of the sector size.
* The *Length* passed to **NtReadFile** or **NtWriteFile** must be an integral of the sector size. Note that specifying a read operation to a buffer whose length is exactly the sector size might result in a lesser number of significant bytes being transferred to that buffer if the end of the file was reached during the transfer.
* Buffers must be aligned in accordance with the alignment requirement of the underlying device. To obtain this information, call **NtCreateFile** to get a handle for the file object that represents the physical device, and pass that handle to [NtQueryInformationFile](./nf-ntifs-ntqueryinformationfile.md). For a list of the system's FILE_*XXX*_ALIGNMENT values, see [DEVICE_OBJECT](../wdm/ns-wdm-_device_object.md).
* Calls to [NtSetInformationFile](./nf-ntifs-ntsetinformationfile.md) with the *FileInformationClass* parameter set to **FilePositionInformation** must specify an offset that is a multiple of the sector size.

The FILE_SYNCHRONOUS_IO_ALERT and FILE_SYNCHRONOUS_IO_NONALERT *CreateOptions* flags (which are mutually exclusive) specify that all I/O operations on the file will be synchronous, as long as the operations occur through the file object referred to by the returned *FileHandle*. All I/O on such a file is serialized across all threads using the returned handle. If either of these *CreateOptions* flags is set, the SYNCHRONIZE *DesiredAccess* flag must also be set to compel the I/O manager to use the file object as a synchronization object. In these cases, the I/O manager keeps track of the current file-position offset, which you can pass to **NtReadFile** and **NtWriteFile**. Call **NtQueryInformationFile** or **NtSetInformationFile** to get or set this position.

If the *CreateOptions* FILE_OPEN_REPARSE_POINT flag is **not** specified and **NtCreateFile** attempts to open a file with a reparse point, normal reparse point processing occurs for the file. If, on the other hand, the FILE_OPEN_REPARSE_POINT flag is specified, normal reparse processing does *not* occur and **NtCreateFile** attempts to directly open the reparse point file. In either case, if the open operation was successful, **NtCreateFile** returns STATUS_SUCCESS; otherwise, the routine returns an NTSTATUS error code. **NtCreateFile** never returns STATUS_REPARSE.

The *CreateOptions* FILE_OPEN_REQUIRING_OPLOCK flag eliminates the time between when you open the file and request an oplock that could potentially allow a third party to open the file and get a sharing violation. An application can use the FILE_OPEN_REQUIRING_OPLOCK flag on **NtCreateFile** and then request any oplock. This ensures that an oplock owner will be notified of any subsequent open request that causes a sharing violation.

In Windows 7, if other handles exist on the file when an application uses the FILE_OPEN_REQUIRING_OPLOCK flag, the create operation will fail with STATUS_OPLOCK_NOT_GRANTED. This restriction no longer exists starting with Windows 8.

If this create operation would break an oplock that already exists on the file, then setting the FILE_OPEN_REQUIRING_OPLOCK flag will cause the create operation to fail with STATUS_CANNOT_BREAK_OPLOCK. The existing oplock will not be broken by this create operation.

An application that uses the FILE_OPEN_REQUIRING_OPLOCK flag must request an oplock after this call succeeds, or all subsequent attempts to open the file will be blocked without the benefit of normal oplock processing. Similarly, if this call succeeds but the subsequent oplock request fails, an application that uses this flag must close its handle after it detects that the oplock request has failed.

> [!NOTE]
> The FILE_OPEN_REQUIRING_OPLOCK flag is available in Windows 7, Windows Server 2008 R2 and later Windows operating systems. The Microsoft file systems that implement this flag in Windows 7 are NTFS, FAT, and exFAT.

The *CreateOptions* flag FILE_RESERVE_OPFILTER allows an application to request a Level 1, Batch, or Filter oplock to prevent other applications from getting share violations. However, FILE_RESERVE_OPFILTER is only practically useful for Filter oplocks. To use it, you must complete the following steps:

1. Issue a create request with *CreateOptions* of FILE_RESERVE_OPFILTER, *DesiredAccess* of exactly FILE_READ_ATTRIBUTES, and *ShareAccess* of exactly FILE_SHARE_READ | FILE_SHARE_WRITE | FILE_SHARE_DELETE.
    * If there are already open handles, the create request fails with STATUS_OPLOCK_NOT_GRANTED, and the next requested oplock also fails.
    * If you open with more access or less sharing will also cause a failure of STATUS_OPLOCK_NOT_GRANTED.
2. If the create request succeeds, request an oplock.
3. Open another handle to the file to do I/O.

Step 3 makes this practical only for Filter oplocks. The handle opened in step 3 can have a *DesiredAccess* that contains a maximum of FILE_READ_ATTRIBUTES | FILE_WRITE_ATTRIBUTES | FILE_READ_DATA | FILE_READ_EA | FILE_EXECUTE | SYNCHRONIZE | READ_CONTROL and still not break a Filter oplock. However, any *DesiredAccess* greater than FILE_READ_ATTRIBUTES | FILE_WRITE_ATTRIBUTES | SYNCHRONIZE will break a Level 1 or Batch oplock and make the FILE_RESERVE_OPFILTER flag useless for those oplock types.

NTFS is the only Microsoft file system that implements FILE_RESERVE_OPFILTER.

For the *CreateOptions* FILE_OPEN_BY_FILE_ID flag, an example device name will have the format: ```\??\C:\FileID\device\HardDiskVolume1\ObjectID```, where FileID is 8 bytes and ObjectID is 16 bytes:

* On NTFS, this can be a 8-byte or 16-byte reference number or object ID. A 16-byte reference number is the same as an 8-byte number padded with zeros.
* On ReFS, this can be an 8-byte or 16-byte reference number. A 16-byte number is not related to an 8-byte number. Object IDs are not supported.
* The FAT, ExFAT, UDFS, and CDFS file systems do not support the FILE_OPEN_BY_FILE_ID flag.

This number is assigned by and specific to the particular file system. Because the filename field will partly contain a binary blob, it is incorrect to assume that this is a valid Unicode string, and more importantly may not be a null terminated string.

Callers of **NtCreateFile** must be running at IRQL = PASSIVE_LEVEL and [with special kernel APCs enabled](/windows-hardware/drivers/kernel/disabling-apcs).

> [!NOTE]
> If the call to this function occurs in user mode, you should use the name "**NtCreateFile**" instead of "**ZwCreateFile**".

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[ACCESS_MASK](/windows-hardware/drivers/kernel/access-mask)

[DEVICE_OBJECT](../wdm/ns-wdm-_device_object.md)

[IO_STATUS_BLOCK](../wdm/ns-wdm-_io_status_block.md)

[InitializeObjectAttributes](/windows-hardware/drivers/ddi/wudfwdm/nf-wudfwdm-initializeobjectattributes)

[Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines)

[NtClose](./nf-ntifs-ntclose.md)

[NtOpenFile](./nf-ntifs-ntopenfile.md)

[NtQueryInformationFile](./nf-ntifs-ntqueryinformationfile.md)

[NtReadFile](./nf-ntifs-ntreadfile.md)

[NtSetInformationFile](./nf-ntifs-ntsetinformationfile.md)

[NtWriteFile](./nf-ntifs-ntwritefile.md)
