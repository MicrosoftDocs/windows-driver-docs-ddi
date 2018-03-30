---
UID: NF:wdm.IoForwardIrpSynchronously
title: IoForwardIrpSynchronously function
author: windows-driver-content
description: The IoForwardIrpSynchronously routine sends an IRP to a specified driver and waits for that driver to complete the IRP.
old-location: kernel\ioforwardirpsynchronously.htm
old-project: kernel
ms.assetid: c3e7c79f-2a0d-4011-887d-0f01537cd6e6
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: IoForwardIrpSynchronously, IoForwardIrpSynchronously routine [Kernel-Mode Driver Architecture], k104_130c736e-6408-4484-b306-91ba275eaac0.xml, kernel.ioforwardirpsynchronously, wdm/IoForwardIrpSynchronously
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PnpIrpCompletion
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoForwardIrpSynchronously
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoForwardIrpSynchronously function


## -description


The <b>IoForwardIrpSynchronously</b> routine sends an IRP to a specified driver and waits for that driver to complete the IRP.


## -parameters




### -param DeviceObject [in]

Specifies the device object of the driver to which the IRP is sent. 


### -param Irp [in]

Specifies the IRP to send. 


## -returns



<b>IoForwardIrpSynchronously</b> returns <b>TRUE</b> if the IRP is sent successfully. Otherwise, it returns <b>FALSE</b>.




## -remarks



Use the <b>IoForwardIrpSynchronously</b> routine to synchronously forward the current IRP to the next driver in the stack. (To asynchronously forward the IRP, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548387">IoCopyCurrentIrpStackLocationToNext</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff548336">IoCallDriver</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff549679">IoSetCompletionRoutine</a> routines.)

The <b>IoForwardIrpSynchronously</b> routine copies the current stack location to the next stack location. That stack location is then used as the current stack location by the driver specified in <i>DeviceObject</i>. If no next stack location is available, the routine returns <b>FALSE</b>. If the routine returns <b>TRUE</b>, then the IRP has been sent to the specified driver, and that driver has completed its processing of this IRP. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548336">IoCallDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548387">IoCopyCurrentIrpStackLocationToNext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549679">IoSetCompletionRoutine</a>
 

 

