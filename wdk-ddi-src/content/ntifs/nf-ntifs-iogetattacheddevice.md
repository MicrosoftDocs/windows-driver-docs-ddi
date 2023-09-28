---
UID: NF:ntifs.IoGetAttachedDevice
title: IoGetAttachedDevice function (ntifs.h)
description: Learn more about the IoGetAttachedDevice function.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["IoGetAttachedDevice function"]
ms.keywords: IoGetAttachedDevice, IoGetAttachedDevice routine [Installable File System Drivers], ifsk.iogetattacheddevice, ioref_5a77f51f-2bea-4991-bf10-965e6b72e9ab.xml, ntifs/IoGetAttachedDevice
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
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
 - IoGetAttachedDevice
 - ntifs/IoGetAttachedDevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoGetAttachedDevice
---

# IoGetAttachedDevice function

## -description

The **IoGetAttachedDevice** routine returns a pointer to the highest-level device object associated with the specified device.

## -parameters

### -param DeviceObject [in]

A pointer to the device object for which the topmost attached device is to be returned.

## -returns

**IoGetAttachedDevice** returns the highest-level device attached to the specified device.

## -remarks

If the device object specified by **DeviceObject** has no other device objects attached to it, **DeviceObject** and the returned pointer are equal.

**IoGetAttachedDevice** differs from [**IoGetAttachedDeviceReference**](nf-ntifs-iogetattacheddevicereference.md) in the following respects:

* **IoGetAttachedDevice** does not increment the reference count on the device object. (Thus no matching call to [**ObDereferenceObject**](../wdm/nf-wdm-obdereferenceobject.md) is required.)

* Callers of **IoGetAttachedDevice** must ensure that no device objects are added to or removed from the stack while **IoGetAttachedDevice** is executing. Callers that cannot do this must use [**IoGetAttachedDeviceReference**](nf-ntifs-iogetattacheddevicereference.md) instead.

## -see-also

[**IoGetAttachedDeviceReference**](nf-ntifs-iogetattacheddevicereference.md)

[**ObDereferenceObject**](../wdm/nf-wdm-obdereferenceobject.md)
