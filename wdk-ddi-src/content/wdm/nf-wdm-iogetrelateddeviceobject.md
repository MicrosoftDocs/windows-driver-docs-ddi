---
UID: NF:wdm.IoGetRelatedDeviceObject
title: IoGetRelatedDeviceObject function (wdm.h)
description: Given a file object, the IoGetRelatedDeviceObject routine returns a pointer to the corresponding device object.
old-location: kernel\iogetrelateddeviceobject.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["IoGetRelatedDeviceObject function"]
ms.keywords: IoGetRelatedDeviceObject, IoGetRelatedDeviceObject routine [Kernel-Mode Driver Architecture], k104_22abf9c6-81f5-497e-9bca-8a00b2c871df.xml, kernel.iogetrelateddeviceobject, wdm/IoGetRelatedDeviceObject
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: <= DISPATCH_LEVEL (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - IoGetRelatedDeviceObject
 - wdm/IoGetRelatedDeviceObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoGetRelatedDeviceObject
---

# IoGetRelatedDeviceObject function


## -description

Given a file object, the <b>IoGetRelatedDeviceObject</b> routine returns a pointer to the corresponding device object.

## -parameters

### -param FileObject 

[in]
Pointer to the file object.

## -returns

<b>IoGetRelatedDeviceObject</b> returns a pointer to the device object.

## -remarks

When called on a file object that represents the underlying storage device, <b>IoGetRelatedDeviceObject</b> returns the highest-level device object in the storage device stack. To obtain the highest-level device object in the file system driver stack, drivers must call <b>IoGetRelatedDeviceObject</b> on a file object that represents the file system's driver stack, and the file system must currently be mounted. (Otherwise, the storage device stack is traversed instead of the file system stack.)

To ensure that the file system is mounted on the storage device, the driver must have specified an appropriate access mask, such as FILE_READ_DATA or FILE_WRITE_ATTRIBUTES, when opening the file or device represented by the file object. Specifying FILE_READ_ATTRIBUTES does not cause the file system to be mounted. 

The caller must be running at IRQL <= DISPATCH_LEVEL. Usually, callers of this routine are running at IRQL = PASSIVE_LEVEL.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdeviceobjectpointer">IoGetDeviceObjectPointer</a>
