---
UID: NF:wdm.IoRegisterShutdownNotification
title: IoRegisterShutdownNotification function
author: windows-driver-content
description: The IoRegisterShutdownNotification routine registers the driver to receive an IRP_MJ_SHUTDOWN IRP when the system is shut down.
old-location: kernel\ioregistershutdownnotification.htm
old-project: kernel
ms.assetid: fd9a612b-b0a7-4bef-9fab-8212a3b594b6
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/IoRegisterShutdownNotification, IoRegisterShutdownNotification routine [Kernel-Mode Driver Architecture], IoRegisterShutdownNotification, kernel.ioregistershutdownnotification, k104_dd357e39-68b4-4cc2-b7c7-34f16c74a4a0.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows. Not available in Microsoft Windows 98/Me.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoRegisterShutdownNotification
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoRegisterShutdownNotification function


## -description


The <b>IoRegisterShutdownNotification</b> routine registers the driver to receive an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549423">IRP_MJ_SHUTDOWN</a> IRP when the system is shut down.


## -syntax


````
NTSTATUS IoRegisterShutdownNotification(
  _In_ PDEVICE_OBJECT DeviceObject
);
````


## -parameters




### -param DeviceObject [in]

Pointer to the device object of the device for which the driver requests shutdown notification. The system passes this pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff543405">DispatchShutdown</a> routine. 


## -returns



<b>IoRegisterShutdownNotification</b> returns STATUS_SUCCESS on success, or the appropriate NTSTATUS error code on failure.




## -remarks



The <b>IoRegisterShutdownNotification</b> routine registers the driver to receive an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549423">IRP_MJ_SHUTDOWN</a> IRP for the specified device when the system shuts down. The driver receives one such IRP for each device it registers to receive notification for. Drivers handle <b>IRP_MJ_SHUTDOWN</b> IRPs within their <a href="https://msdn.microsoft.com/library/windows/hardware/ff543405">DispatchShutdown</a> routines.

If the driver ceases to require shutdown notification for the device, use <a href="..\wdm\nf-wdm-iounregistershutdownnotification.md">IoUnregisterShutdownNotification</a> to remove the driver from the shutdown notification queue.

Only one driver in a device stack should register to receive shutdown notification.

The system sends the driver the <b>IRP_MJ_SHUTDOWN</b> request before it flushes the file systems. Some drivers, such as drivers for mass storage devices, can require shutdown notification after the system flushes the file systems. To receive shutdown notification for a device after the file systems are flushed, use the <a href="..\wdm\nf-wdm-ioregisterlastchanceshutdownnotification.md">IoRegisterLastChanceShutdownNotification</a> routine instead.

The registered <i>DispatchShutdown</i> routine is called before the power manager sends an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551744">IRP_MN_SET_POWER</a> request for <b>PowerSystemShutdown</b>. The <i>DispatchShutdown</i> routine is not called for transitions to any other power states. 

A driver writer can make no assumptions about the order in which the driver's <i>DispatchShutdown</i> routine will be called in relation to other such routines or to other shutdown activities.

A PnP driver might register a shutdown routine to perform certain tasks before system shutdown starts, such as locking down code. 




## -see-also

<a href="..\wdm\nf-wdm-iounregistershutdownnotification.md">IoUnregisterShutdownNotification</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543405">DispatchShutdown</a>



<a href="..\wdm\nf-wdm-ioregisterlastchanceshutdownnotification.md">IoRegisterLastChanceShutdownNotification</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoRegisterShutdownNotification routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

