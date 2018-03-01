---
UID: NF:wdm.IoDisconnectInterrupt
title: IoDisconnectInterrupt function
author: windows-driver-content
description: The IoDisconnectInterrupt routine releases a device driver's set of interrupt object(s) when the device is paused or removed, or when the driver is being unloaded.
old-location: kernel\iodisconnectinterrupt.htm
old-project: kernel
ms.assetid: 06130ec3-7031-4c40-932a-7342c26b7e15
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IoDisconnectInterrupt, IoDisconnectInterrupt routine [Kernel-Mode Driver Architecture], k104_6ed94efc-9513-4ad3-87d0-cec41e912876.xml, kernel.iodisconnectinterrupt, wdm/IoDisconnectInterrupt
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlIoPassive4, PowerIrpDDis, HwStorPortProhibitedDDIs
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
-	IoDisconnectInterrupt
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoDisconnectInterrupt function


## -description


The <b>IoDisconnectInterrupt</b> routine releases a device driver's set of interrupt object(s) when the device is paused or removed, or when the driver is being unloaded.


## -syntax


````
VOID IoDisconnectInterrupt(
  _In_ PKINTERRUPT InterruptObject
);
````


## -parameters




### -param InterruptObject [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554237">KINTERRUPT</a> structure. The caller obtained this pointer from the <a href="..\wdm\nf-wdm-ioconnectinterrupt.md">IoConnectInterrupt</a> call that previously connected the interrupt or interrupts.


## -returns



None.




## -remarks



The driver should configure the device to issue interrupts only when these interrupts are connected. Failure to prevent a device from issuing interrupts when the interrupts are disconnected might cause system instability. For example, if a device shares a level-triggered interrupt line with other devices, and the device issues an interrupt request when the device's interrupts are disconnected, the other devices on the line will not acknowledge the interrupt and the interrupt will continue to fire. Before calling <b>IoDisconnectInterrupt</b>, the driver should configure the device to stop issuing interrupts. After calling <a href="..\wdm\nf-wdm-ioconnectinterrupt.md">IoConnectInterrupt</a>, the driver should configure the device to start issuing interrupts.

If the driver stored the pointer to its interrupt object(s) in the device extension of its device object or in the controller extension of its controller object, it must call <b>IoDisconnectInterrupt</b> before it calls <a href="..\wdm\nf-wdm-iodeletedevice.md">IoDeleteDevice</a> or <a href="..\ntddk\nf-ntddk-iodeletecontroller.md">IoDeleteController</a>. 




## -see-also

<a href="..\ntddk\nf-ntddk-iodeletecontroller.md">IoDeleteController</a>



<a href="..\wdm\nf-wdm-ioconnectinterrupt.md">IoConnectInterrupt</a>



<a href="..\wdm\nf-wdm-iodeletedevice.md">IoDeleteDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554237">KINTERRUPT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoDisconnectInterrupt routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

