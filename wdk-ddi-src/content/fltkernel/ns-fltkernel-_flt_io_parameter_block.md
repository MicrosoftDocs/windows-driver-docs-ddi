---
UID: NS:fltkernel._FLT_IO_PARAMETER_BLOCK
title: FLT_IO_PARAMETER_BLOCK (fltkernel.h)
description: The FLT_IO_PARAMETER_BLOCK structure contains the parameters for the I/O operation that is represented by a callback data (FLT_CALLBACK_DATA) structure.
old-location: ifsk\flt_io_parameter_block.htm
tech.root: ifsk
ms.assetid: a62f6db3-baca-492a-b485-062fcc69f563
ms.date: 07/27/2020
keywords: ["FLT_IO_PARAMETER_BLOCK structure"]
ms.keywords: "*PFLT_IO_PARAMETER_BLOCK, FLT_IO_PARAMETER_BLOCK, FLT_IO_PARAMETER_BLOCK structure [Installable File System Drivers], FltSystemStructures_8abf39e5-b9d1-4c44-8137-80ee1b35c0a3.xml, PFLT_IO_PARAMETER_BLOCK, PFLT_IO_PARAMETER_BLOCK structure pointer [Installable File System Drivers], _FLT_IO_PARAMETER_BLOCK, fltkernel/FLT_IO_PARAMETER_BLOCK, fltkernel/PFLT_IO_PARAMETER_BLOCK, ifsk.flt_io_parameter_block"
req.header: fltkernel.h
req.include-header: Fltkernel.h
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
req.typenames: FLT_IO_PARAMETER_BLOCK, *PFLT_IO_PARAMETER_BLOCK
f1_keywords:
 - _FLT_IO_PARAMETER_BLOCK
 - fltkernel/_FLT_IO_PARAMETER_BLOCK
 - PFLT_IO_PARAMETER_BLOCK
 - fltkernel/PFLT_IO_PARAMETER_BLOCK
 - FLT_IO_PARAMETER_BLOCK
 - fltkernel/FLT_IO_PARAMETER_BLOCK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - fltkernel.h
api_name:
 - FLT_IO_PARAMETER_BLOCK
---

# _FLT_IO_PARAMETER_BLOCK structure


## -description

The FLT_IO_PARAMETER_BLOCK structure contains the parameters for the I/O operation that is represented by a callback data ([**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data)) structure.

## -struct-fields

### -field IrpFlags

A bitmask of flags that specify various aspects of the I/O operation. These flags are used only for IRP-based operations. The following table shows flag values.

| Value | Meaning |
| ----- | ------- |
| IRP_BUFFERED_IO            |  The operation is a buffered I/O operation. |
| IRP_CLOSE_OPERATION        |  The operation is a cleanup or close operation. |
| IRP_DEALLOCATE_BUFFER      |  The I/O Manager will free the buffer during the completion phase for the IRP. |
| IRP_INPUT_OPERATION        |  The operation is an input operation. |
| IRP_NOCACHE                |  The operation is a noncached I/O operation. |
| IRP_PAGING_IO              |  The operation is a paging I/O operation. |
| IRP_SYNCHRONOUS_API        | The I/O operation is synchronous. |
| IRP_SYNCHRONOUS_PAGING_IO  | The operation is a synchronous paging I/O operation. |
| IRP_MOUNT_COMPLETION       | A volume mount is completed for the operation. |
| IRP_CREATE_OPERATION       | The operation is a create or open operation. |
| IRP_READ_OPERATION         | The I/O operation is for reading. |
| IRP_WRITE_OPERATION        | The I/O operation is for writing. |
| IRP_DEFER_IO_COMPLETION    | I/O completion of the operation is deferred. |
| IRP_ASSOCIATED_IRP         | The operation is associated with a master IRP. |
| IRP_OB_QUERY_NAME          | The operation is an asynchronous name query. |
| IRP_HOLD_DEVICE_QUEUE      | Reserved. |
| IRP_UM_DRIVER_INITIATED_IO | The operation originated from a user-mode driver. |

### -field MajorFunction

The major function code for the I/O operation. Major function codes are used for IRP-based operations, fast I/O operations, and file system (FSFilter) callback operations. For more information about additional operations, see [**FLT_PARAMETERS**](ns-fltkernel-_flt_parameters.md).

### -field MinorFunction

