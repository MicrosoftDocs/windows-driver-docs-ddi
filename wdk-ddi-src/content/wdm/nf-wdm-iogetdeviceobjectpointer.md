---
UID: NF:wdm.IoGetDeviceObjectPointer
title: IoGetDeviceObjectPointer function
author: windows-driver-content
description: The IoGetDeviceObjectPointer routine returns a pointer to the top object in the named device object's stack and a pointer to the corresponding file object, if the requested access to the objects can be granted.
old-location: kernel\iogetdeviceobjectpointer.htm
old-project: kernel
ms.assetid: aeb088f3-92c3-4619-9c3b-756bd70307e7
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IoGetDeviceObjectPointer, IoGetDeviceObjectPointer routine [Kernel-Mode Driver Architecture], k104_c57b87e5-8316-4c45-a245-0fe7592c3471.xml, kernel.iogetdeviceobjectpointer, wdm/IoGetDeviceObjectPointer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoGetDeviceObjectPointer
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoGetDeviceObjectPointer function


## -description


The <b>IoGetDeviceObjectPointer</b> routine returns a pointer to the top object in the named device object's stack and a pointer to the corresponding file object, if the requested access to the objects can be granted.


## -syntax


````
NTSTATUS IoGetDeviceObjectPointer(
  _In_  PUNICODE_STRING ObjectName,
  _In_  ACCESS_MASK     DesiredAccess,
  _Out_ PFILE_OBJECT    *FileObject,
  _Out_ PDEVICE_OBJECT  *DeviceObject
);
````


## -parameters




### -param ObjectName [in]

Pointer to a buffer that contains a Unicode string that is the name of the device object.


### -param DesiredAccess [in]

Specifies the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value that represents the desired access. Usually <i>DesiredAccess</i> is FILE_READ_DATA. Infrequently, the FILE_WRITE_DATA, or FILE_ALL_ACCESS access rights are specified.


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



<b>IoGetDeviceObjectPointer</b> establishes a "connection" between the caller and the next-lower-level driver. A successful caller can use the returned device object pointer to initialize its own device objects. It can also be used as an argument to <a href="..\wdm\nf-wdm-ioattachdevicetodevicestack.md">IoAttachDeviceToDeviceStack</a>, <a href="..\wdm\nf-wdm-iocalldriver.md">IoCallDriver</a>, and any routine that creates IRPs for lower drivers. The returned pointer is a required argument to <b>IoCallDriver</b>.

This routine also returns a pointer to the corresponding file object. When unloading, a driver can dereference the file object as a means of indirectly dereferencing the device object. To do so, the driver calls <a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a> from its Unload routine, passing the file object pointer returned by <b>IoGetDeviceObjectPointer</b>. Failure to dereference the device object in a driver's Unload routine prevents the next-lower driver from being unloaded. However, drivers that close the file object before the unload process must take out an extra reference on the device object before dereferencing the file object. Otherwise, dereferencing the file object can lead to a premature deletion of the device object.

To get a pointer to the highest-level driver in the file system driver stack, a driver must ensure that the file system is mounted; if it is not, this routine traverses the storage device stack. To ensure that the file system is mounted on the storage device, the driver must specify an appropriate access mask, such as FILE_READ_DATA or FILE_WRITE_ATTRIBUTES, in the <i>DesiredAccess</i> parameter. Specifying FILE_READ_ATTRIBUTES does not cause the file system to be mounted.

After any higher-level driver has chained itself over another driver by successfully calling this routine, the higher-level driver must set the <b>StackSize</b> field in its device object to that of the next-lower-level driver's device object plus one.

Callers of <b>IoGetDeviceObjectPointer</b> must be running at IRQL = PASSIVE_LEVEL.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



<a href="..\wdm\nf-wdm-iocalldriver.md">IoCallDriver</a>



<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>



<a href="..\wdm\nf-wdm-ioallocateirp.md">IoAllocateIrp</a>



<a href="..\wdm\nf-wdm-obreferenceobjectbypointer.md">ObReferenceObjectByPointer</a>



<a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a>



<a href="..\wdm\nf-wdm-ioattachdevicetodevicestack.md">IoAttachDeviceToDeviceStack</a>



<a href="..\wdm\nf-wdm-ioattachdevice.md">IoAttachDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoGetDeviceObjectPointer routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

