---
UID: NF:ntifs.IoGetDeviceToVerify
title: IoGetDeviceToVerify function (ntifs.h)
description: Learn more about the IoGetDeviceToVerify function.
old-location: ifsk\iogetdevicetoverify.htm
tech.root: ifsk
ms.date: 01/18/2023
keywords: ["IoGetDeviceToVerify function"]
ms.keywords: IoGetDeviceToVerify, IoGetDeviceToVerify routine [Installable File System Drivers], ifsk.iogetdevicetoverify, k104_47163b80-0b35-40e0-9a30-3f5e2fe51bba.xml, ntifs/IoGetDeviceToVerify
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows 2000
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
 - IoGetDeviceToVerify
 - ntifs/IoGetDeviceToVerify
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoGetDeviceToVerify
---

# IoGetDeviceToVerify function

## -description

The **IoGetDeviceToVerify** routine returns a pointer to the device object, representing a removable-media device, that is the target of the given thread's I/O request.

## -parameters

### -param Thread [in]

Pointer to an [**ETHREAD**](/windows-hardware/drivers/kernel/eprocess) structure whose device object is being queried. That is, **Thread** is the thread for which a highest-level driver is attempting to verify the validity of the media on which the thread has opened a file.

## -returns

**IoGetDeviceToVerify** returns a pointer to a [**DEVICE_OBJECT**](../wdm/ns-wdm-_device_object.md) structure that identifies the device object representing a device on which the media should be verified. This function can return NULL.

## -remarks

In general, highest-level drivers, particularly file systems, are most likely to call this routine.

An underlying removable-media device driver is responsible for notifying higher-level drivers, particularly the file system, when the media appears to have changed since the last access to the target device. For more information, see [Notifying the File System of Possible Media Changes](/windows-hardware/drivers/kernel/notifying-the-file-system-of-possible-media-changes).

## -see-also

[**IoIsErrorUserInduced**](../wdm/nf-wdm-ioiserroruserinduced.md)

[**IoSetDeviceToVerify**](nf-ntifs-iosetdevicetoverify.md)

[**IoSetHardErrorOrVerifyDevice**](../ntddk/nf-ntddk-iosetharderrororverifydevice.md)

[**PsGetCurrentThread**](../ntddk/nf-ntddk-psgetcurrentthread.md)
