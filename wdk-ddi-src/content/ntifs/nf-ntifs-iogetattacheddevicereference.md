---
UID: NF:ntifs.IoGetAttachedDeviceReference
title: IoGetAttachedDeviceReference function (ntifs.h)
description: Learn more about the IoGetAttachedDeviceReference routine.
tech.root: kernel
ms.date: 07/06/2023
keywords: ["IoGetAttachedDeviceReference function"]
ms.keywords: IoGetAttachedDeviceReference, kernel.iogetattacheddevicereference, wdm/IoGetAttachedDeviceReference
req.header: ntifs.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows 2000
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: DanglingDeviceObjectReference, HwStorPortProhibitedDDIs
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
 - IoGetAttachedDeviceReference
 - ntifs/IoGetAttachedDeviceReference
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoGetAttachedDeviceReference
---

# IoGetAttachedDeviceReference function (ntifs.h)

## -description

The **IoGetAttachedDeviceReference** routine returns a pointer to the highest level device object in a driver stack and increments the reference count on that object.

## -parameters

### -param DeviceObject [in]

Pointer to the device object for which the topmost attached device object is retrieved.

## -returns

**IoGetAttachedDeviceReference** returns a pointer to the highest level device object in a stack of attached device objects after incrementing the reference count on the object.

## -remarks

If the device object at **DeviceObject** has no device objects attached to it, **DeviceObject** and the returned pointer are equal.

Device driver writers must ensure that when they have completed all operations that required them to make this call, that they call [**ObDereferenceObject**](../wdm/nf-wdm-obdereferenceobject.md) with the device object pointer returned by this routine. Failure to do so will prevent the system from freeing or deleting the device object because of an outstanding reference count.

## -see-also

[**ObDereferenceObject**](../wdm/nf-wdm-obdereferenceobject.md)
