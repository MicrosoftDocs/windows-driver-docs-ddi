---
UID: NS:wdm._FILE_OBJECT
title: FILE_OBJECT (wdm.h)
description: The FILE_OBJECT structure is used by the system to represent a file object.
tech.root: kernel
ms.date: 12/15/2022
keywords: ["FILE_OBJECT structure"]
ms.keywords: "*PFILE_OBJECT, *PLOG_FILE_OBJECT, FILE_OBJECT, FILE_OBJECT structure [Kernel-Mode Driver Architecture], LOG_FILE_OBJECT, LOG_FILE_OBJECT structure [Kernel-Mode Driver Architecture], PFILE_OBJECT, PFILE_OBJECT structure pointer [Kernel-Mode Driver Architecture], _FILE_OBJECT, kernel.file_object, kstruct_b_513d4c8b-8e8d-402f-836d-18e00767bd29.xml, wdm/FILE_OBJECT, wdm/LOG_FILE_OBJECT, wdm/PFILE_OBJECT"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: FILE_OBJECT, *PFILE_OBJECT
f1_keywords:
 - _FILE_OBJECT
 - wdm/_FILE_OBJECT
 - PFILE_OBJECT
 - wdm/PFILE_OBJECT
 - FILE_OBJECT
 - wdm/FILE_OBJECT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - _FILE_OBJECT
 - PFILE_OBJECT
 - FILE_OBJECT
---

## -description

The **FILE_OBJECT** structure is used by the system to represent a file object. To user-mode protected subsystems, a file object represents an open instance of a file, device, directory, or volume. To device and intermediate drivers, a file object usually represents a device object. To drivers in the file system stack, a file object usually represents a directory or file.

A file object is partially opaque. Certain types of drivers, such as file system drivers and network transport drivers, use some of the fields of file objects.

## -struct-fields

### -field Type

A read-only member used by the system to indicate that the object is a file object. If the object is a file object, the value of this member is 5.

### -field Size

A read-only member that specifies the size, in bytes, of the file object. This size does not include the file object extension, if one is present.

### -field DeviceObject

A pointer to the device object on which the file is opened.

### -field Vpb

A pointer to the volume parameter block associated with the file object.

Note that if the **Vpb** member is non-**NULL**, the file resides on a mounted volume.

### -field FsContext

A pointer to whatever optional state a driver maintains about the file object; otherwise, **NULL**. For file system drivers, this member must point to a [**FSRTL_ADVANCED_FCB_HEADER**](/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_fsrtl_advanced_fcb_header) header structure that is contained within a file-system-specific structure; otherwise system instability can result. Usually, this header structure is embedded in a file control block (FCB). However, on some file systems that support multiple data streams, such as NTFS, this header structure is a stream control block (SCB).

In a WDM device stack, only the functional device object (FDO) can use the two context pointers. File system drivers share this member across multiple opens to the same data stream.

### -field FsContext2

A pointer to whatever additional state a driver maintains about the file object; otherwise, **NULL**.

This member is opaque for drivers in the file system stack because the underlying file system utilizes this member.

### -field SectionObjectPointer

A pointer to the file object's read-only section object. This member is set only by file systems and used for Cache Manager interaction.

### -field PrivateCacheMap

An opaque member, set only by file systems, that points to handle-specific information and that is used for Cache Manager interaction.

### -field FinalStatus

A read-only member that is used, in certain synchronous cases, to indicate the final status of the file object's I/O request.

### -field RelatedFileObject

A pointer to a **FILE_OBJECT** structure used to indicate that the current file object has been opened relative to an already open file object. The file object pointed to by this member is usually a directory (meaning the current file has been opened relative to this directory). However, a file can be reopened relative to itself, and alternate data streams for a file can be opened relative to an already open primary data stream for that same file. The **RelatedFileObject** member is only valid during the processing of the [IRP_MJ_CREATE](/windows-hardware/drivers/ifs/irp-mj-create) requests.

### -field LockOperation

A read-only member. If **FALSE**, a lock operation (**NtLockFile**) has never been performed on the file object. If **TRUE**, at least one lock operation has been performed on the file object. Once set to **TRUE**, this member always remains **TRUE** (for example, releasing file locks on the file object does not reset this member to **FALSE**).

### -field DeletePending

A read-only member. If **TRUE**, a delete operation for the file associated with the file object exists. If **FALSE**, there currently is no pending delete operation for the file object.

### -field ReadAccess

A read-only member. If **TRUE**, the file associated with the file object has been opened for read access. If **FALSE**, the file has been opened without read access. This information is used when checking and/or setting the share access of the file.

### -field WriteAccess

