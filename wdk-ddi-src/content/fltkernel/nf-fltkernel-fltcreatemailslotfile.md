---
UID: NF:fltkernel.FltCreateMailslotFile
title: FltCreateMailslotFile function (fltkernel.h)
description: Minifilter drivers call FltCreateMailslotFile to create a new pipe or open an existing mailslot.
old-location: ifsk\fltcreatemailslotfile.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FltCreateMailslotFile function"]
ms.keywords: FltCreateMailslotFile, FltCreateMailslotFile function [Installable File System Drivers], fltkernel/FltCreateMailslotFile, ifsk.fltcreatemailslotfile
req.header: fltkernel.h
req.include-header: FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 8.
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
 - FltCreateMailslotFile
 - fltkernel/FltCreateMailslotFile
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Fltmgr.lib
 - Fltmgr.dll
api_name:
 - FltCreateMailslotFile
---

# FltCreateMailslotFile function

## -description

Minifilter drivers call **FltCreateMailslotFile** to create a new pipe or open an existing mailslot.

## -parameters

### -param Filter

[in] An opaque filter pointer for the caller.

### -param Instance

[in, optional] An opaque instance pointer for the minifilter driver instance that the create request is to be sent to. The instance must be attached to the volume for the mailslot file system. This parameter is optional and can be **NULL**. If this parameter is **NULL**, the request is sent to the device object at the top of the file system driver stack for the volume. If it is non-**NULL**, the request is sent only to minifilter driver instances that are attached below the specified instance.

### -param FileHandle

[out] A pointer to a caller-allocated variable that receives the file handle if the call to  **FltCreateMailslotFile** is successful.

### -param FileObject

[out, optional] A pointer to a caller-allocated variable that receives the file object pointer if the call to **FltCreateMailslotFile** is successful. This parameter is optional and can be **NULL**.

### -param DesiredAccess

[in] A bitmask of flags that specify the type of access that the caller requires to the file or directory. The set of system-defined **DesiredAccess** flags determines the following specific access rights for file objects.

| DesiredAccess Flag | Meaning |
| ------------------ | ------- |
| FILE_READ_DATA     | Data can be read from the named mailslot.|
| FILE_READ_ATTRIBUTES | **FileAttributes** flags can be read.  For additional information, see the table of valid flag values in the **FileAttributes** parameter of [**FltCreateFileEx2**](nf-fltkernel-fltcreatefileex2.md). |
| READ_CONTROL | The access control list [ACL](../wdm/ns-wdm-_acl.md) and ownership information associated with the mailslot can be read. |
| FILE_WRITE_DATA | Data can be written to the mailslot. |
| FILE_WRITE_ATTRIBUTES | **FileAttributes** flags can be written. |
| FILE_APPEND_DATA | Data can be appended to the mailslot. |
| WRITE_DAC | The discretionary access control list [DACL](../wdm/ns-wdm-_acl.md) associated with the mailslot can be written. |
| WRITE_OWNER | Ownership information associated with the mailslot can be written. |
| ACCESS_SYSTEM_SECURITY | The caller will have write access to the mailslot's SACL. |
| SYNCHRONIZE | The caller can synchronize the completion of an I/O operation by waiting for the returned **FileHandle** to be set to the Signaled state. This flag must be set if the **CreateOptions** FILE_SYNCHRONOUS_IO_ALERT or FILE_SYNCHRONOUS_IO_NONALERT flag is set. |

Alternatively, for any file object that does not represent a directory, you can specify one or more of the following generic [ACCESS_MASK](/windows-hardware/drivers/kernel/access-mask) flags. (The STANDARD_RIGHTS_*XXX* flags are predefined system values that are used to enforce security on system objects.) You can also combine these generic flags with additional flags from the preceding table.

| DesiredAccess to File Values | Maps to DesiredAccess Flags |
| ---------------------------- | --------------------------- |
| GENERIC_READ | STANDARD_RIGHTS_READ, FILE_READ_DATA, and SYNCHRONIZE. |
| GENERIC_WRITE | STANDARD_RIGHTS_WRITE, FILE_WRITE_DATA, FILE_APPEND_DATA, and SYNCHRONIZE. |

