---
UID: NF:wdm.IoUnregisterShutdownNotification
title: IoUnregisterShutdownNotification function (wdm.h)
description: The IoUnregisterShutdownNotification routine removes a registered driver from the shutdown notification queue.
old-location: kernel\iounregistershutdownnotification.htm
tech.root: kernel
ms.assetid: b48a38ff-60b9-4c01-ac71-4ae07010db1f
ms.date: 04/30/2018
keywords: ["IoUnregisterShutdownNotification function"]
ms.keywords: IoUnregisterShutdownNotification, IoUnregisterShutdownNotification routine [Kernel-Mode Driver Architecture], k104_f242a3dc-8338-4d64-bad7-0cca78c30a45.xml, kernel.iounregistershutdownnotification, wdm/IoUnregisterShutdownNotification
f1_keywords:
 - "wdm/IoUnregisterShutdownNotification"
 - "IoUnregisterShutdownNotification"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlIoPassive5, PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoUnregisterShutdownNotification
targetos: Windows
req.typenames: 
---

# IoUnregisterShutdownNotification function


## -description


The <b>IoUnregisterShutdownNotification</b> routine removes a registered driver from the shutdown notification queue.


## -parameters




### -param DeviceObject 
[in]
Pointer to the driver's device object.


## -remarks



<b>IoUnregisterShutdownNotification</b> can be called by a driver only if that driver previously called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioregistershutdownnotification">IoRegisterShutdownNotification</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioregisterlastchanceshutdownnotification">IoRegisterLastChanceShutdownNotification</a> with the given <i>DeviceObject</i>. This routine is usually called from a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_unload">Unload</a> routine.

Calling <b>IoUnregisterShutdownNotification</b> cancels all shutdown notifications that have been registered for the given <i>DeviceObject</i>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioregisterlastchanceshutdownnotification">IoRegisterLastChanceShutdownNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioregistershutdownnotification">IoRegisterShutdownNotification</a>
 

 

