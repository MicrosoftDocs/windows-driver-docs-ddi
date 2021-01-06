---
UID: NF:wdm.IoDetachDevice
title: IoDetachDevice function (wdm.h)
description: The IoDetachDevice routine releases an attachment between the caller's device object and a lower driver's device object.
old-location: kernel\iodetachdevice.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["IoDetachDevice function"]
ms.keywords: IoDetachDevice, IoDetachDevice routine [Kernel-Mode Driver Architecture], k104_e928372b-1222-4421-bea7-c2457c38a09f.xml, kernel.iodetachdevice, wdm/IoDetachDevice
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlIoPassive3, PnpSurpriseRemove, PowerIrpDDis, RemoveLockCheck, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoDetachDevice
 - wdm/IoDetachDevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoDetachDevice
---

# IoDetachDevice function


## -description

The <b>IoDetachDevice</b> routine releases an attachment between the caller's device object and a lower driver's device object.

## -parameters

### -param TargetDevice 

[in, out]
Pointer to the lower driver's device object. The caller previously called <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioattachdevice">IoAttachDevice</a> or <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioattachdevicetodevicestack">IoAttachDeviceToDeviceStack</a> successfully to get this pointer.

## -remarks

<b>IoDetachDevice</b> decrements the reference count of the <i>TargetDevice</i> object. If the reference count goes to zero and the lower driver has been marked for an unload operation, the lower driver is unloaded.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioattachdevice">IoAttachDevice</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioattachdevicetodevicestack">IoAttachDeviceToDeviceStack</a>
