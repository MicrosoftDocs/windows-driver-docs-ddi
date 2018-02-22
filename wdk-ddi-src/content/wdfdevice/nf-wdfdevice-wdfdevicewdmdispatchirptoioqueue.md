---
UID: NF:wdfdevice.WdfDeviceWdmDispatchIrpToIoQueue
title: WdfDeviceWdmDispatchIrpToIoQueue function
author: windows-driver-content
description: The WdfDeviceWdmDispatchIrpToIoQueue method forwards the IRP to a specified I/O queue.
old-location: wdf\wdfdevicewdmdispatchirptoioqueue.htm
old-project: wdf
ms.assetid: 5D1B228D-81D9-47FE-8CF2-41AAD9148667
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: kmdf.wdfdevicewdmdispatchirptoioqueue, wdfdevice/WdfDeviceWdmDispatchIrpToIoQueue, wdf.wdfdevicewdmdispatchirptoioqueue, WdfDeviceWdmDispatchIrpToIoQueue method, kmdf.wdfdevicewdmforwardirptoioqueue, WdfDeviceWdmDispatchIrpToIoQueue
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfDeviceWdmDispatchIrpToIoQueue
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceWdmDispatchIrpToIoQueue function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDeviceWdmDispatchIrpToIoQueue</b> method forwards the IRP to a specified I/O queue.


## -syntax


````
NTSTATUS WdfDeviceWdmDispatchIrpToIoQueue(
  _In_ WDFDEVICE  Device,
  _In_ PIRP         Irp,
  _In_ WDFQUEUE    Queue,
  _In_ ULONG       Flags
);
````


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param Irp [in]

A pointer to an IRP structure.


### -param Queue [in]

A handle to a framework queue object.


### -param Flags [in]

A bitwise <b>OR</b> of <a href="..\wdfdevice\ne-wdfdevice-_wdf_dispatch_irp_to_io_queue_flags.md">WDF_DISPATCH_IRP_TO_IO_QUEUE_FLAGS</a>-typed flags.


## -returns



The <b>WdfDeviceWdmDispatchIrpToIoQueue</b> method returns an NTSTATUS value that the framework or the driver provides as a result of processing the IRP. The driver must use this return value as the return value for the <a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_irp_dispatch.md">EvtDeviceWdmIrpDispatch</a> or the <a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_irp_preprocess.md">EvtDeviceWdmIrpPreprocess</a> callback function that called <b>WdfDeviceWdmDispatchIrpToIoQueue</b>.

A bug check occurs if a KMDF  driver supplies an invalid object handle.  If a UMDF driver supplies an invalid handle, the driver host process terminates.




## -remarks



A driver calls <b>WdfDeviceWdmDispatchIrpToIoQueue</b> to specify a target queue for an incoming IRP.

The driver can call this method from its <a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_irp_preprocess.md">EvtDeviceWdmIrpPreprocess</a> callback routine or from its <a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_irp_dispatch.md">EvtDeviceWdmIrpDispatch</a> callback.

If the driver calls <b>WdfDeviceWdmDispatchIrpToIoQueue</b> from within a <a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_irp_preprocess.md">EvtDeviceWdmIrpPreprocess</a> callback function, the driver must call either <a href="https://msdn.microsoft.com/library/windows/hardware/ff550355">IoSkipCurrentIrpStackLocation</a> or <a href="..\wdm\nf-wdm-iocopycurrentirpstacklocationtonext.md">IoCopyCurrentIrpStackLocationToNext</a> prior to calling  <b>WdfDeviceWdmDispatchIrpToIoQueue</b>.

 For more information about specifying queues for IRPs as they arrive, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dispatching-irps-to-i-o-queues">Dispatching IRPs to I/O Queues</a>.




## -see-also

<a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_irp_dispatch.md">EvtDeviceWdmIrpDispatch</a>



<a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_irp_preprocess.md">EvtDeviceWdmIrpPreprocess</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceWdmDispatchIrpToIoQueue method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

