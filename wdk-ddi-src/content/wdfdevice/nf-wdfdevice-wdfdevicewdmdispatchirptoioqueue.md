---
UID: NF:wdfdevice.WdfDeviceWdmDispatchIrpToIoQueue
title: WdfDeviceWdmDispatchIrpToIoQueue function (wdfdevice.h)
description: The WdfDeviceWdmDispatchIrpToIoQueue method forwards the IRP to a specified I/O queue.
old-location: wdf\wdfdevicewdmdispatchirptoioqueue.htm
tech.root: wdf
ms.assetid: 5D1B228D-81D9-47FE-8CF2-41AAD9148667
ms.date: 02/26/2018
ms.keywords: WdfDeviceWdmDispatchIrpToIoQueue, WdfDeviceWdmDispatchIrpToIoQueue method, kmdf.wdfdevicewdmdispatchirptoioqueue, kmdf.wdfdevicewdmforwardirptoioqueue, wdf.wdfdevicewdmdispatchirptoioqueue, wdfdevice/WdfDeviceWdmDispatchIrpToIoQueue
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 2.17
req.ddi-compliance: DriverCreate, FwdIrpToIoQueueValid
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
- WUDFx02000.dll
- WUDFx02000.dll.dll
api_name:
- WdfDeviceWdmDispatchIrpToIoQueue
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceWdmDispatchIrpToIoQueue function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfDeviceWdmDispatchIrpToIoQueue</b> method forwards the IRP to a specified I/O queue.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param Irp [in]

A pointer to an IRP structure.


### -param Queue [in]

A handle to a framework queue object.


### -param Flags [in]

A bitwise <b>OR</b> of <a href="https://msdn.microsoft.com/library/windows/hardware/hh439503">WDF_DISPATCH_IRP_TO_IO_QUEUE_FLAGS</a>-typed flags.


## -returns



The <b>WdfDeviceWdmDispatchIrpToIoQueue</b> method returns an NTSTATUS value that the framework or the driver provides as a result of processing the IRP. The driver must use this return value as the return value for the <a href="https://msdn.microsoft.com/C6BED59F-066E-42F6-86AE-B0423E0E847F">EvtDeviceWdmIrpDispatch</a> or the <a href="https://msdn.microsoft.com/aff9cb60-d61b-47a8-aae4-6ffd2a1b7a9a">EvtDeviceWdmIrpPreprocess</a> callback function that called <b>WdfDeviceWdmDispatchIrpToIoQueue</b>.

A bug check occurs if a KMDF  driver supplies an invalid object handle.  If a UMDF driver supplies an invalid handle, the driver host process terminates.




## -remarks



A driver calls <b>WdfDeviceWdmDispatchIrpToIoQueue</b> to specify a target queue for an incoming IRP.

The driver can call this method from its <a href="https://msdn.microsoft.com/aff9cb60-d61b-47a8-aae4-6ffd2a1b7a9a">EvtDeviceWdmIrpPreprocess</a> callback routine or from its <a href="https://msdn.microsoft.com/C6BED59F-066E-42F6-86AE-B0423E0E847F">EvtDeviceWdmIrpDispatch</a> callback.

If the driver calls <b>WdfDeviceWdmDispatchIrpToIoQueue</b> from within a <a href="https://msdn.microsoft.com/aff9cb60-d61b-47a8-aae4-6ffd2a1b7a9a">EvtDeviceWdmIrpPreprocess</a> callback function, the driver must call either <a href="https://msdn.microsoft.com/library/windows/hardware/ff550355">IoSkipCurrentIrpStackLocation</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548387">IoCopyCurrentIrpStackLocationToNext</a> prior to calling  <b>WdfDeviceWdmDispatchIrpToIoQueue</b>.

 For more information about specifying queues for IRPs as they arrive, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dispatching-irps-to-i-o-queues">Dispatching IRPs to I/O Queues</a>.




## -see-also




<a href="https://msdn.microsoft.com/C6BED59F-066E-42F6-86AE-B0423E0E847F">EvtDeviceWdmIrpDispatch</a>



<a href="https://msdn.microsoft.com/aff9cb60-d61b-47a8-aae4-6ffd2a1b7a9a">EvtDeviceWdmIrpPreprocess</a>
 

 

