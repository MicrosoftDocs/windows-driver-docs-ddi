---
UID: NF:wdm.IoInitializeDpcRequest
title: IoInitializeDpcRequest function
author: windows-driver-content
description: The IoInitializeDpcRequest routine registers a driver-supplied DpcForIsr routine.
old-location: kernel\ioinitializedpcrequest.htm
old-project: kernel
ms.assetid: d4685c23-7461-4539-9f7c-80f9760bf706
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , D, I, IoInitializeDpcRequest, IoInitializeDpcRequest routine [Kernel-Mode Driver Architecture], R, a, c, e, i, k104_6b13de62-4cbe-4902-8c60-67d873873047.xml, kernel.ioinitializedpcrequest, l, n, o, p, q, s, t, u, wdm/IoInitializeDpcRequest, z"
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
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	IoInitializeDpcRequest
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoInitializeDpcRequest function


## -description


The <b>IoInitializeDpcRequest</b> routine registers a driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff544079">DpcForIsr</a> routine.


## -syntax


````
VOID IoInitializeDpcRequest(
  _In_ PDEVICE_OBJECT  DeviceObject,
  _In_ PIO_DPC_ROUTINE DpcRoutine
);
````


## -parameters




### -param DeviceObject [in]

Supplies a pointer to the <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure representing the physical device that generates interrupts.


### -param DpcRoutine [in]

Supplies a pointer to the driver-supplied <i>DpcForIsr</i> routine.


## -returns



None




## -remarks



<b>IoInitializeDpcRequest</b> associates a driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff544079">DpcForIsr</a> routine with a given device object. The driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff547958">InterruptService</a> routine (ISR) can call <a href="..\wdm\nf-wdm-iorequestdpc.md">IoRequestDpc</a> to queue the <i>DpcForIsr</i> routine. The <i>DpcForIsr</i> routine completes interrupt-driven I/O operations at a lower IRQL than that of the ISR.

PnP drivers call <b>IoInitializeDpcRequest</b> from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a> routine.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544084">DPC Objects and DPCs</a>.




## -see-also

<a href="..\wdm\nf-wdm-keinitializedpc.md">KeInitializeDpc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547958">InterruptService</a>



<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544079">DpcForIsr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a>



<a href="..\wdm\nf-wdm-iorequestdpc.md">IoRequestDpc</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoInitializeDpcRequest routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

