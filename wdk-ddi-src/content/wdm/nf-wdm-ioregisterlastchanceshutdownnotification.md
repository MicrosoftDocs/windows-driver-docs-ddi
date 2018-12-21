---
UID: NF:wdm.IoRegisterLastChanceShutdownNotification
title: IoRegisterLastChanceShutdownNotification function
author: windows-driver-content
description: The IoRegisterLastChanceShutdownNotification routine registers a driver to receive an IRP_MJ_SHUTDOWN IRP when the system is shut down, after all file systems have been flushed.
old-location: kernel\ioregisterlastchanceshutdownnotification.htm
tech.root: kernel
ms.assetid: 9ee590ce-e822-4c15-bb01-6f726268f163
ms.date: 04/30/2018
ms.keywords: IoRegisterLastChanceShutdownNotification, IoRegisterLastChanceShutdownNotification routine [Kernel-Mode Driver Architecture], k104_233a75d7-252b-45e3-a980-bda55edd3fdc.xml, kernel.ioregisterlastchanceshutdownnotification, wdm/IoRegisterLastChanceShutdownNotification
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows. Not available in Microsoft Windows 98/Me.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoRegisterLastChanceShutdownNotification
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoRegisterLastChanceShutdownNotification function


## -description


The <b>IoRegisterLastChanceShutdownNotification</b> routine registers a driver to receive an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549423">IRP_MJ_SHUTDOWN</a> IRP when the system is shut down, after all file systems have been flushed. 


## -parameters




### -param DeviceObject [in]

Pointer to the device object of the device for which the driver requests shutdown notification. The system passes this pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-driver_dispatch">DispatchShutdown</a> routine. 


## -returns



<b>IoRegisterLastChanceShutdownNotification</b> returns STATUS_SUCCESS on success, or the appropriate NTSTATUS error code on failure.




## -remarks



The <b>IoRegisterLastChanceShutdownNotification</b> routine registers the driver to receive an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549423">IRP_MJ_SHUTDOWN</a> IRP for the specified device when the system shuts down. The driver receives one such IRP for each device it registers to receive notification for. Drivers handle <b>IRP_MJ_SHUTDOWN</b> IRPs within their <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-driver_dispatch">DispatchShutdown</a> routines.

For any device that is registered with this routine, the system sends the <b>IRP_MJ_SHUTDOWN</b> IRP after all file systems are flushed. Only one driver in a device stack should register to receive shutdown notification, by calling either <a href="https://msdn.microsoft.com/library/windows/hardware/ff549541">IoRegisterShutdownNotification</a> or <b>IoRegisterLastChanceShutdownNotification</b>.

If the driver ceases to require shutdown notification for that device, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff550409">IoUnregisterShutdownNotification</a> to remove the driver from the shutdown notification queue.

A driver that calls <b>IoRegisterLastChanceShutdownNotification</b> must satisfy the following restrictions in its <i>DispatchShutdown</i> routine:

<ul>
<li>
The <i>DispatchShutdown</i> routine must not call any pageable routines.

</li>
<li>
The <i>DispatchShutdown</i> routine must not access pageable memory.

</li>
<li>
The <i>DispatchShutdown</i> routine must not perform any file I/O operations.

</li>
</ul>
Most drivers that require shutdown notification should call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549541">IoRegisterShutdownNotification</a> routine, which does not impose these limitations on the <i>DispatchShutdown</i> routine, and which causes the <i>DispatchShutdown</i> routine to be called before the file systems are flushed. Only drivers that must do some cleanup after the file systems are flushed, such as a driver for a mass storage device, should use <b>IoRegisterLastChanceShutdownNotification</b>.

The registered <i>DispatchShutdown</i> routine is called before the power manager sends an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551744">IRP_MN_SET_POWER</a> request for <b>PowerSystemShutdown</b>. The <i>DispatchShutdown</i> routine is not called for transitions to any other power states.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-driver_dispatch">DispatchShutdown</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549541">IoRegisterShutdownNotification</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550409">IoUnregisterShutdownNotification</a>
 

 