### -param ObjectAttributes

[in] Pointer to an opaque [OBJECT_ATTRIBUTES](/windows/win32/api/ntdef/ns-ntdef-_object_attributes) structure that is already initialized with [**InitializeObjectAttributes**](/windows/win32/api/ntdef/nf-ntdef-initializeobjectattributes). If the caller is running in the system process context, this parameter can be **NULL**. Otherwise, the caller must set the OBJ_KERNEL_HANDLE attribute in the call to **InitializeObjectAttributes**. Members of this structure for a file object are listed in the following table.

| Member | Value |
| ------ | ----- |
| **ULONG Length** | Number of bytes of data that are contained in the structure pointed to by **ObjectAttributes**. This value must be at least ```sizeof(OBJECT_ATTRIBUTES)```. |
| **PUNICODE_STRING ObjectName** | Pointer to a [**UNICODE_STRING**](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) structure that contains the name of the mailslot to be created or opened. This name must be a fully qualified file specification or the name of a device object unless it is the name of a file relative to the directory specified by **RootDirectory**. For example, "\Device\Mailslot\myslot" or "\??\mailslot\myslot" could both be valid file specifications. (Note: "\??" replaces "\DosDevices" as the name of the Win32 object namespace. "\DosDevices" still works, but "\??" is translated faster by the object manager. |
| **HANDLE RootDirectory** | Optional handle to a directory, obtained by a preceding call to [**FltCreateFileEx2**](nf-fltkernel-fltcreatefileex2.md). If this value is **NULL**, the **ObjectName** member must be a fully qualified file specification that includes the full path to the target mailslot. If this value is non-**NULL**, the **ObjectName** member specifies a mailslot name that is relative to this directory. |
| **PSECURITY_DESCRIPTOR SecurityDescriptor** | Optional [**SECURITY_DESCRIPTOR**](../ntifs/ns-ntifs-_security_descriptor.md) to be applied to a mailslot. [ACLs](../wdm/ns-wdm-_acl.md) specified by such a security descriptor are only applied to the mailslot when it is created. If the value is **NULL** when a mailslot is created, the ACL placed on the mailslot is dependant on the mailslot file system and may allow a client with any access to create an instance. |
| **ULONG Attributes** | A set of flags that controls the file object attributes. If the caller is running in the system process context, this parameter can be zero. Otherwise, the caller must set the OBJ_KERNEL_HANDLE flag. The caller can also optionally set the OBJ_CASE_INSENSITIVE flag, which indicates that name-lookup code should ignore the case of **ObjectName** rather than performing an exact-match search. |

### -param IoStatusBlock

[out] Pointer to an [**IO_STATUS_BLOCK**](../wdm/ns-wdm-_io_status_block.md) structure that receives the final completion status and information about the requested operation. On return from **FltCreateMailslotFile**, the **Information** member of the variable contains one of the following values:

* FILE_CREATED
* FILE_OPENED

### -param CreateOptions

[in] The options to be applied when creating or opening the mailslot, as a compatible combination of the following flags.

| Flags | Meaning |
| ----- | ------- |
| FILE_WRITE_THROUGH | System services, file systems, and drivers that write data to the mailslot must actually transfer the data into the mailslot before any requested write operation is considered complete. This flag is automatically set if the **CreateOptions** flag FILE_NO_INTERMEDIATE_BUFFERING is set. |
| FILE_SYNCHRONOUS_IO_ALERT | All operations on the mailslot are performed synchronously. Any wait on behalf of the caller is subject to premature termination from alerts. This flag also causes the I/O system to maintain the mailslot position context. If this flag is set, the **DesiredAccess** SYNCHRONIZE flag also must be set so that the I/O Manager uses the file object as a synchronization object. |
| FILE_SYNCHRONOUS_IO_NONALERT | All operations on the mailslot are performed synchronously. Waits in the system to synchronize I/O queuing and completion are not subject to alerts. This flag also causes the I/O system to maintain the file position context. If this flag is set, the **DesiredAccess** SYNCHRONIZE flag also must be set so that the I/O Manager uses the file object as a synchronization object. |

### -param MailslotQuota

[in] The size, in bytes, of the buffer for writes to the mailslot.

### -param MaximumMessageSize

[in] The maximum size, in bytes, of a message to write to the mailslot. A message of any size is specified by the value 0.

### -param ReadTimeout

[in] The time a read operation waits for a message to be available in the mailslot. The default timeout is expressed in 100-nanosecond increments as a negative integer. For example, 250 milliseconds is specified as ```–10*1000*250```. Additionally, the following values have special meanings.

| Value | Meaning |
| ----- | ------- |
| 0  | Returns immediately if no message is present. |
| -1 | Waits forever for a message. |

### -param DriverContext

[in, optional] Optional pointer to an [**IO_DRIVER_CREATE_CONTEXT**](../ntddk/ns-ntddk-_io_driver_create_context.md) structure already initialized by [**IoInitializeDriverCreateContext**](../ntddk/nf-ntddk-ioinitializedrivercreatecontext.md).

## -returns

**FltCreateMailslotFile** returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following.

| Return code | Description |
| ----------- | ----------- |
| STATUS_FLT_DELETING_OBJECT | The filter or instance specified in the **Filter** or **Instance** parameters is being torn down. This status code can be received if the open request crosses a volume mount point and the **Instance** parameter is non-**NULL**. This is an error code. |
| STATUS_OBJECT_PATH_SYNTAX_BAD | The **ObjectAttributes** parameter did not contain a **RootDirectory** member, but the **ObjectName** member in the OBJECT_ATTRIBUTES structure was an empty string or did not contain an OBJECT_NAME_PATH_SEPARATOR character. This error code indicates incorrect syntax for the object path. |

## -remarks

The **FltCreateMailslotFile** function allows minifilter drivers to create or open mailslot instances. This is useful for creating virtual mailslots or for creating a mailslot group that distributes to several other mailslots.

The **Instance** parameter is either **NULL** or is previously set by attaching to the mailslot volume. A volume pointer is obtained by passing "\Device\Mailslot" as the volume name to [**FltGetVolumeFromName**](nf-fltkernel-fltgetvolumefromname.md).

To specify an extra create parameter (ECP) as part of a create operation, initialize the **ExtraCreateParameter** member of the [**IO_DRIVER_CREATE_CONTEXT**](../ntddk/ns-ntddk-_io_driver_create_context.md) structure with the [**FltAllocateExtraCreateParameterList**](nf-fltkernel-fltallocateextracreateparameterlist.md) routine.  If ECPs are used, they must be allocated, initialized, and freed using their associated support routines.  Upon returning from the call of **FltCreateMailslotFile**, the ECP list is unchanged and may be passed to additional calls of **FltCreateMailslotFile** for other create operations.  The ECP list structure is not automatically deallocated. The caller of **FltCreateMailslotFile** must deallocate this structure by calling the [**FltFreeExtraCreateParameterList**](nf-fltkernel-fltfreeextracreateparameterlist.md) routine.

If **Instance** is not **NULL**, the create request from **FltCreateMailslotFile** is sent only to the instances attached below the specified minifilter driver instance and to the mailslot file system. The specified instance and the instances attached above it do not receive the create request. If no instance is specified, the request goes to the top of the stack and is received by all instances and the mailslot file system.

## -see-also

[**FltAllocateExtraCreateParameterList**](nf-fltkernel-fltallocateextracreateparameterlist.md)

[**FltFreeExtraCreateParameterList**](nf-fltkernel-fltfreeextracreateparameterlist.md)

[**IO_DRIVER_CREATE_CONTEXT**](../ntddk/ns-ntddk-_io_driver_create_context.md)

[**InitializeObjectAttributes**](/windows/win32/api/ntdef/nf-ntdef-initializeobjectattributes)

[**IoInitializeDriverCreateContext**](../ntddk/nf-ntddk-ioinitializedrivercreatecontext.md)
