---
UID: NF:ntifs.IoSetDeviceToVerify
title: IoSetDeviceToVerify function
author: windows-driver-content
description: The IoSetDeviceToVerify routine specifies a device object to be verified. The specified device object represents a removable media device.
old-location: ifsk\iosetdevicetoverify.htm
old-project: ifsk
ms.assetid: 509eb91d-7f34-4ebb-bc37-56889c15a1b3
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: IoSetDeviceToVerify, IoSetDeviceToVerify routine [Installable File System Drivers], ifsk.iosetdevicetoverify, ioref_58eab192-eab0-42ee-8c2b-4fe1ad0fb703.xml, ntifs/IoSetDeviceToVerify
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlIoDispatch
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoSetDeviceToVerify
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# IoSetDeviceToVerify function


## -description


The <b>IoSetDeviceToVerify</b> routine specifies a device object to be verified. The specified device object represents a removable media device.


## -syntax


````
VOID IoSetDeviceToVerify(
  _In_     PETHREAD       Thread,
  _In_opt_ PDEVICE_OBJECT DeviceObject
);
````


## -parameters




### -param Thread [in]

A pointer to the thread.


### -param DeviceObject [in, optional]

A pointer to the device object for a removable-media device. Can be <b>NULL</b>.


## -returns



None




## -remarks



A file system calls <b>IoSetDeviceToVerify</b> to indicate that a given device object, representing a removable-media device, needs to be verified.

A file system must verify a volume when it receives notification from an underlying removable-media device driver that the media appears to have changed since the last access to the target device. 

Before using <b>IoSetDeviceToVerify</b> and <a href="..\ntifs\nf-ntifs-ioverifyvolume.md">IoVerifyVolume</a>, driver writers are strongly encouraged to study the way these routines are used in the FASTFAT sample.

For more information about removable-media devices, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563916">Supporting Removable Media</a>.




## -see-also

<a href="..\wdm\nf-wdm-psgetcurrentthread.md">PsGetCurrentThread</a>



<a href="..\ntifs\nf-ntifs-iogetdevicetoverify.md">IoGetDeviceToVerify</a>



<a href="..\wdm\ns-wdm-_irp.md">IRP</a>



<a href="..\ntifs\nf-ntifs-ioverifyvolume.md">IoVerifyVolume</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IoSetDeviceToVerify routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

