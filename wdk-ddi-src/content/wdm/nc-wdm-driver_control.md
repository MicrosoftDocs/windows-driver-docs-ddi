---
UID: NC:wdm.DRIVER_CONTROL
title: DRIVER_CONTROL
author: windows-driver-content
description: The AdapterControl routine starts a DMA data-transfer operation.
old-location: kernel\adaptercontrol.htm
old-project: Benchmark
ms.assetid: b75b8937-793d-4d75-9bb7-2226096044f0
ms.author: windowsdriverdev
ms.date: 1/12/2018
ms.keywords: kernel.adaptercontrol, AdapterControl routine [Kernel-Mode Driver Architecture], AdapterControl, DRIVER_CONTROL, DRIVER_CONTROL, wdm/AdapterControl, DrvrRtns_1e3fb66d-8977-4894-a3ac-d310fdfa6515.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.irql: Called at DISPATCH_LEVEL.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdm.h
apiname:
-	AdapterControl
product: Windows
targetos: Windows
req.typenames: "*PWDBGEXTS_THREAD_OS_INFO, WDBGEXTS_THREAD_OS_INFO"
---

# DRIVER_CONTROL callback


## -description


The <i>AdapterControl</i> routine starts a DMA data-transfer operation. 


## -prototype


````
DRIVER_CONTROL AdapterControl;

IO_ALLOCATION_ACTION AdapterControl(
  _In_    struct _DEVICE_OBJECT *DeviceObject,
  _Inout_ struct _IRP           *Irp,
  _In_    PVOID                 MapRegisterBase,
  _In_    PVOID                 Context
)
{ ... }
````


## -parameters




### -param DeviceObject [in]

Caller-supplied pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure. This is the device object for the target device, previously created by the driver's <i>AddDevice</i> routine.


### -param Irp [in, out]

Caller-supplied pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a> structure. <i>Irp</i> is equal to the value of the <b>CurrentIrp</b> member of <i>DeviceObject</i> when the <i>AdapterControl</i> routine was registered.


### -param MapRegisterBase [in]

Caller-supplied opaque value that represents  the map registers that the system has assigned for this transfer operation. The driver passes this value to <a href="https://msdn.microsoft.com/library/windows/hardware/ff545917">FlushAdapterBuffers</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff546513">FreeMapRegisters</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff554402">MapTransfer</a>.


### -param Context [in]

Caller-supplied pointer to driver-defined context information, specified in a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff540573">AllocateAdapterChannel</a>.


## -returns


The routine must return one of the values defined by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550534">IO_ALLOCATION_ACTION</a> enumeration. Drivers of bus-master devices return either <b>DeallocateObject</b> or <b>DeallocateObjectKeepRegisters</b>; drivers that use system DMA return <b>KeepObject</b>.



## -remarks


To register an <i>AdapterControl</i> routine for a specific device object, a driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> to obtain an adapter object, then call <a href="https://msdn.microsoft.com/library/windows/hardware/ff540573">AllocateAdapterChannel</a> to request use of the adapter and to supply the <i>AdapterControl</i> routine's address. When the adapter is free, the system calls the <i>AdapterControl</i> routine.

If <i>AdapterControl</i> has been registered by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563858">StartIo</a> routine, then the <i>Irp</i> parameter is guaranteed to point to the IRP currently being processed by the <i>StartIo</i> routine. Otherwise, drivers must set the <b>CurrentIrp</b> member of the device object structure before calling <b>AllocateAdapterChannel</b>.

For detailed information about implementing an <i>AdapterControl</i> routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff566397">Writing AdapterControl Routines</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540573">AllocateAdapterChannel</a>

 

 

