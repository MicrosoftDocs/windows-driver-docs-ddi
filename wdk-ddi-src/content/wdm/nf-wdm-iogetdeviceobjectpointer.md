---
UID: NF:wdm.IoGetDeviceObjectPointer
title: IoGetDeviceObjectPointer function (wdm.h)
description: The IoGetDeviceObjectPointer routine returns a pointer to the top object in the named device object's stack and a pointer to the corresponding file object, if the requested access to the objects can be granted.
old-location: kernel\iogetdeviceobjectpointer.htm
tech.root: kernel
ms.assetid: aeb088f3-92c3-4619-9c3b-756bd70307e7
ms.date: 04/30/2018
keywords: ["IoGetDeviceObjectPointer function"]
ms.keywords: IoGetDeviceObjectPointer, IoGetDeviceObjectPointer routine [Kernel-Mode Driver Architecture], k104_c57b87e5-8316-4c45-a245-0fe7592c3471.xml, kernel.iogetdeviceobjectpointer, wdm/IoGetDeviceObjectPointer
f1_keywords:
 - "wdm/IoGetDeviceObjectPointer"
 - "IoGetDeviceObjectPointer"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlIoPassive5, PowerIrpDDis, HwStorPortProhibitedDDIs
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
- IoGetDeviceObjectPointer
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoGetDeviceObjectPointer function


## -description


The <b>IoGetDeviceObjectPointer</b> routine returns a pointer to the top object in the named device object's stack and a pointer to the corresponding file object, if the requested access to the objects can be granted.


## -parameters




### -param ObjectName [in]

Pointer to a buffer that contains a Unicode string that is the name of the device object.


### -param DesiredAccess [in]

Specifies the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> value that represents the desired access. Usually <i>DesiredAccess</i> is FILE_READ_DATA. Infrequently, the FILE_WRITE_DATA, or FILE_ALL_ACCESS access rights are specified.


### -param FileObject [out]

Pointer to the file object that represents the corresponding device object to user-mode code if the call is successful.


### -param DeviceObject [out]

Pointer to the device object that represents the named logical, virtual, or physical device if the call is successful.


## -returns



<b>IoGetDeviceObjectPointer</b> returns STATUS_SUCCESS if it is successful. Possible error return values include the following status codes:

STATUS_OBJECT_TYPE_MISMATCH

STATUS_INVALID_PARAMETER

STATUS_PRIVILEGE_NOT_HELD

STATUS_INSUFFICIENT_RESOURCES

STATUS_OBJECT_NAME_INVALID




## -remarks



<b>IoGetDeviceObjectPointer</b> establishes a "connection" between the caller and the next-lower-level driver. A successful caller can use the returned device object pointer to initialize its own device objects. It can also be used as an argument to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioattachdevicetodevicestack">IoAttachDeviceToDeviceStack</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocalldriver">IoCallDriver</a>, and any routine that creates IRPs for lower drivers. The returned pointer is a required argument to <b>IoCallDriver</b>.

This routine also returns a pointer to the corresponding file object. When unloading, a driver can dereference the file object as a means of indirectly dereferencing the device object. To do so, the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobject">ObDereferenceObject</a> from its Unload routine, passing the file object pointer returned by <b>IoGetDeviceObjectPointer</b>. Failure to dereference the device object in a driver's Unload routine prevents the next-lower driver from being unloaded. However, drivers that close the file object before the unload process must take out an extra reference on the device object before dereferencing the file object. Otherwise, dereferencing the file object can lead to a premature deletion of the device object.

To get a pointer to the highest-level driver in the file system driver stack, a driver must ensure that the file system is mounted; if it is not, this routine traverses the storage device stack. To ensure that the file system is mounted on the storage device, the driver must specify an appropriate access mask, such as FILE_READ_DATA or FILE_WRITE_ATTRIBUTES, in the <i>DesiredAccess</i> parameter. Specifying FILE_READ_ATTRIBUTES does not cause the file system to be mounted.

After any higher-level driver has chained itself over another driver by successfully calling this routine, the higher-level driver must set the <b>StackSize</b> field in its device object to that of the next-lower-level driver's device object plus one.

Callers of <b>IoGetDeviceObjectPointer</b> must be running at IRQL = PASSIVE_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateirp">IoAllocateIrp</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioattachdevice">IoAttachDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioattachdevicetodevicestack">IoAttachDeviceToDeviceStack</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocalldriver">IoCallDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobject">ObDereferenceObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obreferenceobjectbypointer">ObReferenceObjectByPointer</a>
 

 

