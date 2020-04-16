---
UID: NF:wdm.IoCreateFile
title: IoCreateFile function (wdm.h)
description: The IoCreateFile routine either causes a new file or directory to be created, or it opens an existing file, device, directory, or volume, giving the caller a handle for the file object.
old-location: kernel\iocreatefile.htm
tech.root: kernel
ms.assetid: 928f16d4-19cb-4d80-96a6-d25357bfdc30
ms.date: 02/13/2020
keywords: ["IoCreateFile function"]
ms.keywords: IoCreateFile, IoCreateFile routine [Kernel-Mode Driver Architecture], k104_7221dba8-910f-439a-acdf-5a6ca4fcd49a.xml, kernel.iocreatefile, wdm/IoCreateFile
f1_keywords:
 - "wdm/IoCreateFile"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlIoPassive4, PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoCreateFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoCreateFile function

## -description

The **IoCreateFile** routine either causes a new file or directory to be created, or it opens an existing file, device, directory, or volume, giving the caller a handle for the file object.

## -parameters

### -param FileHandle [out]

Pointer to a variable that receives the file handle if the call is successful. The driver must close the handle with [**ZwClose**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose) once the handle is no longer in use.

### -param DesiredAccess [in]

A bitmask of flags specifying the type of access to the file or directory that the caller requires. See the *DesiredAccess* parameter of [**IoCreateFileEx**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iocreatefileex#desiredaccess) for more information about this parameter and for the list of flag values.

### -param ObjectAttributes [in]

Pointer to an opaque [**OBJECT_ATTRIBUTES**](https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_object_attributes) structure that is already initialized with [**InitializeObjectAttributes**](https://docs.microsoft.com/windows/desktop/api/ntdef/nf-ntdef-initializeobjectattributes). See the *ObjectAttributes* parameter of [**IoCreateFileEx**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iocreatefileex#objectattributes) for more information and for a description of each structure member.

### -param IoStatusBlock [out]

Pointer to an [**IO_STATUS_BLOCK**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_status_block) structure that receives the final completion status and information about the requested operation. See the **IoStatusBlock** parameter of [**IoCreateFileEx**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iocreatefileex#iostatusblock).

### -param AllocationSize [in, optional]

Optionally specifies the initial allocation size in bytes for the file. A nonzero value has no effect unless the file is being created, overwritten, or superseded.

### -param FileAttributes [in]

Explicitly specified attributes are applied only when the file is created, superseded, or, in some cases, overwritten. By default, this value is FILE_ATTRIBUTE_NORMAL, which can be overridden by an ORed combination of one or more FILE_ATTRIBUTE_*XXX* flags, which are defined in Wdm.h. For a list of flags that can be used with **IoCreateFile**, see [**CreateFile**](https://docs.microsoft.com/windows/desktop/api/fileapi/nf-fileapi-createfilea) in the Microsoft Windows SDK documentation.

### -param ShareAccess [in]

Specifies the type of share access to the file that the caller requires, as zero or one, or a combination of the flags. See the *ShareAccess* parameter of [**IoCreateFileEx**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iocreatefileex#shareaccess) for more details and for the list of flags.

### -param Disposition [in]

Specifies a value that determines the action to be taken, depending on whether the file already exists. See the *Disposition* parameter of [**IoCreateFileEx**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iocreatefileex#disposition) for the list of possible values.

### -param CreateOptions [in]

Specifies the options to be applied when creating or opening the file. This parameter is a compatible combination of the flags listed and described in the *CreateOptions* parameter of [**IoCreateFileEx**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iocreatefileex#createoptions).

### -param EaBuffer [in, optional]

For device and intermediate drivers, this parameter must be a **NULL** pointer.

### -param EaLength [in]

For device and intermediate drivers, this parameter must be zero.

### -param CreateFileType [in]

Drivers must set this parameter to **CreateFileTypeNone**.

### -param InternalParameters [in, optional]

Drivers must set this parameter to **NULL**.

### -param Options [in]

Specifies options to be used during the creation of the create request. See the *Options* parameter of [**IoCreateFileEx**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iocreatefileex#options) for the list of possible options.

## -returns

**IoCreateFile** either returns STATUS_SUCCESS or an appropriate error status. NTSTATUS value. See the **Return Value** section of [**IoCreateFileEx**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iocreatefileex#returns) for a list of possible return codes.

## -remarks

> [!NOTE]
> The [**IoCreateFileEx**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iocreatefileex) routine is similar to the **IoCreateFile** routine but provides greater functionality than the **IoCreateFile** routine, including access to extra create parameters (ECPs), device objects, and transaction information.

The handle obtained by **IoCreateFile** can be used by subsequent calls to manipulate data within the file or the file object's state or attributes.

There are two alternate ways to specify the name of the file to be created or opened with **IoCreateFile**:

1. As a fully qualified pathname, supplied in the **ObjectName** member of the input *ObjectAttributes*
2. As pathname relative to the directory file represented by the handle in the **RootDirectory** member of the input *ObjectAttributes*

Certain *DesiredAccess* flags and combinations of flags have the following effects:

* For a caller to synchronize an I/O completion by waiting for the returned *FileHandle*, the SYNCHRONIZE flag must be set. Otherwise, a caller that is a device or intermediate driver must synchronize an I/O completion by using an event object.

* If only the FILE_APPEND_DATA and SYNCHRONIZE flags are set, the caller can write only to the end of the file, and any offset information about writes to the file is ignored. However, the file will automatically be extended as necessary for this type of write operation.

* Setting the FILE_WRITE_DATA flag for a file also allows writes beyond the end of the file to occur. The file is automatically extended for this type of write, as well.

* If only the FILE_EXECUTE and SYNCHRONIZE flags are set, the caller cannot directly read or write any data in the file using the returned *FileHandle*: that is, all operations on the file occur through the system pager in response to instruction and data accesses. Device and intermediate drivers should not set the FILE_EXECUTE flag in *DesiredAccess*.

The *ShareAccess* parameter determines whether separate threads can access the same file, possibly simultaneously. Provided that both file openers have the privilege to access a file in the specified manner, the file can be successfully opened and shared. If the original caller of **IoCreateFile** does not specify FILE_SHARE_READ, FILE_SHARE_WRITE, or FILE_SHARE_DELETE, no other open operations can be performed on the file: that is, the original caller is given exclusive access to the file.

In order for a shared file to be successfully opened, the requested *DesiredAccess* to the file must be compatible with both the *DesiredAccess* and *ShareAccess* specifications of all preceding opens that have not yet been released with **ZwClose**. That is, the *DesiredAccess* specified to **IoCreateFile** for a given file must not conflict with the accesses that other openers of the file have disallowed.

The *Disposition* value FILE_SUPERSEDE requires that the caller have DELETE access to a existing file object. If so, a successful call to **IoCreateFile** with FILE_SUPERSEDE on an existing file effectively deletes that file, and then recreates it. This implies that, if the file has already been opened by another thread, it opened the file by specifying a *ShareAccess *parameter with the FILE_SHARE_DELETE flag set. Note that this type of disposition is consistent with the POSIX style of overwriting files.

The *Disposition* values FILE_OVERWRITE_IF and FILE_SUPERSEDE are similar. If **IoCreateFile** is called with a existing file and either of these *Disposition* values, the file will be replaced.

Overwriting a file is semantically equivalent to a supersede operation, except for the following:

* The caller must have write access to the file, rather than delete access. This implies that, if the file has already been opened by another thread, it opened the file with the FILE_SHARE_WRITE flag set in the input *ShareAccess*.

* The specified file attributes are logically ORed with those already on the file. This implies that, if the file has already been opened by another thread, a subsequent caller of **IoCreateFile** cannot disable existing *FileAttributes* flags but can enable additional flags for the same file.

The *CreateOptions* FILE_DIRECTORY_FILE value specifies that the file to be created or opened is a directory file. When a directory file is created, the file system creates an appropriate structure on the disk to represent an empty directory for that particular file system's on-disk structure. If this option was specified and the given file to be opened is not a directory file, or if the caller specified an inconsistent *CreateOptions* or *Disposition* value, the call to **IoCreateFile** will fail.

The *CreateOptions* FILE_NO_INTERMEDIATE_BUFFERING flag prevents the file system from performing any intermediate buffering on behalf of the caller. Specifying this value places certain restrictions on the caller's parameters to the **Zw*Xxx*File** routines, including the following:

* Any optional *ByteOffset* passed to [**ZwReadFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntreadfile) or [**ZwWriteFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntwritefile) must be an integral of the sector size.

* The *Length* passed to **ZwReadFile** or **ZwWriteFile**, must be an integral of the sector size. Note that specifying a read operation to a buffer whose length is exactly the sector size might result in a lesser number of significant bytes being transferred to that buffer if the end of the file was reached during the transfer.

* Buffers must be aligned in accordance with the alignment requirement of the underlying device. This information can be obtained by calling **IoCreateFile** to get a handle for the file object that represents the physical device, and, then, calling [**ZwQueryInformationFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntqueryinformationfile) with that handle. For a list of the system FILE_*XXX*_ALIGNMENT values, see [**DEVICE_OBJECT**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object).

* Calls to [**ZwSetInformationFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntsetinformationfile) with the *FileInformationClass* parameter set to **FilePositionInformation** must specify an offset that is an integral of the sector size.

The *CreateOptions* FILE_SYNCHRONOUS_IO_ALERT and FILE_SYNCHRONOUS_IO_NONALERT, which are mutually exclusive as their names suggest, specify that all I/O operations on the file are to be synchronous as long as they occur through the file object referred to by the returned *FileHandle*. All I/O on such a file is serialized across all threads using the returned handle. With either of these *CreateOptions*, the *DesiredAccess* SYNCHRONIZE flag must be set so that the I/O manager will use the file object as a synchronization object. With either of these *CreateOptions* set, the I/O manager maintains the "file position context" for the file object, an internal, current file position offset. This offset can be used in calls to **ZwReadFile** and **ZwWriteFile**. Its position also can be queried or set with **ZwQueryInformationFile** and **ZwSetInformationFile**.

If the *CreateOptions* FILE_OPEN_REPARSE_POINT flag is not specified and **IoCreateFile** attempts to open a file with a reparse point, normal reparse point processing occurs for the file. If, on the other hand, the FILE_OPEN_REPARSE_POINT flag is specified, normal reparse processing does not occur and **IoCreateFile** attempts to directly open the reparse point file. In either case, if the open operation was successful, **IoCreateFile** returns STATUS_SUCCESS; otherwise, the routine returns an NTSTATUS error code. **IoCreateFile** never returns STATUS_REPARSE.

The *CreateOptions* FILE_OPEN_REQUIRING_OPLOCK flag eliminates the time between when you open the file and request an oplock that could potentially enable a third party to open the file and get a sharing violation. An application can use the FILE_OPEN_REQUIRING_OPLOCK flag on **IoCreateFile** and then request any oplock. This ensures that an oplock owner will be notified of any later open request that causes a sharing violation.

In Windows 7, if other handles exist on the file when an application uses the FILE_OPEN_REQUIRING_OPLOCK flag, the create operation will fail with STATUS_OPLOCK_NOT_GRANTED. This restriction no longer exists starting with Windows 8.

If this create operation would break an oplock that already exists on the file, then setting the FILE_OPEN_REQUIRING_OPLOCK flag will cause the create operation to fail with STATUS_CANNOT_BREAK_OPLOCK. The existing oplock will not be broken by this create operation.

An application that uses the FILE_OPEN_REQUIRING_OPLOCK flag must request an oplock after this call succeeds, or all subsequent attempts to open the file will be blocked without the benefit of normal oplock processing. Similarly, if this call succeeds but the subsequent oplock request fails, an application that uses this flag must close its handle after it detects that the oplock request has failed.

>[!NOTE]
>The FILE_OPEN_REQUIRING_OPLOCK flag is available in Windows 7, Windows Server 2008 R2 and later versions of Windows. The Microsoft file systems that implement this flag in Windows 7 are NTFS, FAT, and exFAT.

The *CreateOptions* flag, FILE_RESERVE_OPFILTER, allows an application to request a level 1, batch, or filter oplock to prevent other applications from getting share violations. However, FILE_RESERVE_OPFILTER is only useful for filter oplocks. To use it, you must follow these steps:

1. Issue a create request with *CreateOptions* of FILE_RESERVE_OPFILTER, *DesiredAccess* of exactly FILE_READ_ATTRIBUTES, and *ShareAccess* of exactly FILE_SHARE_READ | FILE_SHARE_WRITE | FILE_SHARE_DELETE.
    * If there are already open handles, the create request fails with STATUS_OPLOCK_NOT_GRANTED, and the next requested oplock also fails.
    * If you open with more access or less sharing will also cause a failure of STATUS_OPLOCK_NOT_GRANTED.
2. If the create request succeeds, request an oplock.
3. Open another handle to the file to do I/O.

Step 3 makes this practical only for filter oplocks. The handle opened in step 3 can have a *DesiredAccess* that contains a maximum of FILE_READ_ATTRIBUTES | FILE_WRITE_ATTRIBUTES | FILE_READ_DATA | FILE_READ_EA | FILE_EXECUTE | SYNCHRONIZE | READ_CONTROL and still not break a filter oplock. However, any *DesiredAccess* greater than FILE_READ_ATTRIBUTES | FILE_WRITE_ATTRIBUTES | SYNCHRONIZE will break a level 1 or batch oplock and make the FILE_RESERVE_OPFILTER flag useless for those oplock types.

The *Options* IO_NO_PARAMETER_CHECKING flag can be useful if a driver is issuing a kernel-mode create request on behalf of an operation initiated by a user-mode application. Because the request occurs within a user-mode context, the I/O manager, by default, probes the supplied parameter values, which can cause an access violation if the parameters are kernel-mode addresses. This flag enables the caller to override this default behavior and avoid the access violation.

For create requests originating in user mode, if the driver sets both IO_NO_PARAMETER_CHECKING and IO_FORCE_ACCESS_CHECK in the *Options* parameter of **IoCreateFile** then it should also set OBJ_FORCE_ACCESS_CHECK in the *ObjectAttributes* parameter. For info on this flag, see the **Attributes** member of [OBJECT_ATTRIBUTES](https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfwdm/ns-wudfwdm-_object_attributes).

NTFS is the only Microsoft file system that implements FILE_RESERVE_OPFILTER.

Driver routines that run in a process context other than that of the system process must set the OBJ_KERNEL_HANDLE attribute for the *ObjectAttributes* parameter of **IoCreateFile**. This restricts the use of the handle returned by **IoCreateFile** to processes running only in kernel mode. Otherwise, the handle can be accessed by the process in whose context the driver is running. Drivers can call [**InitializeObjectAttributes**](https://docs.microsoft.com/windows/desktop/api/ntdef/nf-ntdef-initializeobjectattributes) to set the OBJ_KERNEL_HANDLE attribute as follows.

```cpp
InitializeObjectAttributes(&ObjectAttributes, NULL, OBJ_KERNEL_HANDLE, NULL, NULL);
```

## -see-also

[**ACCESS_MASK**](https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask)

[**InitializeObjectAttributes**](https://docs.microsoft.com/windows/desktop/api/ntdef/nf-ntdef-initializeobjectattributes)

[**IO_STATUS_BLOCK**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_status_block)

[**IoCreateFileEx**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iocreatefileex#desiredaccess)

[**OBJECT_ATTRIBUTES**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfwdm/ns-wudfwdm-_object_attributes)

[**ZwClose**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose)

[**ZwCreateFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile)

[**ZwQueryInformationFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntqueryinformationfile)

[**ZwReadFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntreadfile)

[**ZwSetInformationFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntsetinformationfile)

[**ZwWriteFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntwritefile)
