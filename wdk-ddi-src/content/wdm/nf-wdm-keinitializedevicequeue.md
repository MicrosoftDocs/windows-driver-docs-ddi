---
UID: NF:wdm.KeInitializeDeviceQueue
title: KeInitializeDeviceQueue function (wdm.h)
description: The KeInitializeDeviceQueue routine initializes a device queue object to a not-busy state.
old-location: kernel\keinitializedevicequeue.htm
tech.root: kernel
ms.assetid: 0df0fcba-9ae8-4c69-957a-5685ea40c378
ms.date: 04/30/2018
keywords: ["KeInitializeDeviceQueue function"]
ms.keywords: KeInitializeDeviceQueue, KeInitializeDeviceQueue routine [Kernel-Mode Driver Architecture], k105_5d7ea571-8c88-45f7-917c-e42e6caac514.xml, kernel.keinitializedevicequeue, wdm/KeInitializeDeviceQueue
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlKeDispatchLte, HwStorPortProhibitedDDIs
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
 - KeInitializeDeviceQueue
 - wdm/KeInitializeDeviceQueue
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeInitializeDeviceQueue
---

# KeInitializeDeviceQueue function


## -description

The <b>KeInitializeDeviceQueue</b> routine initializes a device queue object to a not-busy state.

## -parameters

### -param DeviceQueue 

[out]
Pointer to a device queue object for which the caller provides the storage.

## -remarks

<b>KeInitializeDeviceQueue</b> initializes the specified device queue and sets its state to not-busy.

A driver should call <b>KeInitializeDeviceQueue</b> from its <i>AddDevice</i> routine after creating the device object for the associated device. Storage for the device queue object must be resident: in the device extension of a driver-created device object, in the controller extension of a driver-created controller object, or in nonpaged pool allocated by the caller.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keinsertbykeydevicequeue">KeInsertByKeyDeviceQueue</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keinsertdevicequeue">KeInsertDeviceQueue</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keremovedevicequeue">KeRemoveDeviceQueue</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keremoveentrydevicequeue">KeRemoveEntryDeviceQueue</a>