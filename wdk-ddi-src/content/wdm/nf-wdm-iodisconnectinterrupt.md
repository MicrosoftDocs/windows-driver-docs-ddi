---
UID: NF:wdm.IoDisconnectInterrupt
title: IoDisconnectInterrupt function
author: windows-driver-content
description: The IoDisconnectInterrupt routine releases a device driver's set of interrupt object(s) when the device is paused or removed, or when the driver is being unloaded.
old-location: kernel\iodisconnectinterrupt.htm
tech.root: kernel
ms.assetid: 06130ec3-7031-4c40-932a-7342c26b7e15
ms.date: 04/30/2018
ms.keywords: IoDisconnectInterrupt, IoDisconnectInterrupt routine [Kernel-Mode Driver Architecture], k104_6ed94efc-9513-4ad3-87d0-cec41e912876.xml, kernel.iodisconnectinterrupt, wdm/IoDisconnectInterrupt
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoDisconnectInterrupt function


## -description


The <b>IoDisconnectInterrupt</b> routine releases a device driver's set of interrupt object(s) when the device is paused or removed, or when the driver is being unloaded.


## -parameters




### -param InterruptObject [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554237">KINTERRUPT</a> structure. The caller obtained this pointer from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548371">IoConnectInterrupt</a> call that previously connected the interrupt or interrupts.


## -returns



None.




## -remarks



The driver should configure the device to issue interrupts only when these interrupts are connected. Failure to prevent a device from issuing interrupts when the interrupts are disconnected might cause system instability. For example, if a device shares a level-triggered interrupt line with other devices, and the device issues an interrupt request when the device's interrupts are disconnected, the other devices on the line will not acknowledge the interrupt and the interrupt will continue to fire. Before calling <b>IoDisconnectInterrupt</b>, the driver should configure the device to stop issuing interrupts. After calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff548371">IoConnectInterrupt</a>, the driver should configure the device to start issuing interrupts.

If the driver stored the pointer to its interrupt object(s) in the device extension of its device object or in the controller extension of its controller object, it must call <b>IoDisconnectInterrupt</b> before it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff549083">IoDeleteDevice</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff549078">IoDeleteController</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548371">IoConnectInterrupt</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549078">IoDeleteController</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549083">IoDeleteDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554237">KINTERRUPT</a>
 

 