A read-only member. If **TRUE**, the file associated with the file object has been opened for write access. If **FALSE**, the file has been opened without write access. This information is used when checking and/or setting the share access of the file.

### -field DeleteAccess

A read-only member. If **TRUE**, the file associated with the file object has been opened for delete access. If **FALSE**, the file has been opened without delete access. This information is used when checking and/or setting the share access of the file.

### -field SharedRead

A read-only member. If **TRUE**, the file associated with the file object has been opened for read sharing access. If **FALSE**, the file has been opened without read sharing access. This information is used when checking and/or setting the share access of the file.

### -field SharedWrite

A read-only member. If **TRUE**, the file associated with the file object has been opened for write sharing access. If **FALSE**, the file has been opened without write sharing access. This information is used when checking and/or setting the share access of the file.

### -field SharedDelete

A read-only member. If **TRUE**, the file associated with the file object has been opened for delete sharing access. If **FALSE**, the file has been opened without delete sharing access. This information is used when checking and/or setting the share access of the file.

### -field Flags

A read-only member used by the system to hold one or more (a bitwise inclusive OR combination) of the following private flag values.

| Flag | Meaning |
|---|---|
| **FO_FILE_OPEN** | Deprecated. |
| **FO_SYNCHRONOUS_IO** | The file object is opened for synchronous I/O. |
| **FO_ALERTABLE_IO** | Any wait in the I/O manager, as a result of a request made to this file object, is alertable. |
| **FO_NO_INTERMEDIATE_BUFFERING** | The file associated with the file object cannot be cached or buffered in a driver's internal buffers. |
| **FO_WRITE_THROUGH** | System services, file system drivers, and drivers that write data to the file must transfer the data into the file before any requested write operation is considered complete. |
| **FO_SEQUENTIAL_ONLY** | The file associated with the file object was opened for sequential I/O operations only. |
| **FO_CACHE_SUPPORTED** | The file associated with the file object is cacheable. This flag should be set only by a file system driver, and only if the **FsContext** member points to a valid [**FSRTL_ADVANCED_FCB_HEADER**](/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_fsrtl_advanced_fcb_header) structure. |
| **FO_NAMED_PIPE** | The file object represents a named pipe. |
| **FO_STREAM_FILE** | The file object represents a file stream. |
| **FO_MAILSLOT** | The file object represents a mailslot. |
| **FO_GENERATE_AUDIT_ON_CLOSE** | Deprecated. |
| **FO_QUEUE_IRP_TO_THREAD** | IRPs will not be queued to this file object. |
| **FO_DIRECT_DEVICE_OPEN** | The device targeted by this file object was opened directly. |
| **FO_FILE_MODIFIED** | The file associated with the file object has been modified. |
| **FO_FILE_SIZE_CHANGED** | The file associated with the file object has changed in size. |
| **FO_CLEANUP_COMPLETE** | The file system has completed its cleanup for this file object. |
| **FO_TEMPORARY_FILE** | The file associated with the file object is a temporary file. |
| **FO_DELETE_ON_CLOSE** | The file associated with the file object will be deleted by the file system upon close. |
| **FO_OPENED_CASE_SENSITIVE** | The file name case of the file associated with the file object is respected. |
| **FO_HANDLE_CREATED** | A file handle was created for file object. |
| **FO_FILE_FAST_IO_READ** | A fast I/O read was performed on this file object. |
| **FO_RANDOM_ACCESS** | The file associated with the file object was opened for random access. |
| **FO_FILE_OPEN_CANCELLED** | The create request for this file object was canceled before completing. |
| **FO_VOLUME_OPEN** | The file object represents a volume open request. |
| **FO_REMOTE_ORIGIN** | The create request for the file associated with the file object originated on a remote machine. |
| **FO_SKIP_COMPLETION_PORT** | For a file object associated with a port, determines if the system should skip queuing to the completion port when the IRP is completed synchronously with a non-error status return value. |
| **FO_SKIP_SET_EVENT** | Skip setting the event for the file object upon IRP completion. |
| **FO_SKIP_SET_FAST_IO** | Skip setting an event supplied to a system service when the fast I/O path is successful. |

### -field FileName

A [**UNICODE_STRING**](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) structure whose **Buffer** member points to a read-only Unicode string that holds the name of the file opened on the volume. If the volume is being opened, the **Length** member of the **UNICODE_STRING** structure will be zero. Note that the file name in this string is valid only during the initial processing of an [IRP_MJ_CREATE](/windows-hardware/drivers/ifs/irp-mj-create) request. This file name should not be considered valid after the file system starts to process the **IRP_MJ_CREATE** request. The storage for the string pointed to by the **Buffer** member of the **UNICODE_STRING** structure is allocated in paged system memory. For more information about obtaining a file name, see [FltGetFileNameInformation](/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetfilenameinformation).

