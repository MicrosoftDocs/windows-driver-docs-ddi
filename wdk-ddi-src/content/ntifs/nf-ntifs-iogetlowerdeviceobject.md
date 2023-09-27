---
UID: NF:ntifs.IoGetLowerDeviceObject
title: IoGetLowerDeviceObject function (ntifs.h)
description: Learn more about the IoGetLowerDeviceObject function.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["IoGetLowerDeviceObject function"]
ms.keywords: IoGetLowerDeviceObject, IoGetLowerDeviceObject routine [Installable File System Drivers], ifsk.iogetlowerdeviceobject, ioref_0739069f-c14d-4b35-accd-8d65954bbc3d.xml, ntifs/IoGetLowerDeviceObject
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows 2000 SP4 Update Rollup; Windows XP
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoGetLowerDeviceObject
 - ntifs/IoGetLowerDeviceObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoGetLowerDeviceObject
---

# IoGetLowerDeviceObject function

## -description

The **IoGetLowerDeviceObject** routine returns a pointer to the next-lower-level device object on the driver stack.

## -parameters

### -param DeviceObject [in]

A pointer to the device object in the stack for which the next-lower-level device object is to be returned.

## -returns

**IoGetLowerDeviceObject** returns a pointer to the next-lower-level device object on the driver stack.

## -remarks

Given a pointer to a device object in a file system or device driver stack, **IoGetLowerDeviceObject** returns a pointer to the next-lower-level device object on the stack.

**IoGetLowerDeviceObject** returns NULL if:

* The next-lower-level driver is not loaded.

* The next-lower-level driver is currently being unloaded, removed, or deleted.

* The device object pointed to by **DeviceObject** is the lowest device object in the driver stack.

A file system filter driver typically uses **IoGetLowerDeviceObject** to determine whether it is already attached to the filter driver stack that is chained above a given file system device object. First, the filter calls [**IoGetAttachedDeviceReference**](nf-ntifs-iogetattacheddevicereference.md) to get a pointer to the topmost device object in the stack. Then it calls **IoGetLowerDeviceObject** repeatedly to walk the driver stack, checking each device object to see whether the object belongs to the filter driver.

**IoGetLowerDeviceObject** increments the reference count on the next-lower-level device object. Thus every successful call to **IoGetLowerDeviceObject** must be matched by a subsequent call [**ObDereferenceObject**](../wdm/nf-wdm-obdereferenceobject.md).

## -see-also

[**IoGetAttachedDevice**](nf-ntifs-iogetattacheddevice.md)

[**IoGetAttachedDeviceReference**](nf-ntifs-iogetattacheddevicereference.md)

[**ObDereferenceObject**](../wdm/nf-wdm-obdereferenceobject.md)
