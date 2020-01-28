---
UID: NF:ntifs.IoCreateStreamFileObjectEx2
title: IoCreateStreamFileObjectEx2 function (ntifs.h)
description: The IoCreateStreamFileObjectEx2 routine creates a new stream file object with create options for a target device object.
old-location: ifsk\iocreatestreamfileobjectex2.htm
tech.root: ifsk
ms.assetid: 2F12F4E5-21C2-4DA8-9111-0087A16F0256
ms.date: 04/16/2018
ms.keywords: IoCreateStreamFileObjectEx, IoCreateStreamFileObjectEx routine [Installable File System Drivers], IoCreateStreamFileObjectEx2, ifsk.iocreatestreamfileobjectex2, ntifs/IoCreateStreamFileObjectEx
f1_keywords:
 - "ntifs/IoCreateStreamFileObjectEx"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoCreateStreamFileObjectEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoCreateStreamFileObjectEx2 function


## -description


The <b>IoCreateStreamFileObjectEx2</b> routine creates a new stream file object with create options for a target device object. 


## -parameters




### -param CreateOptions [in]

Pointer a <b>IO_CREATE_STREAM_FILE_OPTIONS</b> structure containing the create options for the new stream file object.  <b>IO_CREATE_STREAM_FILE_OPTIONS</b> is defined in <i>ntifs.h</i> as the following.

<pre class="syntax" xml:space="preserve"><code>typedef struct _IO_CREATE_STREAM_FILE_OPTIONS {
    USHORT Size;
    USHORT Flags;
    PDEVICE_OBJECT TargetDeviceObject;
} IO_CREATE_STREAM_FILE_OPTIONS, *PIO_CREATE_STREAM_FILE_OPTIONS;
</code></pre>




#### Size

Size of the stream options structure. Set to <b>sizeof</b>(IO_CREATE_STREAM_FILE_OPTIONS).



#### Flags

The flags for the stream file create options. This value can be one of the following.



<table>
<tr>
<th>Term</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<a id="IO_CREATE_STREAM_FILE_RAISE_ON_ERROR"></a><a id="io_create_stream_file_raise_on_error"></a>IO_CREATE_STREAM_FILE_RAISE_ON_ERROR

</td>
<td width="60%">
On an error condition, <b>IoCreateStreamFileObjectEx2</b> will raise the error
        status as an exception instead of returning it.  This flag is specified to maintain error status behavior of the other stream file object creation routines.

</td>
</tr>
<tr>
<td width="40%">
<a id="IO_CREATE_STREAM_FILE_LITE"></a><a id="io_create_stream_file_lite"></a>IO_CREATE_STREAM_FILE_LITE

</td>
<td width="60%">
A file object is created with out a file handle. No close operation is sent for the file object when it is deleted.

</td>
</tr>
</table>
 



#### TargetDeviceObject

A pointer to the device object to set as the target for operations on the file
        handle.  <b>TargetDeviceObject</b> must be in the same device stack as <i>DeviceObject</i> parameter.  This
        member is optional.


### -param FileObject [in, optional]

Pointer to the file object to which the new stream file is related. This parameter is optional and can be <b>NULL</b>. 


### -param DeviceObject [in, optional]

Pointer to a device object for the device on which the stream file is to be opened. If the caller specifies a non-<b>NULL</b> value for <i>FileObject</i>, the value of <i>DeviceObject</i> is ignored. Otherwise, the caller must specify a non-<b>NULL</b> value for <i>DeviceObject</i>. 


### -param StreamFileObject [out]

Pointer to a device object pointer to receive the stream fille object.


### -param FileHandle [out, optional]

A pointer to a file handle for the stream on output. This parameter is optional and can be <b>NULL</b>. 


## -returns



<b>IoCreateStreamFileObjectEx2</b> returns a pointer to the newly created stream file object.




## -remarks



File systems call <b>IoCreateStreamFileObjectEx2</b> to create a new stream file object. A <i>stream file object</i> is identical to an ordinary file object, except that the<b> FO_STREAM_FILE</b> file object flag is set.

A stream file object is commonly used to represent an internal stream for a volume mounted by the file system. This <i>virtual volume file</i> permits the file system to view, change, and cache the volume's on-disk structure as if it were an ordinary file. In this case, the <i>DeviceObject</i> parameter in the call to <b>IoCreateStreamFileObjectEx2</b> specifies the volume device object (VDO) for the volume.

A stream file object can also be used to represent an alternate data stream for accessing a file's metadata, such as extended attributes or security descriptors. In this case, the <i>FileObject</i> parameter in the call to <b>IoCreateStreamFileObjectEx2</b> specifies an existing file object for the file. The newly created stream file object permits the file system to view, change, and cache the file's metadata as if it were an ordinary file.

When the stream file object is no longer needed, the caller must decrement its reference count by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobject">ObDereferenceObject</a>. When the stream file object's reference count reaches zero, an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-close">IRP_MJ_CLOSE</a> request is sent to the file system driver stack for the volume.

File system filter driver writers should note that <b>IoCreateStreamFileObjectEx2</b> causes an <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-cleanup">IRP_MJ_CLEANUP</a> request to be sent to the file system driver stack for the volume. Because file systems often create stream file objects as a side effect of operations other than <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-create">IRP_MJ_CREATE</a>, it is difficult for filter drivers to reliably detect stream file object creation. Thus a filter driver should expect to receive I<b>IRP_MJ_CLEANUP</b> and <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-close">IRP_MJ_CLOSE</a> requests for previously unseen file objects.

If a pool allocation failure occurs, <b>IoCreateStreamFileObjectEx2</b> raises a <b>STATUS_INSUFFICIENT_RESOURCES</b> exception.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-cleanup">IRP_MJ_CLEANUP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-close">IRP_MJ_CLOSE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-create">IRP_MJ_CREATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iocreatestreamfileobject">IoCreateStreamFileObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iocreatestreamfileobjectex">IoCreateStreamFileObjectEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iocreatestreamfileobjectlite">IoCreateStreamFileObjectLite</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobject">ObDereferenceObject</a>
 

 