The minor function code for the I/O operation. This member is optional and can be **NULL**. The value of the **MajorFunction** member determines the possible values. For more information about minor function codes, see [**FLT_PARAMETERS**](ns-fltkernel-_flt_parameters.md).

### -field OperationFlags

A bitmask of flags that specify various aspects of the I/O operation. These flags are used only for IRP-based operations. The Filter Manager copies these flags from the  **Flags** member of the [**IO_STACK_LOCATION**](../wdm/ns-wdm-_io_stack_location.md) structure that is associated with the [**IRP**](../wdm/ns-wdm-_irp.md). The following table shows the most commonly used flag values.

| Value | Meaning |
| ----- | ------- |
| SL_CASE_SENSITIVE    | Used for [**IRP_MJ_CREATE**](/windows-hardware/drivers/ifs/irp-mj-create). If this flag is set, file name comparisons should be case-sensitive. |
| SL_EXCLUSIVE_LOCK    | Used for [**IRP_MJ_LOCK_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-lock-control). If this flag is set, an exclusive byte-range lock is requested. Otherwise, a shared lock is requested. |
| SL_FAIL_IMMEDIATELY  | Used for [**IRP_MJ_LOCK_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-lock-control). If this flag is set, the lock request should fail if it cannot be granted immediately. |
| SL_FORCE_ACCESS_CHECK  | Used for [**IRP_MJ_CREATE**](/windows-hardware/drivers/ifs/irp-mj-create). If this flag is set, access checks must be performed even if the value of the IRP's **RequestorMode** member is **KernelMode**. |
| SL_FORCE_DIRECT_WRITE  | Used for IRP_MJ_WRITE and IOCTL_DISK_COPY_DATA. If this flag is set, kernel-mode drivers can write to volume areas that they are normally blocked from writing to due to security reasons. This flag is checked both at the file system layer and storage stack layer. For more information about this flag, see [Blocking Direct Write Operations to Volumes and Disks](../index.yml). The SL_FORCE_DIRECT_WRITE flag is available in Windows Vista and later versions of Windows. |
| SL_INDEX_SPECIFIED    | Used for [**IRP_MJ_DIRECTORY_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-directory-control), [**IRP_MJ_QUERY_EA**](/windows-hardware/drivers/ifs/irp-mj-query-ea), and [**IRP_MJ_SET_QUOTA**](/windows-hardware/drivers/ifs/irp-mj-set-quota). If this flag is set, the scan for directory, quota, or extended-attribute information should begin at the entry in the list whose index is specified. |
| SL_OPEN_PAGING_FILE    | Used for [**IRP_MJ_CREATE**](/windows-hardware/drivers/ifs/irp-mj-create). If this flag is set, the file is a paging file. |
| SL_OPEN_TARGET_DIRECTORY | Used for [**IRP_MJ_CREATE**](/windows-hardware/drivers/ifs/irp-mj-create). If this flag is set, the file's parent directory should be opened. |
| SL_OVERRIDE_VERIFY_VOLUME | Used for [**IRP_MJ_DIRECTORY_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-directory-control), [**IRP_MJ_READ**](/windows-hardware/drivers/ifs/irp-mj-read), and [**IRP_MJ_WRITE**](/windows-hardware/drivers/kernel/irp-mj-write). If this flag is set, the I/O operation should be performed even if the DO_VERIFY_VOLUME flag is set on the volume's device object. |
| SL_RESTART_SCAN | Used for [**IRP_MJ_DIRECTORY_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-directory-control), [**IRP_MJ_QUERY_EA**](/windows-hardware/drivers/ifs/irp-mj-query-ea), and [**IRP_MJ_SET_QUOTA**](/windows-hardware/drivers/ifs/irp-mj-set-quota). If this flag is set, the scan for directory, quota, or extended-attribute information should begin at the first entry in the directory or list. Otherwise, the scan should be resumed from the previous scan. |
| SL_RETURN_SINGLE_ENTRY | Used for [**IRP_MJ_DIRECTORY_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-directory-control), [**IRP_MJ_QUERY_EA**](/windows-hardware/drivers/ifs/irp-mj-query-ea), and [**IRP_MJ_SET_QUOTA**](/windows-hardware/drivers/ifs/irp-mj-set-quota). If this flag is set, the scan for directory, quota, or extended-attribute information should return only the first entry that is found. |
| SL_WATCH_TREE | Used for [**IRP_MJ_DIRECTORY_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-directory-control). If this flag is set, all subdirectories of this directory should also be watched. Otherwise, only the directory itself is to be watched. |
| SL_WRITE_THROUGH | Used for [**IRP_MJ_WRITE**](/windows-hardware/drivers/kernel/irp-mj-write). If this flag is set, the file data must be written through to persistent storage, not just written to the cache. |

