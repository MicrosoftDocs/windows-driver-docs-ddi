---
UID: NF:wdm.IoRequestDpc
title: IoRequestDpc function
author: windows-driver-content
description: The IoRequestDpc routine queues a driver-supplied DpcForIsr routine to complete interrupt-driven I/O processing at a lower IRQL.
old-location: kernel\iorequestdpc.htm
old-project: kernel
ms.assetid: 196555c8-74a6-4dae-ac4d-52654015ffeb
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: k104_37f449eb-de3d-4932-b845-388c73c55d01.xml, wdm/IoRequestDpc, IoRequestDpc, IoRequestDpc routine [Kernel-Mode Driver Architecture], kernel.iorequestdpc
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: DIRQL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	IoRequestDpc
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoRequestDpc function


## -description


The <b>IoRequestDpc</b> routine queues a driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff544079">DpcForIsr</a> routine to complete interrupt-driven I/O processing at a lower IRQL.


## -syntax


````
VOID IoRequestDpc(
  _In_ PDEVICE_OBJECT DeviceObject,
  _In_ PIRP           Irp,
  _In_ PVOID          Context
);
````


## -parameters




### -param DeviceObject [in]

Pointer to the device object for which the request that caused the interrupt is being processed.


### -param Irp [in]

Pointer to the current IRP for the specified device.


### -param Context [in]

Pointer to a driver-determined context to be passed to the DPC routine.


## -returns


None



## -remarks


Callers of <b>IoRequestDpc</b> must be running at DIRQL.

Drivers call  <b>IoRequestDpc</b> from an <a href="https://msdn.microsoft.com/library/windows/hardware/ff547958">InterruptService</a> routine. Because of this, <b>IoRequestDpc</b> runs at the DIRQL value that was specified by <i>SynchronizeIrql</i> when the driver called <a href="..\wdm\nf-wdm-ioconnectinterrupt.md">IoConnectInterrupt</a>. However, it is also possible to queue a DPC at any IRQL &gt;= DISPATCH_LEVEL by using the <b>Ke<i>Xxx</i>Dpc</b> routines. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565664">Which Type of DPC Should You Use?</a>




## -see-also

<a href="..\wdm\nf-wdm-keinsertqueuedpc.md">KeInsertQueueDpc</a>

<a href="..\wdm\nf-wdm-keinitializedpc.md">KeInitializeDpc</a>

<a href="..\wdm\nf-wdm-ioinitializedpcrequest.md">IoInitializeDpcRequest</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoRequestDpc routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