### -field CurrentByteOffset

A read-only member that specifies the file offset, in bytes, associated with the file object.

### -field Waiters

A read-only member used by the system to count the number of outstanding waiters on a file object opened for synchronous access.

### -field Busy

A read-only member used by the system to indicate whether a file object opened for synchronous access is currently busy.

### -field LastLock

An opaque pointer to the last lock applied to the file object.

### -field Lock

An opaque member used by the system to hold a file object event lock. The event lock is used to control synchronous access to the file object. Applicable only to file objects that are opened for synchronous access.

### -field Event

An opaque member used by the system to hold an event object for the file object. The event object is used to signal the completion of an I/O request on the file object if no user event was supplied or a synchronous API was called.

### -field CompletionContext

An opaque pointer to completion port information (port pointer and key) associated with the file object, if any.

### -field IrpListLock

An opaque pointer to a [KSPIN_LOCK](/windows-hardware/drivers/kernel/introduction-to-spin-locks) structure that serves as the spin lock used to synchronize access to the file object's IRP list.

### -field IrpList

An opaque pointer to the head of the IRP list associated with the file object.

### -field FileObjectExtension

An opaque pointer to the file object's file object extension ([FOBX](/windows-hardware/drivers/ifs/the-fobx-structure)) structure. The **FOBX** structure contains various opaque contexts used internally as well as the per-file object contexts available through **FsRtl*Xxx*** routines.

## -remarks

Drivers can use the **FsContext** and **FsContext2** members to maintain driver-determined state about an open file object. A driver cannot use these members unless the file object is accessible in the driver's I/O stack location of an IRP.

All remaining members in a file object are either opaque or read-only:

- Opaque members within a file object should be considered inaccessible. Drivers with dependencies on object field locations or access to opaque members might not remain portable and interoperable with other drivers over time.

- Drivers can use read-only members to acquire relevant information but must not modify read-only members and, if a pointer, the object that the member points to.

During the processing of an [IRP_MJ_CREATE](/windows-hardware/drivers/ifs/irp-mj-create) request, a file system driver calls the [IoSetShareAccess](/windows-hardware/drivers/ddi/wdm/nf-wdm-iosetshareaccess) routine (if the client is the first to open the file) or the [IoCheckShareAccess](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocheckshareaccess) routine (for subsequent clients that want to share the file). **IoSetShareAccess** and **IoCheckShareAccess** update the **ReadAccess**, **WriteAccess**, and **DeleteAccess** members to indicate the access rights that are granted to the client if the client has exclusive access to the file. Additionally, **IoCheckShareAccess** updates the **SharedRead**, **SharedWrite**, and **SharedDelete** members to indicate the access rights that are simultaneously granted to two or more clients that share the file. If the driver for a device other than a file system has to monitor the access rights of clients, this driver typically stores access rights information in context buffers that are pointed to by the **FsContext** and **FsContext2** members.

The type of object (for example, a file, directory, or volume) that a given file object represents cannot be determined by only examining the contents of the file object structure. For information about how to determine the type of object that a file object represents, see [ZwQueryInformationFile](/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntqueryinformationfile).

The Common Log File System (CLFS) uses the **LOG_FILE_OBJECT** structure to represent logs. The [ClfsCreateLogFile](/windows-hardware/drivers/ddi/wdm/nf-wdm-clfscreatelogfile) function returns a pointer to a **LOG_FILE_OBJECT** structure, which clients then pass to other CLFS functions.

CLFS clients do not directly access the members of a **LOG_FILE_OBJECT** structure.

```cpp
typedef FILE_OBJECT LOG_FILE_OBJECT, *PLOG_FILE_OBJECT, **PPLOG_FILE_OBJECT;
```

## -see-also

[**DEVICE_OBJECT**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object)

[FOBX](/windows-hardware/drivers/ifs/the-fobx-structure)

[**FSRTL_ADVANCED_FCB_HEADER**](/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_fsrtl_advanced_fcb_header)

[IRP_MJ_CREATE](/windows-hardware/drivers/ifs/irp-mj-create)

[IoCheckShareAccess](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocheckshareaccess)

[IoGetDeviceObjectPointer](/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdeviceobjectpointer)

[IoSetShareAccess](/windows-hardware/drivers/ddi/wdm/nf-wdm-iosetshareaccess)

[ObDereferenceObject](/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobject)

[ZwQueryInformationFile](/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntqueryinformationfile)