### -field Reserved

Reserved for system use. Do not use.

### -field TargetFileObject

A file object pointer for the file or directory that is the target for this I/O operation.

### -field TargetInstance

An opaque instance pointer for the minifilter that is the target for this I/O operation.

### -field Parameters

An [**FLT_PARAMETERS**](ns-fltkernel-_flt_parameters) structure that contains the parameters for the I/O operation that are specified by the **MajorFunction** and **MinorFunction** members.

## -remarks

The FLT_IO_PARAMETER_BLOCK structure contains the parameters for the I/O operation that is represented by a callback data ([**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)) structure. The callback data structure contains a pointer to the FLT_IO_PARAMETER_BLOCK structure in its  **Iopb** member.

A minifilter receives a pointer to the callback data structure as the *Data* or *CallbackData* input parameter to the following callback routine types:

* [**PFLT_POST_OPERATION_CALLBACK**](nc-fltkernel-pflt_post_operation_callback.md)
* [**PFLT_PRE_OPERATION_CALLBACK**](nc-fltkernel-pflt_pre_operation_callback.md)
* [**PFLT_COMPLETED_ASYNC_IO_CALLBACK**](nc-fltkernel-pflt_completed_async_io_callback.md)
* [**PFLT_GENERATE_FILE_NAME**](nc-fltkernel-pflt_generate_file_name.md)

A minifilter's preoperation and postoperation callback routines can modify the contents of the FLT_IO_PARAMETER_BLOCK structure for the I/O operation, except for the **MajorFunction** and **Reserved** members. If it does, it must call [**FltSetCallbackDataDirty**](nf-fltkernel-fltsetcallbackdatadirty.md), unless it has also modified the **IoStatus** member of the callback data structure for the operation. Otherwise, the modified values are ignored.

When Filter Manager issues a preoperation or postoperation callback to a minifilter,  [**FltObjects->FileObject**](ns-fltkernel-_flt_related_objects.md) and **TargetFileObject** (CallbackData->Iopb->TargetFileObject) are initially the same. If a minifilter modifies **TargetFileObject** or **TargetInstance**, its subsequent call to **FltSetCallbackDataDirty** from a preoperation callback will cause Filter Manager to replace **FltObjects->FileObject** and **FltObjects->Instance** before sending the operation to lower filters.

If a minifilter's preoperation callback routine modifies the parameters for an I/O operation, all minifilters below it in the minifilter instance stack will receive the modified parameters in their preoperation and postoperation callback routines.

The modified parameters are not received by the minifilter's own postoperation callback routine, or by any minifilters above that minifilter in the minifilter instance stack. In all cases, a minifilter's preoperation and postoperation callback routines receive the same input parameter values.

If a minifilter changes the value of the **TargetInstance** member, the new value must be a pointer to an instance of the same minifilter at the same altitude on a different volume. In addition, the new volume's device object must have a stack size that is greater than or equal to that of the original volume's device object.

To get the stack size for a volume device object, given an opaque instance pointer for an instance that is attached to the volume, do the following:

* Call **FltGetVolumeFromInstance** to get the volume pointer.
* Call **FltGetDeviceObject** to get a pointer to the volume device object. This pointer is returned in the *DeviceObject* parameter. The device object's stack size can be found in **DeviceObject->StackSize**.
* When the volume pointer is no longer needed, call **FltObjectDereference** to decrement its reference count.
* When the volume device object pointer is no longer needed, call **ObDereferenceObject** to decrement its reference count.

A minifilter can change the value of the **TargetFileObject** member. However, the new value must be a pointer to a file object for a file that resides on the same volume as the instance specified by the **TargetInstance** member.

A minifilter cannot safely change the value of the **MajorFunction** member. Instead, it must initiate a new I/O operation.

A minifilter can initiate an I/O operation by calling a support routine such as [**FltReadFile**](nf-fltkernel-fltreadfile.md) or by calling [**FltAllocateCallbackData**](nf-fltkernel-fltallocatecallbackdata.md) to allocate a callback data structure; initializing the I/O parameters in the **FLT_IO_PARAMETER_BLOCK** structure, and passing the callback data structure to [**FltPerformSynchronousIo**](nf-fltkernel-fltperformsynchronousio.md) or [**FltPerformAsynchronousIo**](nf-fltkernel-fltperformasynchronousio.md).

