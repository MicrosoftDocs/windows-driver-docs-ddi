---
UID: NF:ntifs.IoCreateStreamFileObjectEx2
title: IoCreateStreamFileObjectEx2 function (ntifs.h)
description: Learn more about the IoCreateStreamFileObjectEx2 routine.
tech.root: ifsk
ms.date: 07/06/2023
keywords: ["IoCreateStreamFileObjectEx2 function"]
ms.keywords: IoCreateStreamFileObjectEx, ifsk.iocreatestreamfileobjectex2, ntifs/IoCreateStreamFileObjectEx
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
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
req.irql: PASSIVE
targetos: Windows
req.typenames: 
f1_keywords:
 - IoCreateStreamFileObjectEx2
 - ntifs/IoCreateStreamFileObjectEx2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoCreateStreamFileObjectEx2
---

# IoCreateStreamFileObjectEx2 function

## -description

The **IoCreateStreamFileObjectEx2** routine creates a new stream file object with create options for a target device object.

## -parameters

### -param CreateOptions [in]

Pointer a [**IO_CREATE_STREAM_FILE_OPTIONS**](ns-ntifs-io_create_stream_file_options.md) structure containing the create options for the new stream file object.

### -param FileObject [in, optional]

Pointer to the file object to which the new stream file is related. This parameter is optional and can be NULL.

### -param DeviceObject [in, optional]

Pointer to a device object for the device on which the stream file is to be opened. If the caller specifies a non-NULL value for **FileObject**, the value of **DeviceObject** is ignored. Otherwise, the caller must specify a non-NULL value for **DeviceObject**.

### -param StreamFileObject [out]

Pointer to a device object pointer to receive the stream fille object.

### -param FileHandle [out, optional]

A pointer to a file handle for the stream on output. This parameter is optional and can be NULL.

## -returns

**IoCreateStreamFileObjectEx2** returns a pointer to the newly created stream file object.

## -remarks

File systems call **IoCreateStreamFileObjectEx2** to create a new stream file object. A **stream file object** is identical to an ordinary file object, except that the **FO_STREAM_FILE** file object flag is set.

A stream file object is commonly used to represent an internal stream for a volume mounted by the file system. This **virtual volume file** permits the file system to view, change, and cache the volume's on-disk structure as if it were an ordinary file. In this case, the **DeviceObject** parameter in the call to **IoCreateStreamFileObjectEx2** specifies the volume device object (VDO) for the volume.

A stream file object can also be used to represent an alternate data stream for accessing a file's metadata, such as extended attributes or security descriptors. In this case, the **FileObject** parameter in the call to **IoCreateStreamFileObjectEx2** specifies an existing file object for the file. The newly created stream file object permits the file system to view, change, and cache the file's metadata as if it were an ordinary file.

When the stream file object is no longer needed, the caller must decrement its reference count by calling [**ObDereferenceObject**](../wdm/nf-wdm-obdereferenceobject.md). When the stream file object's reference count reaches zero, an [IRP_MJ_CLOSE](/windows-hardware/drivers/ifs/irp-mj-close) request is sent to the file system driver stack for the volume.

File system filter driver writers should note that **IoCreateStreamFileObjectEx2** causes an [IRP_MJ_CLEANUP](/windows-hardware/drivers/ifs/irp-mj-cleanup) request to be sent to the file system driver stack for the volume. Because file systems often create stream file objects as a side effect of operations other than [IRP_MJ_CREATE](/windows-hardware/drivers/ifs/irp-mj-create), it is difficult for filter drivers to reliably detect stream file object creation. Thus a filter driver should expect to receive I**IRP_MJ_CLEANUP** and [IRP_MJ_CLOSE](/windows-hardware/drivers/ifs/irp-mj-close) requests for previously unseen file objects.

If a pool allocation failure occurs, **IoCreateStreamFileObjectEx2** raises a **STATUS_INSUFFICIENT_RESOURCES** exception.

## -see-also

[IRP_MJ_CLEANUP](/windows-hardware/drivers/ifs/irp-mj-cleanup)

[IRP_MJ_CLOSE](/windows-hardware/drivers/ifs/irp-mj-close)

[IRP_MJ_CREATE](/windows-hardware/drivers/ifs/irp-mj-create)

[**IoCreateStreamFileObject**](nf-ntifs-iocreatestreamfileobject.md)

[**IoCreateStreamFileObjectEx**](nf-ntifs-iocreatestreamfileobjectex.md)

[**IoCreateStreamFileObjectLite**](nf-ntifs-iocreatestreamfileobjectlite.md)

[**ObDereferenceObject**](../wdm/nf-wdm-obdereferenceobject.md)
