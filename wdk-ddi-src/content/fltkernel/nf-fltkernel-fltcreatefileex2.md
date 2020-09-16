---
UID: NF:fltkernel.FltCreateFileEx2
title: FltCreateFileEx2 function (fltkernel.h)
description: Minifilter drivers call FltCreateFileEx2 to create a new file or open an existing file. This routine also includes an optional create context parameter.
old-location: ifsk\fltcreatefileex2.htm
tech.root: ifsk
ms.assetid: e662472d-4d72-449e-91d7-119bd59e0943
ms.date: 02/13/2020
keywords: ["FltCreateFileEx2 function"]
ms.keywords: FltApiRef_a_to_d_21436e16-822a-4250-abac-10346593435f.xml, FltCreateFileEx2, FltCreateFileEx2 routine [Installable File System Drivers], fltkernel/FltCreateFileEx2, ifsk.fltcreatefileex2
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
targetos: Windows
req.typenames: 
f1_keywords:
 - FltCreateFileEx2
 - fltkernel/FltCreateFileEx2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Fltmgr.lib
 - Fltmgr.sys
api_name:
 - FltCreateFileEx2
---

# FltCreateFileEx2 function


## -description

Minifilter drivers call **FltCreateFileEx2** to create a new file or open an existing file.  This routine includes an optional create context parameter.

## -parameters

### -param Filter 

[in]
An opaque filter pointer for the caller.

### -param Instance 

[in, optional]
An opaque instance pointer for the minifilter driver instance that the create request is to be sent to. The instance must be attached to the volume where the file or directory resides. This parameter is optional and can be **NULL**. If this parameter is **NULL**, the request is sent to the device object at the top of the file system driver stack for the volume. If this parameter is non-**NULL**, the request is sent only to minifilter driver instances that are attached below the specified instance.

### -param FileHandle 

[out]
A pointer to a caller-allocated variable that receives the file handle if the call to **FltCreateFileEx2** is successful.

### -param FileObject 

[out, optional]
A pointer to a caller-allocated variable that receives the file object pointer if the call to **FltCreateFileEx2** is successful. This parameter is optional and can be **NULL**.

### -param DesiredAccess 

