---
UID: NF:wdm.IoGetRelatedDeviceObject
title: IoGetRelatedDeviceObject function
author: windows-driver-content
description: Given a file object, the IoGetRelatedDeviceObject routine returns a pointer to the corresponding device object.
old-location: kernel\iogetrelateddeviceobject.htm
old-project: kernel
ms.assetid: 70427fad-6a3d-40bb-9523-787c14fa1e39
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: IoGetRelatedDeviceObject, kernel.iogetrelateddeviceobject, IoGetRelatedDeviceObject routine [Kernel-Mode Driver Architecture], wdm/IoGetRelatedDeviceObject, k104_22abf9c6-81f5-497e-9bca-8a00b2c871df.xml
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL (see Remarks section)"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoGetRelatedDeviceObject
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoGetRelatedDeviceObject function


## -description


Given a file object, the <b>IoGetRelatedDeviceObject</b> routine returns a pointer to the corresponding device object.


## -syntax


````
PDEVICE_OBJECT IoGetRelatedDeviceObject(
  _In_ PFILE_OBJECT FileObject
);
````


## -parameters




### -param FileObject [in]

Pointer to the file object. 


## -returns



<b>IoGetRelatedDeviceObject</b> returns a pointer to the device object.




## -remarks



When called on a file object that represents the underlying storage device, <b>IoGetRelatedDeviceObject</b> returns the highest-level device object in the storage device stack. To obtain the highest-level device object in the file system driver stack, drivers must call <b>IoGetRelatedDeviceObject</b> on a file object that represents the file system's driver stack, and the file system must currently be mounted. (Otherwise, the storage device stack is traversed instead of the file system stack.)

To ensure that the file system is mounted on the storage device, the driver must have specified an appropriate access mask, such as FILE_READ_DATA or FILE_WRITE_ATTRIBUTES, when opening the file or device represented by the file object. Specifying FILE_READ_ATTRIBUTES does not cause the file system to be mounted. 

The caller must be running at IRQL &lt;= DISPATCH_LEVEL. Usually, callers of this routine are running at IRQL = PASSIVE_LEVEL. 




## -see-also

<a href="..\wdm\nf-wdm-iogetdeviceobjectpointer.md">IoGetDeviceObjectPointer</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoGetRelatedDeviceObject routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

