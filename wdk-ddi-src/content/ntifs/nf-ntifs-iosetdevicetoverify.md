---
UID: NF:ntifs.IoSetDeviceToVerify
title: IoSetDeviceToVerify function (ntifs.h)
description: Learn more about the IoSetDeviceToVerify routine.
old-location: ifsk\iosetdevicetoverify.htm
tech.root: ifsk
ms.date: 01/18/2023
keywords: ["IoSetDeviceToVerify function"]
ms.keywords: IoSetDeviceToVerify, IoSetDeviceToVerify routine [Installable File System Drivers], ifsk.iosetdevicetoverify, ioref_58eab192-eab0-42ee-8c2b-4fe1ad0fb703.xml, ntifs/IoSetDeviceToVerify
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoSetDeviceToVerify
 - ntifs/IoSetDeviceToVerify
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoSetDeviceToVerify
---

# IoSetDeviceToVerify function

## -description

The **IoSetDeviceToVerify** routine sets the device object to be verified in the specified thread. The specified device object represents a removable media device.

## -parameters

### -param Thread [in]

Pointer to an [**ETHREAD**](/windows-hardware/drivers/kernel/eprocess) thread object structure for the thread.

### -param DeviceObject [in, optional]

Pointer to a [**DEVICE_OBJECT**](../wdm/ns-wdm-_device_object.md) structure that identifies the device object for a removable-media device. **DeviceObject** can be NULL.

## -remarks

*Before using **IoSetDeviceToVerify** and [**IoVerifyVolume**](nf-ntifs-ioverifyvolume.md), driver writers should study the way these routines are used in the FASTFAT sample. For additional information, see also [Supporting Removable Media](/windows-hardware/drivers/kernel/supporting-removable-media).*

**IoSetDeviceToVerify** is called to indicate that a given device object, representing a removable-media device, needs to be verified. Call [**IoGetDeviceToVerify**](nf-ntifs-iogetdevicetoverify.md) to obtain the device object that is the target of the given thread's I/O request.

A file system driver must verify a volume when it receives notification from an underlying removable-media device driver that the media appears to have changed since the last access to the target device. The file system typically calls **IoSetDeviceToVerify** and [**IoVerifyVolume**](nf-ntifs-ioverifyvolume.md) when the lower device returns STATUS_VERIFY_REQUIRED.

## -see-also

[**IRP**](../wdm/ns-wdm-_irp.md)

[**IoGetDeviceToVerify**](nf-ntifs-iogetdevicetoverify.md)

[**IoVerifyVolume**](nf-ntifs-ioverifyvolume.md)

[**PsGetCurrentThread**](../ntddk/nf-ntddk-psgetcurrentthread.md)
