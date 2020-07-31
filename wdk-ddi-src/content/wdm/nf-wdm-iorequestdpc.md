---
UID: NF:wdm.IoRequestDpc
title: IoRequestDpc function (wdm.h)
description: The IoRequestDpc routine queues a driver-supplied DpcForIsr routine to complete interrupt-driven I/O processing at a lower IRQL.
old-location: kernel\iorequestdpc.htm
tech.root: kernel
ms.assetid: 196555c8-74a6-4dae-ac4d-52654015ffeb
ms.date: 04/30/2018
keywords: ["IoRequestDpc function"]
ms.keywords: IoRequestDpc, IoRequestDpc routine [Kernel-Mode Driver Architecture], k104_37f449eb-de3d-4932-b845-388c73c55d01.xml, kernel.iorequestdpc, wdm/IoRequestDpc
f1_keywords:
 - "wdm/IoRequestDpc"
 - "IoRequestDpc"
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
req.irql: DIRQL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wdm.h
api_name:
- IoRequestDpc
targetos: Windows
req.typenames: 
---

# IoRequestDpc function


## -description


The <b>IoRequestDpc</b> routine queues a driver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_dpc_routine">DpcForIsr</a> routine to complete interrupt-driven I/O processing at a lower IRQL.


## -parameters




### -param DeviceObject [in]

Pointer to the device object for which the request that caused the interrupt is being processed.


### -param Irp [in]

Pointer to the current IRP for the specified device.


### -param Context [in]

Pointer to a driver-determined context to be passed to the DPC routine.


## -remarks



Callers of <b>IoRequestDpc</b> must be running at DIRQL.

Drivers call  <b>IoRequestDpc</b> from an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-kservice_routine">InterruptService</a> routine. Because of this, <b>IoRequestDpc</b> runs at the DIRQL value that was specified by <i>SynchronizeIrql</i> when the driver called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioconnectinterrupt">IoConnectInterrupt</a>. However, it is also possible to queue a DPC at any IRQL >= DISPATCH_LEVEL by using the <b>Ke<i>Xxx</i>Dpc</b> routines. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/which-type-of-dpc-should-you-use-">Which Type of DPC Should You Use?</a>





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioinitializedpcrequest">IoInitializeDpcRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializedpc">KeInitializeDpc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinsertqueuedpc">KeInsertQueueDpc</a>
 

 

