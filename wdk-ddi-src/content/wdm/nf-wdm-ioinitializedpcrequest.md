---
UID: NF:wdm.IoInitializeDpcRequest
title: IoInitializeDpcRequest function (wdm.h)
description: The IoInitializeDpcRequest routine registers a driver-supplied DpcForIsr routine.
old-location: kernel\ioinitializedpcrequest.htm
tech.root: kernel
ms.assetid: d4685c23-7461-4539-9f7c-80f9760bf706
ms.date: 04/30/2018
ms.keywords: IoInitializeDpcRequest, IoInitializeDpcRequest routine [Kernel-Mode Driver Architecture], k104_6b13de62-4cbe-4902-8c60-67d873873047.xml, kernel.ioinitializedpcrequest, wdm/IoInitializeDpcRequest
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wdm.h
api_name:
- IoInitializeDpcRequest
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoInitializeDpcRequest function


## -description


The <b>IoInitializeDpcRequest</b> routine registers a driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff544079">DpcForIsr</a> routine.


## -parameters




### -param DeviceObject [in]

Supplies a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure representing the physical device that generates interrupts.


### -param DpcRoutine [in]

Supplies a pointer to the driver-supplied <i>DpcForIsr</i> routine.


## -returns



None




## -remarks



<b>IoInitializeDpcRequest</b> associates a driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff544079">DpcForIsr</a> routine with a given device object. The driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff547958">InterruptService</a> routine (ISR) can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549657">IoRequestDpc</a> to queue the <i>DpcForIsr</i> routine. The <i>DpcForIsr</i> routine completes interrupt-driven I/O operations at a lower IRQL than that of the ISR.

PnP drivers call <b>IoInitializeDpcRequest</b> from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a> routine.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544084">DPC Objects and DPCs</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544079">DpcForIsr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547958">InterruptService</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549657">IoRequestDpc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552130">KeInitializeDpc</a>
 

 

