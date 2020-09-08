---
UID: NF:ntifs.IoSetDeviceToVerify
title: IoSetDeviceToVerify function (ntifs.h)
description: The IoSetDeviceToVerify routine specifies a device object to be verified. The specified device object represents a removable media device.
old-location: ifsk\iosetdevicetoverify.htm
tech.root: ifsk
ms.assetid: 509eb91d-7f34-4ebb-bc37-56889c15a1b3
ms.date: 04/16/2018
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

The <b>IoSetDeviceToVerify</b> routine specifies a device object to be verified. The specified device object represents a removable media device.

## -parameters

### -param Thread 

[in]
A pointer to the thread.

### -param DeviceObject 

[in, optional]
A pointer to the device object for a removable-media device. Can be <b>NULL</b>.

## -remarks

A file system calls <b>IoSetDeviceToVerify</b> to indicate that a given device object, representing a removable-media device, needs to be verified.

A file system must verify a volume when it receives notification from an underlying removable-media device driver that the media appears to have changed since the last access to the target device. 

Before using <b>IoSetDeviceToVerify</b> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioverifyvolume">IoVerifyVolume</a>, driver writers are strongly encouraged to study the way these routines are used in the FASTFAT sample.

For more information about removable-media devices, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/supporting-removable-media">Supporting Removable Media</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iogetdevicetoverify">IoGetDeviceToVerify</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioverifyvolume">IoVerifyVolume</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psgetcurrentthread">PsGetCurrentThread</a>

