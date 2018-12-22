---
UID: NF:ntddk.IoAttachDeviceToDeviceStackSafe
title: IoAttachDeviceToDeviceStackSafe function
description: The IoAttachDeviceToDeviceStackSafe routine attaches the caller's device object to the topmost device object in a driver stack.
old-location: ifsk\ioattachdevicetodevicestacksafe.htm
tech.root: ifsk
ms.assetid: bc403fc7-7862-4c4c-8a82-bd5c740b270e
ms.date: 04/16/2018
ms.keywords: IoAttachDeviceToDeviceStackSafe, IoAttachDeviceToDeviceStackSafe routine [Installable File System Drivers], ifsk.ioattachdevicetodevicestacksafe, ioref_1db91288-e8ad-4796-9052-333bf37f01d1.xml, ntddk/IoAttachDeviceToDeviceStackSafe
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Update Rollup for Windows 2000 Service Pack 4 (SP4) and on Windows XP and later.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoAttachDeviceToDeviceStackSafe
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoAttachDeviceToDeviceStackSafe function


## -description


The <b>IoAttachDeviceToDeviceStackSafe</b> routine attaches the caller's device object to the topmost device object in a driver stack. 


## -parameters




### -param SourceDevice [in]

Pointer to a caller-created device object. 


### -param TargetDevice [in]

Pointer to the device object in the stack to which the <i>SourceDevice</i> object is to be attached. 


### -param AttachedToDeviceObject [out]

On input, this parameter specifies the address of <i>SourceDevice-&gt;DeviceExtension-&gt;AttachedToDeviceObject</i>, which must contain a <b>NULL</b> pointer. On output, this parameter receives a pointer to the device object to which the <i>SourceDevice</i> was attached. 


## -returns



<b>IoAttachDeviceToDeviceStackSafe</b> returns STATUS_SUCCESS if <i>SourceDevice</i> is successfully attached above the <i>TargetDevice</i>; otherwise it returns STATUS_NO_SUCH_DEVICE. 




## -remarks



Like <a href="https://msdn.microsoft.com/library/windows/hardware/ff548300">IoAttachDeviceToDeviceStack</a>, <b>IoAttachDeviceToDeviceStackSafe</b> establishes layering between drivers so that the same IRPs are sent to each driver in the stack. However, unlike <b>IoAttachDeviceToDeviceStack</b>, <b>IoAttachDeviceToDeviceStackSafe</b> has an additional parameter, <i>AttachedToDeviceObject</i>, which the filter driver uses to pass the address of the <i>SourceDevice</i> object's AttachedToDeviceObject field. <b>IoAttachDeviceToDeviceStackSafe</b> updates this field while holding the I/O system database lock. Because it holds this lock, <b>IoAttachDeviceToDeviceStackSafe</b> avoids a race condition that could otherwise occur if the <i>SourceDevice</i> object received an IRP before its AttachedToDeviceObject field was updated. 

A file system filter driver calls <b>IoAttachDeviceToDeviceStackSafe</b> to attach its own filter device object (<i>SourceDevice</i>) above a device object (<i>TargetDevice</i>) belonging to a file system or another filter driver. Subsequent I/O requests sent to <i>AttachedToDeviceObject</i> are received first by the filter driver, which processes them and forwards them down to the next driver in the stack by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff548336">IoCallDriver</a>. 

If the device object specified by <i>TargetDevice</i> is currently at the top of the driver stack, the <i>SourceDevice</i> is attached directly to the <i>TargetDevice</i>. In this case, <i>TargetDevice</i> and the returned <i>AttachedToDeviceObject</i> pointer are equal. 

If one or more filter device objects are already attached above the <i>TargetDevice</i> in the driver stack, <b>IoAttachDeviceToDeviceStackSafe</b> attaches the <i>SourceDevice</i> to the topmost filter device object. A pointer to the latter is returned in <i>AttachedToDeviceObject</i>. 

At the moment immediately after it is attached to the top of the stack, the <i>SourceDevice</i> occupies the top of the driver stack. Note, however, that this does not necessarily mean that the <i>SourceDevice</i> will remain at the top of the driver stack. Other filters can attach their own filter device objects above the <i>SourceDevice</i> in the stack. 

<b>IoAttachDeviceToDeviceStackSafe</b> sets the <b>AlignmentRequirement</b> member of the device object pointed to by <i>SourceDevice</i> to the value of the corresponding in the next-lower device object and sets the <b>StackSize</b> in <i>SourceDevice</i> to the value in the next-lower-object plus one. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548300">IoAttachDeviceToDeviceStack</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548336">IoCallDriver</a>
 

 

