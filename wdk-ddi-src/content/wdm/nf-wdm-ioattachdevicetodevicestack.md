---
UID: NF:wdm.IoAttachDeviceToDeviceStack
title: IoAttachDeviceToDeviceStack function (wdm.h)
description: The IoAttachDeviceToDeviceStack routine attaches the caller's device object to the highest device object in the chain and returns a pointer to the previously highest device object.
old-location: kernel\ioattachdevicetodevicestack.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["IoAttachDeviceToDeviceStack function"]
ms.keywords: IoAttachDeviceToDeviceStack, IoAttachDeviceToDeviceStack routine [Kernel-Mode Driver Architecture], k104_18c6aeef-4362-49f9-88a3-6d2a970eb0d7.xml, kernel.ioattachdevicetodevicestack, wdm/IoAttachDeviceToDeviceStack
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: AddDevice, PnpSameDeviceObject, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoAttachDeviceToDeviceStack
 - wdm/IoAttachDeviceToDeviceStack
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoAttachDeviceToDeviceStack
---

# IoAttachDeviceToDeviceStack function


## -description

The <b>IoAttachDeviceToDeviceStack</b> routine attaches the caller's device object to the highest device object in the chain and returns a pointer to the previously highest device object.

## -parameters

### -param SourceDevice 

[in]
Pointer to the caller-created device object.

### -param TargetDevice 

[in]
Pointer to another driver's device object, such as a pointer returned by a preceding call to <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdeviceobjectpointer">IoGetDeviceObjectPointer</a>.

## -returns

<b>IoAttachDeviceToDeviceStack</b> returns a pointer to the device object to which the <i>SourceDevice</i> was attached. The returned device object pointer can differ from <i>TargetDevice</i> if <i>TargetDevice</i> had additional drivers layered on top of it.

<b>IoAttachDeviceToDeviceStack</b> returns <b>NULL</b> if it could not attach the device object because, for example, the target device was being unloaded.

## -remarks

<b>IoAttachDeviceToDeviceStack</b> establishes layering between drivers so that the same IRPs are sent to each driver in the chain.

An intermediate driver can use this routine during initialization to attach its own device object to another driver's device object. Subsequent I/O requests sent to <i>TargetDevice</i> are sent first to the intermediate driver.

This routine sets the <b>AlignmentRequirement</b> in <i>SourceDevice</i>  to the value in the next-lower device object and sets the <b>StackSize</b> to the value in the next-lower-object plus one.

A driver writer must take care to call this routine <u>before</u> any drivers that must layer on top of their driver. <b>IoAttachDeviceToDeviceStack</b> attaches <i>SourceDevice</i> to the highest device object currently layered in the chain and has no way to determine whether drivers are being layered in the correct order.

A driver that acquired a pointer to the target device by calling <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdeviceobjectpointer">IoGetDeviceObjectPointer</a> should call <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobject">ObDereferenceObject</a> with the file object pointer that was returned by <b>IoGetDeviceObjectPointer</b> to release its reference to the file object before it detaches its own device object, for example, when such a higher-level driver is unloaded.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioattachdevice">IoAttachDevice</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iodetachdevice">IoDetachDevice</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdeviceobjectpointer">IoGetDeviceObjectPointer</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobject">ObDereferenceObject</a>