> [!NOTE]
>
> Use support routines wherever possible when initiating I/O operations.  A minifilter should allocate its own callback data only if there is no support function for a particular I/O operation.

## -see-also

[**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)

[**FLT_IS_IRP_OPERATION**](/previous-versions/ff544654(v=vs.85))

[**FLT_PARAMETERS**](ns-fltkernel-_flt_parameters.md)

[**FltAllocateCallbackData**](nf-fltkernel-fltallocatecallbackdata.md)

[**FltClearCallbackDataDirty**](nf-fltkernel-fltclearcallbackdatadirty.md)

[**FltDecodeParameters**](nf-fltkernel-fltdecodeparameters.md)

[**FltIsCallbackDataDirty**](nf-fltkernel-fltiscallbackdatadirty.md)

[**FltReadFile**](nf-fltkernel-fltreadfile.md)

[**FltSetCallbackDataDirty**](nf-fltkernel-fltsetcallbackdatadirty.md)

[**IO_STACK_LOCATION**](../wdm/ns-wdm-_io_stack_location.md)

[**IRP**](../wdm/ns-wdm-_irp.md)

[**IRP_MJ_CLEANUP**](/windows-hardware/drivers/ifs/irp-mj-cleanup)

[**IRP_MJ_CLOSE**](/windows-hardware/drivers/kernel/irp-mj-close)

[**IRP_MJ_CREATE**](/windows-hardware/drivers/ifs/irp-mj-create)

[**IRP_MJ_DEVICE_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-device-control)

[**IRP_MJ_DIRECTORY_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-directory-control)

[**IRP_MJ_FILE_SYSTEM_CONTROL**](/windows-hardware/drivers/kernel/irp-mj-file-system-control)

[**IRP_MJ_FLUSH_BUFFERS**](/windows-hardware/drivers/ifs/irp-mj-flush-buffers)

[**IRP_MJ_INTERNAL_DEVICE_CONTROL**](/windows-hardware/drivers/kernel/irp-mj-internal-device-control)

[**IRP_MJ_LOCK_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-lock-control)

[**IRP_MJ_PNP**](/windows-hardware/drivers/ifs/irp-mj-pnp)

[**IRP_MJ_QUERY_EA**](/windows-hardware/drivers/ifs/irp-mj-query-ea)

[**IRP_MJ_QUERY_INFORMATION**](/windows-hardware/drivers/ifs/irp-mj-query-information)

[**IRP_MJ_QUERY_QUOTA**](/windows-hardware/drivers/ifs/irp-mj-query-quota)

[**IRP_MJ_QUERY_SECURITY**](/windows-hardware/drivers/ifs/irp-mj-query-security)

[**IRP_MJ_QUERY_VOLUME_INFORMATION**](/windows-hardware/drivers/ifs/irp-mj-query-volume-information)

[**IRP_MJ_READ**](/windows-hardware/drivers/ifs/irp-mj-read)

[**IRP_MJ_SET_EA**](/windows-hardware/drivers/ifs/irp-mj-set-ea)

[**IRP_MJ_SET_INFORMATION**](/windows-hardware/drivers/ifs/irp-mj-set-information)

[**IRP_MJ_SET_QUOTA**](/windows-hardware/drivers/ifs/irp-mj-set-quota)

[**IRP_MJ_SET_SECURITY**](/windows-hardware/drivers/ifs/irp-mj-set-security)

[**IRP_MJ_SET_VOLUME_INFORMATION**](/windows-hardware/drivers/ifs/irp-mj-set-volume-information)

[**IRP_MJ_SHUTDOWN**](/windows-hardware/drivers/ifs/irp-mj-shutdown)

[**IRP_MJ_WRITE**](/windows-hardware/drivers/kernel/irp-mj-write)

[**PFLT_COMPLETED_ASYNC_IO_CALLBACK**](nc-fltkernel-pflt_completed_async_io_callback.md)

[**PFLT_GENERATE_FILE_NAME**](nc-fltkernel-pflt_generate_file_name.md)

[**PFLT_POST_OPERATION_CALLBACK**](nc-fltkernel-pflt_post_operation_callback.md)

[**PFLT_PRE_OPERATION_CALLBACK**](nc-fltkernel-pflt_pre_operation_callback.md)