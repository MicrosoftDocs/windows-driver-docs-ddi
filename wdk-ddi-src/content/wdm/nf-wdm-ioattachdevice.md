---
UID: NF:wdm.IoAttachDevice
title: IoAttachDevice function
author: windows-driver-content
description: The IoAttachDevice routine attaches the caller's device object to a named target device object, so that I/O requests bound for the target device are routed first to the caller.
old-location: kernel\ioattachdevice.htm
old-project: kernel
ms.assetid: 0227751d-739b-4e0c-84bd-9135f117ec9b
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoAttachDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoAttachDevice
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: IrqlIoPassive1, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoAttachDevice function



## -description
The <b>IoAttachDevice</b> routine attaches the caller's device object to a named target device object, so that I/O requests bound for the target device are routed first to the caller.



## -syntax

````
NTSTATUS IoAttachDevice(
  _In_  PDEVICE_OBJECT  SourceDevice,
  _In_  PUNICODE_STRING TargetDevice,
  _Out_ PDEVICE_OBJECT  *AttachedDevice
);
````


## -parameters

### -param SourceDevice [in]

Pointer to the caller-created device object.


### -param TargetDevice [in]

Pointer to a buffer containing the name of the device object to which the specified <i>SourceDevice</i> is to be attached.


### -param AttachedDevice [out]

Pointer to caller-allocated storage for a pointer. On return, contains a pointer to the target device object if the attachment succeeds.


## -returns
<b>IoAttachDevice</b> can return one of the following NTSTATUS values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
<dt><b>STATUS_OBJECT_NAME_INVALID</b></dt>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>

## -remarks
<b>IoAttachDevice</b> establishes layering between drivers so that the same IRPs can be sent to each driver in the chain.

This routine is used by intermediate drivers during initialization. It allows such a driver to attach its own device object to another device in such a way that any requests being made to the original device are given first to the intermediate driver.

The caller can be layered only at the top of an existing chain of layered drivers. <b>IoAttachDevice</b> searches for the highest device object layered over <i>TargetDevice</i> and attaches to that object (that can be the <i>TargetDevice</i>). Therefore, this routine must not be called if a driver that must be higher-level has already layered itself over the target device.

Note that for file system drivers and drivers in the storage stack, <b>IoAttachDevice</b> opens the target device with FILE_READ_ATTRIBUTES and then calls <a href="..\wdm\nf-wdm-iogetrelateddeviceobject.md">IoGetRelatedDeviceObject</a>. This does not cause a file system to be mounted. Thus, a successful call to <b>IoAttachDevice</b> returns the device object of the storage driver, not that of the file system driver.

This routine sets the <b>AlignmentRequirement</b> in <i>SourceDevice</i> to the value in the next-lower device object and sets the <b>StackSize</b> to the value in the next-lower object plus one.


## -see-also
<dl>
<dt>
<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-ioattachdevicetodevicestack.md">IoAttachDeviceToDeviceStack</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-ioattachdevicetodevicestacksafe.md">IoAttachDeviceToDeviceStackSafe</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iogetrelateddeviceobject.md">IoGetRelatedDeviceObject</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iocreatedevice.md">IoCreateDevice</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iodetachdevice.md">IoDetachDevice</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoAttachDevice routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