[in]
A bitmask of flags specifying the type of access to the file or directory that the caller requires. See the *DesiredAccess* parameter of [**IoCreateFileEx**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iocreatefileex#desiredaccess) for more information about this parameter and for the list of flag values.

### -param ObjectAttributes 

[in]
Pointer to an opaque [**OBJECT_ATTRIBUTES**](https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-object_attributes) structure that is already initialized with [**InitializeObjectAttributes**](https://docs.microsoft.com/windows/desktop/api/ntdef/nf-ntdef-initializeobjectattributes). See the *ObjectAttributes* parameter of [**IoCreateFileEx**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iocreatefileex#objectattributes) for more information and for a description of each structure member.

### -param IoStatusBlock 

[out]
Pointer to an [**IO_STATUS_BLOCK**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_status_block) structure that receives the final completion status and information about the requested operation. See the **IoStatusBlock** parameter of [**IoCreateFileEx**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iocreatefileex#iostatusblock) for more information about this parameter.

### -param AllocationSize 

[in, optional]
Optionally specifies the initial allocation size, in bytes, for the file stream. A nonzero value has no effect unless the file is being created, overwritten, or superseded.

### -param FileAttributes 

[in]
Specifies one or more FILE_ATTRIBUTE_*XXX* flags, which represent the file attributes to set if you are creating, superseding, or overwriting a file. See the *FileAttributes* parameter of [**IoCreateFileEx**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iocreatefileex#fileattributes) for more details and for the list of flags.

### -param ShareAccess 

[in]
Specifies the type of share access to the file that the caller requires, as zero or one, or a combination of the flags. See the *ShareAccess* parameter of [**IoCreateFileEx**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iocreatefileex#shareaccess) for more details and for the list of flags.

### -param CreateDisposition 

[in]
Specifies a value that determines the action to be taken, depending on whether the file already exists. See the *Disposition* parameter of [**IoCreateFileEx**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iocreatefileex#disposition) for the list of possible values.

### -param CreateOptions 

[in]
Specifies the options to be applied when creating or opening the file. This parameter is a compatible combination of the flags listed and described in the *CreateOptions* parameter of [**IoCreateFileEx**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iocreatefileex#createoptions).

### -param EaBuffer 

[in, optional]
A pointer to a caller-supplied [**FILE_FULL_EA_INFORMATION**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_full_ea_information) buffer that contains extended attribute (EA) information to be applied to the file.

### -param EaLength 

[in]
Length, in bytes, of *EaBuffer*.

### -param Flags 

[in]
Specifies options to be used during the creation of the create request. See the *Options* parameter of [**IoCreateFileEx**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iocreatefileex#options) for the list of possible options.

### -param DriverContext 

[in, optional]
Optional pointer to an [**IO_DRIVER_CREATE_CONTEXT**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_io_driver_create_context) structure already initialized by [**IoInitializeDriverCreateContext**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-ioinitializedrivercreatecontext).

## -returns

**FltCreateFileEx2** returns STATUS_SUCCESS or an appropriate NTSTATUS value. See the **Return Value** section of [**IoCreateFileEx**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iocreatefileex#returns) for a list of possible return codes.

> [!NOTE]
> **FltCreateFileEx2** might return STATUS_FILE_LOCK_CONFLICT as the return value or in the **Status** member of the IO_STATUS_BLOCK structure that is pointed to by the IoStatusBlock parameter. This would occur only if the NTFS log file is full, and an error occurs while **FltCreateFileEx2** tries to handle this situation.

## -remarks

**FltCreateFileEx2** is similar to [**FltCreateFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatefile) and [**FltCreateFileEx**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatefileex), except that it supports the *DriverContext* input parameter.

To specify an extra create parameter (ECP) as part of a create operation, initialize the **ExtraCreateParameter** member of the IO_DRIVER_CREATE_CONTEXT structure with the [**FltAllocateExtraCreateParameterList**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocateextracreateparameterlist) routine.  If ECPs are used, they must be created, manipulated, and freed using the appropriate routines - the following *See Also* section lists these routines.  Upon returning from the call of **FltCreateFileEx2**, the ECP list is unchanged and may be passed to additional calls of **FltCreateFileEx2** for other create operations.  Note that the operating system does not automatically deallocate the ECP list structure - the caller of **FltCreateFileEx2** must deallocate this structure by calling the [**FltFreeExtraCreateParameterList**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfreeextracreateparameterlist) routine.

To create/open a file in the context of a transaction, set the **TxnParameters** member of the IO_DRIVER_CREATE_CONTEXT structure to the value returned by the [**IoGetTransactionParameterBlock**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iogettransactionparameterblock) routine.

**FltCreateFileEx2** sends the create request only to the instances attached below the specified minifilter driver instance and to the file system. The specified instance and the instances attached above it do not receive the create request. If no instance is specified, the request goes to the top of the stack and is received by all instances and the file system.

There are two alternate ways to specify the name of the file to be created or opened with **FltCreateFileEx2**:

* As a fully qualified pathname, supplied in the **ObjectName** member of the input *ObjectAttributes*.

* As a pathname that is relative to the directory file represented by the handle in the **RootDirectory** member of the input *ObjectAttributes*.

Any *FileHandle* that is obtained from **FltCreateFileEx2** must eventually be released by calling [**FltClose**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltclose). In addition, any returned *FileObject* pointer must be dereferenced when it is no longer needed by calling [**ObDereferenceObject**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobject).

Driver routines that do not run in the system process context must set the OBJ_KERNEL_HANDLE attribute for the *ObjectAttributes* parameter of **FltCreateFileEx2**. Setting this attribute restricts the use of the handle that is returned by **FltCreateFileEx2** to processes running in kernel mode. Otherwise, the handle can be accessed by the process in whose context the driver is running.

> [!NOTE]
> Do not call this routine with a non-NULL top level IRP value, as this can cause a system deadlock.

Certain *DesiredAccess* flags and combinations of flags have the following effects:

* For a caller to synchronize an I/O completion by waiting for the returned *FileHandle* to be set to the Signaled state, the SYNCHRONIZE flag must be set.

* If only the FILE_APPEND_DATA and SYNCHRONIZE flags are set, the caller can write only to the end of the file, and any offset information about write requests to the file is ignored. However, the file is automatically extended as necessary for this type of write operation.

* Setting the FILE_WRITE_DATA flag for a file also allows write requests beyond the end of the file to occur. The file is automatically extended for this type of write request, as well.

* If only the FILE_EXECUTE and SYNCHRONIZE flags are set, the caller cannot use the handle returned in the *FileHandle* parameter to directly read or write any data to or from the file. That is, all operations on the file must use system paging I/O to read or write file data.

The *ShareAccess* parameter determines whether separate threads can access the same file, possibly simultaneously. If both file openers have the privilege to access a file in the specified manner, the file can be successfully opened and shared. If the original caller of **FltCreateFileEx2** does not specify FILE_SHARE_READ, FILE_SHARE_WRITE, or FILE_SHARE_DELETE, no other open operations can be performed on the file because the original caller is given exclusive access to the file.

For a shared file to be successfully opened, the requested *DesiredAccess* to the file must be compatible with both the *DesiredAccess* and *ShareAccess* specifications of all preceding open requests that have not yet been released with [**FltClose**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltclose). That is, the *DesiredAccess* parameter that is specified to **FltCreateFileEx2** for a given file must not conflict with the accesses that other openers of the file have disallowed.

> [!NOTE]
> If IO_IGNORE_SHARE_ACCESS_CHECK is specified in the *Flags* parameter, the I/O manager ignores the *ShareAccess* parameter. However, the file system might still perform access checks. Thus, it is important to specify the sharing mode you would like for the *ShareAccess*parameter, even when using the IO_IGNORE_SHARE_ACCESS_CHECK flag. Additionally, note that when IO_IGNORE_SHARE_ACCESS_CHECK is specified, the file system does not track the current open's desired access or shared access. Because of this, subsequent open calls on the same file may succeed.

The *CreateDisposition* value FILE_SUPERSEDE requires that the caller have DELETE access to an existing file object. If so, a successful call to **FltCreateFileEx2** with FILE_SUPERSEDE on an existing file effectively deletes that file and then recreates it. This implies that if the file has already been opened by another thread, it opened the file by specifying a *ShareAccess*parameter with the FILE_SHARE_DELETE flag set. Note that this type of disposition is consistent with the POSIX style of overwriting files.

The *CreateDisposition* values FILE_OVERWRITE_IF and FILE_SUPERSEDE are similar. If **FltCreateFileEx2** is called with an existing file and either of these *CreateDisposition* values, the file is replaced.

Overwriting a file is semantically equivalent to a supersede operation, except for the following:

* The caller must have write access to the file, rather than delete access. This implies that, if the file has already been opened by another thread, it opened the file with the FILE_SHARE_WRITE flag set in the input *ShareAccess* parameter.

* The specified file attributes are combined with those attributes that are already applied to the file by using a bitwise OR operation. This implies that if the file has already been opened by another thread, a subsequent caller of **FltCreateFileEx2** cannot disable existing *FileAttributes* flags but can enable additional flags for the same file. Note that this style of overwriting files is consistent with MS-DOS, Windows 3.1, and OS/2.

The *CreateOptions* FILE_DIRECTORY_FILE value specifies that the file to be created or opened is a directory file. When a directory file is created, the file system creates an appropriate structure on the disk to represent an empty directory for that particular file system's on-disk structure. If this option was specified and the given file to be opened is not a directory file or if the caller specified an inconsistent *CreateOptions* or *CreateDisposition* value, the call to **FltCreateFileEx2** fails.

The *CreateOptions* FILE_NO_INTERMEDIATE_BUFFERING flag prevents the file system from performing any intermediate buffering on behalf of the caller. Specifying this value places certain restrictions on the caller's parameters to other **Flt..File** routines or **Zw..File** routines, including the following:

* Any byte offset value passed to the *ByteOffset* parameter of [**FltReadFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreadfile), [**ZwReadFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntreadfile), [**FltWriteFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltwritefile), or [**ZwWriteFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntwritefile) must be a multiple of the sector size.

* The *Length* parameter passed to [**FltReadFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreadfile), [**ZwReadFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntreadfile), [**FltWriteFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltwritefile), or [**ZwWriteFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntwritefile) must be a multiple of the sector size. Note that specifying a read operation to a buffer whose length is exactly the sector size might result in fewer significant bytes being transferred to that buffer if the end of the file was reached during the transfer.

* Buffers must be aligned in accordance with the alignment requirement of the underlying storage device. This information can be obtained by calling **FltCreateFileEx2** to get a handle for the file object that represents the physical device and then calling [**ZwQueryInformationFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntqueryinformationfile) with that handle, specifying **FileAlignmentInformation** as the value for *FileInformationClass* parameter. For more information about the system FILE_*XXX*_ALIGNMENT values, which are defined in *Ntifs.h*, see [**DEVICE_OBJECT**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object) and [**Initializing a Device Object**](https://docs.microsoft.com/windows-hardware/drivers/kernel/initializing-a-device-object).

* Calls to [**FltSetInformationFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetinformationfile) or [**ZwSetInformationFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntsetinformationfile) with the *FileInformationClass* parameter set to **FilePositionInformation** must specify an offset that is a multiple of the sector size.

The *CreateOptions* FILE_SYNCHRONOUS_IO_ALERT and FILE_SYNCHRONOUS_IO_NONALERT flags, which are mutually exclusive as their names suggest, specify that the file is being opened for synchronous I/O. This means that all I/O operations on the file are to be synchronous as long as they occur through the file object that the returned *FileHandle* refers to. All I/O on such a file is serialized across all threads by using the returned handle. With either of these *CreateOptions* flags set, the I/O Manager maintains the current file position offset in the file object's **CurrentByteOffset** field. This offset can be used in calls to [**ZwReadFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntreadfile) and [**ZwWriteFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntwritefile). It can also be queried or set by calling [**ZwQueryInformationFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntqueryinformationfile) or [**ZwSetInformationFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntsetinformationfile).

If the *CreateOptions* FILE_OPEN_REPARSE_POINT flag is *not* specified and **FltCreateFileEx2** attempts to open a file with a reparse point, normal reparse point processing occurs for the file.  If, on the other hand, the FILE_OPEN_REPARSE_POINT flag is specified, normal reparse processing does *not* occur and **FltCreateFileEx2** attempts to directly open the reparse point file.  In either case, if the open operation was successful, **FltCreateFileEx2** returns STATUS_SUCCESS; otherwise, the routine returns an NTSTATUS error code. **FltCreateFileEx2** never returns STATUS_REPARSE.

The *CreateOptions* FILE_OPEN_REQUIRING_OPLOCK flag eliminates the time between when you open the file and request an oplock that could potentially enable a third party to open the file and get a sharing violation. An application can use the FILE_OPEN_REQUIRING_OPLOCK flag on **FltCreateFileEx2** and then request any oplock. This ensures that an oplock owner will be notified of any later open request that causes a sharing violation.

In Windows 7, if other handles exist on the file when an application uses the FILE_OPEN_REQUIRING_OPLOCK flag, the create operation will fail with STATUS_OPLOCK_NOT_GRANTED. This restriction no longer exists starting with Windows 8.

If this create operation would break an oplock that already exists on the file, then setting the FILE_OPEN_REQUIRING_OPLOCK flag will cause the create operation to fail with STATUS_CANNOT_BREAK_OPLOCK. The existing oplock will not be broken by this create operation.

 An application that uses this flag must request an oplock after this call succeeds, or all later attempts to open the file will be blocked without the benefit of typical oplock processing. Similarly, if this call succeeds but the later oplock request fails, an application that uses this flag must close its handle after it detects that the oplock request has failed.

> [!NOTE]
> The FILE_OPEN_REQUIRING_OPLOCK flag is available in Windows 7, Windows Server 2008 R2 and later Windows operating systems. The Microsoft file systems that implement this flag in Windows 7 are NTFS, FAT, and exFAT.

The *CreateOptions* flag FILE_RESERVE_OPFILTER allows an application to request a level 1, batch, or filter oplock to prevent other applications from getting share violations. However, FILE_RESERVE_OPFILTER is only practically useful for filter oplocks. To use it, you must complete the following steps:

1. Issue a create request with *CreateOptions* of FILE_RESERVE_OPFILTER, *DesiredAccess* of exactly FILE_READ_ATTRIBUTES, and *ShareAccess* of exactly FILE_SHARE_READ | FILE_SHARE_WRITE | FILE_SHARE_DELETE.
   * If there are already open handles, the create request fails with STATUS_OPLOCK_NOT_GRANTED, and the next requested oplock also fails.
   * If you open with more access or less sharing will also cause a failure of STATUS_OPLOCK_NOT_GRANTED.

2. If the create request succeeds, request an oplock.

3. Open another handle to the file to do I/O.  

Step three makes this practical only for filter oplocks. The handle opened in step 3 can have a DesiredAccess that contains a maximum of FILE_READ_ATTRIBUTES | FILE_WRITE_ATTRIBUTES | FILE_READ_DATA | FILE_READ_EA | FILE_EXECUTE | SYNCHRONIZE | READ_CONTROL and still not break a filter oplock. However, any DesiredAccess greater than FILE_READ_ATTRIBUTES | FILE_WRITE_ATTRIBUTES | SYNCHRONIZE will break a level 1 or batch oplock and make the FILE_RESERVE_OPFILTER flag useless for those oplock types.

NTFS is the only Microsoft file system that implements FILE_RESERVE_OPFILTER.

Minifilter drivers must use [**FltSetInformationFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetinformationfile), not [**ZwSetInformationFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntsetinformationfile), to rename a file.

> [!NOTE]
> If you try to open a volume but only specify a combination of the following flags for the *DesiredAccess* parameter, **FltCreateFileEx2** will open a handle, independent of the file system, that has direct access to the storage device for the volume.
>
> * FILE_READ_ATTRIBUTES
> * READ_CONTROL
> * WRITE_DAC
> * WRITE_OWNER
> * SYNCHRONIZE
>
> You must not use **FltCreateFileEx2** to open a handle with direct access to the storage device for the volume or you will leak system resources. If you want to open a handle with direct access to a storage device, call the [**IoCreateFileEx**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iocreatefileex), [**IoCreateFileSpecifyDeviceObjectHint**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iocreatefilespecifydeviceobjecthint), or [**ZwCreateFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile) function instead.

When a caller of **FltCreateFileEx2** wishes to enable reparsing for a volume target, a [**FLT_CREATEFILE_TARGET_ECP_CONTEXT**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_createfile_target_ecp_context) can be included as an ECP to the ECP list in the *DriverContext* parameter.  If this ECP is present, **FltCreateFileEx2** will adjust the target device for the create operation and attempt for find a filtered instance  of a volume appropriate for the given file information. Use of this ECP is available starting with Windows 8.

## -see-also

[**ACCESS_MASK**](https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask)

[**ACL**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_acl)

[**DEVICE_OBJECT**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object)

[**FILE_FULL_EA_INFORMATION**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_full_ea_information)

[**FltAcknowledgeEcp**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltacknowledgeecp)

[**FltAllocateExtraCreateParameter**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocateextracreateparameter)

[**FltAllocateExtraCreateParameterList**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocateextracreateparameterlist)

[**FltClose**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltclose)

[**FltFindExtraCreateParameter**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfindextracreateparameter)

[**FltFreeExtraCreateParameter**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfreeextracreateparameter)

[**FltFreeExtraCreateParameterList**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfreeextracreateparameterlist)

[**FltGetEcpListFromCallbackData**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetecplistfromcallbackdata)

[**FltGetNextExtraCreateParameter**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetnextextracreateparameter)

[**FltInsertExtraCreateParameter**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltinsertextracreateparameter)

[**FltIsEcpAcknowledged**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltisecpacknowledged)

[**FltIsEcpFromUserMode**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltisecpfromusermode)

[**FltQueryInformationFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltqueryinformationfile)

[**FltReadFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreadfile)

[**FltRemoveExtraCreateParameter**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltremoveextracreateparameter)

[**FltSetEcpListIntoCallbackData**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetecplistintocallbackdata)

[**FltSetInformationFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetinformationfile)

[**FltWriteFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltwritefile)

[**IO_DRIVER_CREATE_CONTEXT**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_io_driver_create_context)

[**InitializeObjectAttributes**](https://docs.microsoft.com/windows/desktop/api/ntdef/nf-ntdef-initializeobjectattributes)

[**IoCreateFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocreatefile)

[**IoCreateFileSpecifyDeviceObjectHint**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iocreatefilespecifydeviceobjecthint)

[**IoInitializeDriverCreateContext**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-ioinitializedrivercreatecontext)

[**ObDereferenceObject**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobject)

[**SECURITY_DESCRIPTOR**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor)

[**UNICODE_STRING**](https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_unicode_string)

[**ZwCreateFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile)

[**ZwQueryInformationFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntqueryinformationfile)

[**ZwReadFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntreadfile)

[**ZwSetInformationFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntsetinformationfile)

[**ZwWriteFile**](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntwritefile)

