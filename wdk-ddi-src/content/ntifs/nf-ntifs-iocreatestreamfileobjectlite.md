---
UID: NF:ntifs.IoCreateStreamFileObjectLite
title: IoCreateStreamFileObjectLite function (ntifs.h)
description: The IoCreateStreamFileObjectLite routine creates a new stream file object, but does not cause an IRP_MJ_CLEANUP request to be sent to the file system driver stack.
old-location: ifsk\iocreatestreamfileobjectlite.htm
tech.root: ifsk
ms.assetid: 79c6438c-ba8c-4fc5-8c3f-5865a51869b7
ms.date: 04/16/2018
ms.keywords: IoCreateStreamFileObjectLite, IoCreateStreamFileObjectLite routine [Installable File System Drivers], ifsk.iocreatestreamfileobjectlite, ioref_0e35141f-7028-47b0-8dc1-0bd9d1c4e0be.xml, ntifs/IoCreateStreamFileObjectLite
ms.topic: function
f1_keywords:
 - "ntifs/IoCreateStreamFileObjectLite"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows 2000 and later.
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
req.irql: "< DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoCreateStreamFileObjectLite
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoCreateStreamFileObjectLite function


## -description


The <b>IoCreateStreamFileObjectLite</b> routine creates a new stream file object, but does not cause an IRP_MJ_CLEANUP request to be sent to the file system driver stack. 


## -parameters




### -param FileObject [in, optional]

A pointer to the file object to which the new stream file is related. This parameter is optional and can be <b>NULL</b>. 


### -param DeviceObject [in, optional]

A pointer to a device object for the device on which the stream file is to be opened. If the caller specifies a non-<b>NULL</b> value for <i>FileObject</i>, the value of <i>DeviceObject</i> is ignored. Otherwise, the caller must specify a non-<b>NULL</b> value for <i>DeviceObject</i>. 


## -returns



<b>IoCreateStreamFileObjectLite</b> returns a pointer to the newly created stream file object.




## -remarks



File systems call <b>IoCreateStreamFileObjectLite</b> to create a new stream file object. A <i>stream file object</i> is identical to an ordinary file object, except that the FO_STREAM_FILE file object flag is set. 

A stream file object is commonly used to represent an internal stream for a volume mounted by the file system. This <i>virtual volume file</i> permits the file system to view, change, and cache the volume's on-disk structure as if it were an ordinary file. In this case, the <i>DeviceObject</i> parameter in the call to <b>IoCreateStreamFileObjectLite</b> specifies the volume device object (VDO) for the volume. 

A stream file object can also be used to represent an alternate data stream for accessing metadata, such as extended attributes or security descriptors, for an already opened file. In this case, the <i>FileObject</i> parameter in the call to <b>IoCreateStreamFileObjectLite</b> specifies an existing file object for the file. The newly created stream file object permits the file system to view, change, and cache the file's metadata as if it were an ordinary file. 

When the stream file object is no longer needed, the caller must decrement its reference count by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-obdereferenceobject">ObDereferenceObject</a>. When the stream file object's reference count reaches zero, an IRP_MJ_CLOSE request is sent to the file system driver stack for the volume. 

File system filter driver writers should note that, unlike <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-iocreatestreamfileobject">IoCreateStreamFileObject</a>, <b>IoCreateStreamFileObjectLite</b> does not cause an IRP_MJ_CLEANUP request to be sent to the file system driver stack. For this reason, and because file systems often create stream file objects as a side effect of operations other than IRP_MJ_CREATE, it is difficult for filter drivers to reliably detect stream file object creation. Thus filter drivers should expect to receive IRP_MJ_CLOSE requests for previously unseen file objects. 

If a pool allocation failure occurs, <b>IoCreateStreamFileObjectLite</b> raises a STATUS_INSUFFICIENT_RESOURCES exception. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-cleanup">IRP_MJ_CLEANUP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-close">IRP_MJ_CLOSE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-create">IRP_MJ_CREATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-iocreatestreamfileobject">IoCreateStreamFileObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-iocreatestreamfileobjectex">IoCreateStreamFileObjectEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-obdereferenceobject">ObDereferenceObject</a>
 

 

