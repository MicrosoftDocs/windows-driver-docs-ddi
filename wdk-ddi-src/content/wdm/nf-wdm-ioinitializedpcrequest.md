---
UID: NF:wdm.IoInitializeDpcRequest
title: IoInitializeDpcRequest function (wdm.h)
description: The IoInitializeDpcRequest routine registers a driver-supplied DpcForIsr routine.
old-location: kernel\ioinitializedpcrequest.htm
tech.root: kernel
ms.assetid: d4685c23-7461-4539-9f7c-80f9760bf706
ms.date: 04/30/2018
keywords: ["IoInitializeDpcRequest function"]
ms.keywords: IoInitializeDpcRequest, IoInitializeDpcRequest routine [Kernel-Mode Driver Architecture], k104_6b13de62-4cbe-4902-8c60-67d873873047.xml, kernel.ioinitializedpcrequest, wdm/IoInitializeDpcRequest
f1_keywords:
 - "wdm/IoInitializeDpcRequest"
 - "IoInitializeDpcRequest"
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
targetos: Windows
req.typenames: 
---

# IoInitializeDpcRequest function


## -description


The <b>IoInitializeDpcRequest</b> routine registers a driver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_dpc_routine">DpcForIsr</a> routine.


## -parameters




### -param DeviceObject 
[in]
Supplies a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure representing the physical device that generates interrupts.


### -param DpcRoutine 
[in]
Supplies a pointer to the driver-supplied <i>DpcForIsr</i> routine.


## -remarks



<b>IoInitializeDpcRequest</b> associates a driver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_dpc_routine">DpcForIsr</a> routine with a given device object. The driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-kservice_routine">InterruptService</a> routine (ISR) can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iorequestdpc">IoRequestDpc</a> to queue the <i>DpcForIsr</i> routine. The <i>DpcForIsr</i> routine completes interrupt-driven I/O operations at a lower IRQL than that of the ISR.

PnP drivers call <b>IoInitializeDpcRequest</b> from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device">AddDevice</a> routine.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/dpc-objects-and-dpcs">DPC Objects and DPCs</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device">AddDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_dpc_routine">DpcForIsr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-kservice_routine">InterruptService</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iorequestdpc">IoRequestDpc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializedpc">KeInitializeDpc</a>
 

 

