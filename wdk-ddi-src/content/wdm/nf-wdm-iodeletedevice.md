---
UID: NF:wdm.IoDeleteDevice
title: IoDeleteDevice function (wdm.h)
description: The IoDeleteDevice routine removes a device object from the system, for example, when the underlying device is removed from the system.
old-location: kernel\iodeletedevice.htm
tech.root: kernel
ms.assetid: 973549c3-c570-48ab-9a82-9398c920dbd9
ms.date: 04/30/2018
ms.keywords: IoDeleteDevice, IoDeleteDevice routine [Kernel-Mode Driver Architecture], k104_246c1fe6-75cc-434e-a1d4-7e573eff96de.xml, kernel.iodeletedevice, wdm/IoDeleteDevice
ms.topic: function
f1_keywords:
 - "wdm/IoDeleteDevice"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: DeleteDevice, IrqlIoApcLte, PnpSurpriseRemove, RemoveLockCheck, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoDeleteDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoDeleteDevice function


## -description


The <b>IoDeleteDevice</b> routine removes a device object from the system, for example, when the underlying device is removed from the system. 


## -parameters




### -param DeviceObject [in]

Pointer to the device object to be deleted. 


## -returns



None




## -remarks



When handling a PnP <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-remove-device">IRP_MN_REMOVE_DEVICE</a> request, a PnP driver calls <b>IoDeleteDevice</b> to delete any associated device objects. See <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/handling-an-irp-mn-remove-device-request">Handling an IRP_MN_REMOVE_DEVICE Request</a> for details.

A legacy driver should call this routine when it is being unloaded or when its <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine encounters a fatal initialization error, such as being unable to properly initialize a physical device. This routine also is called when a driver reconfigures its devices dynamically. For example, a disk driver called to repartition a disk would call <b>IoDeleteDevice</b> to tear down the device objects representing partitions to be replaced.

A driver must release certain resources for which the driver supplied storage in its device extension before it calls <b>IoDeleteDevice</b>. For example, if the driver stores the pointer to its interrupt object(s) in the device extension, it must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iodisconnectinterrupt">IoDisconnectInterrupt</a> before calling <b>IoDeleteDevice</b>.

A driver can call <b>IoDeleteDevice</b> only once for a given device object.

When a driver calls <b>IoDeleteDevice</b>, the I/O manager deletes the target device object if there are no outstanding references to it. However, if any outstanding references remain, the I/O manager marks the device object as "delete pending" and deletes the device object when the references are released.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iocreatedevice">IoCreateDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iodisconnectinterrupt">IoDisconnectInterrupt</a>
 

 

