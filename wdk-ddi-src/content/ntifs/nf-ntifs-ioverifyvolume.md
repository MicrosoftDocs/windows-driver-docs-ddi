---
UID: NF:ntifs.IoVerifyVolume
title: IoVerifyVolume function (ntifs.h)
description: Learn more about the IoVerifyVolume function.
old-location: ifsk\ioverifyvolume.htm
tech.root: ifsk
ms.date: 01/18/2023
keywords: ["IoVerifyVolume function"]
ms.keywords: IoVerifyVolume, IoVerifyVolume routine [Installable File System Drivers], ifsk.ioverifyvolume, ioref_b55e7a87-a18d-4ccd-ab32-061676c9dde4.xml, ntifs/IoVerifyVolume
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
req.irql: < DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoVerifyVolume
 - ntifs/IoVerifyVolume
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoVerifyVolume
---

# IoVerifyVolume function

## -description

**IoVerifyVolume** sends a volume verify request to the specified removable-media device identified by the device object.

## -parameters

### -param DeviceObject [in]

Pointer to a [**DEVICE_OBJECT**](../wdm/ns-wdm-_device_object.md) structure that identifies the device object for the device on which the volume is to be verified/mounted.

### -param AllowRawMount [in]

A value of TRUE indicates that this verify request is being issued on behalf of a DASD (direct-access storage device) open request, which indicates that a raw mount should be performed if the verify request fails.

## -returns

**IoVerifyVolume** returns the NTSTATUS code from the verify operation, which might be one of the following values:

| Return code | Description |
| ----------- | ----------- |
| STATUS_SUCCESS                | **IoVerifyVolume** determined that the volume has not changed or was not previously mounted. |
| STATUS_INSUFFICIENT_RESOURCES | Insufficient system resources exist to complete the operation. |
| STATUS_UNSUCCESSFUL           | The verify operation was unsuccessful. |
| STATUS_WRONG_VOLUME           | The volume has changed. |

## -remarks

*Before using [**IoSetDeviceToVerify**](nf-ntifs-iosetdevicetoverify.md) and **IoVerifyVolume**, driver writers should study the way these routines are used in the [FASTFAT sample](/samples/microsoft/windows-driver-samples/fastfat-file-system-driver).*

**IoVerifyVolume** is called to check a mounted volume on the specified device when it appears that the volume might have changed since it was last accessed. A file system driver typically calls [**IoSetDeviceToVerify**](nf-ntifs-iosetdevicetoverify.md) and  **IoVerifyVolume** when the lower device returns STATUS_VERIFY_REQUIRED.

If the **DeviceObject** has a mounted volume, **IoVerifyVolume** checks whether the volume has changed.

If the volume has changed or has not previously been mounted, **IoVerifyVolume** sends a volume mount request to the device.

For more information about removable-media devices, see [Supporting Removable Media](/windows-hardware/drivers/kernel/supporting-removable-media).

## -see-also

[**IoGetDeviceToVerify**](nf-ntifs-iogetdevicetoverify.md)

[**IoSetDeviceToVerify**](nf-ntifs-iosetdevicetoverify.md)
