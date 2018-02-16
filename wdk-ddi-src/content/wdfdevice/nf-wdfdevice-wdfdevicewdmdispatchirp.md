---
UID: NF:wdfdevice.WdfDeviceWdmDispatchIrp
title: WdfDeviceWdmDispatchIrp function
author: windows-driver-content
description: The WdfDeviceWdmDispatchIrp method returns a dispatched IRP to the framework from EvtDeviceWdmIrpDispatch.
old-location: wdf\wdfdevicewdmdispatchirp.htm
old-project: wdf
ms.assetid: 362C6F7C-7B92-43A8-9BD0-F647FDD266E4
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfDeviceWdmDispatchIrp, WdfDeviceWdmDispatchIrp method, wdfdevice/WdfDeviceWdmDispatchIrp, wdf.wdfdevicewdmdispatchirp, kmdf.wdfdevicewdmdispatchirp
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
req.ddi-compliance: DriverCreate
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
-	WdfDeviceWdmDispatchIrp
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceWdmDispatchIrp function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDeviceWdmDispatchIrp</b> method returns a dispatched IRP to the framework from <a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_irp_dispatch.md">EvtDeviceWdmIrpDispatch</a>.


## -syntax


````
NTSTATUS WdfDeviceWdmDispatchIrp(
  _In_ WDFDEVICE   Device,
  _In_ PIRP          Irp,
  _In_ WDFCONTEXT   DispatchContext
);
````


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param Irp [in]

A pointer to an IRP structure.


### -param DispatchContext [in]

The dispatch context parameter the driver received in <a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_irp_dispatch.md">EvtDeviceWdmIrpDispatch</a>  callback.


## -returns



The <b>WdfDeviceWdmDispatchIrp</b> method returns an NTSTATUS value that the framework or the driver provides as a result of processing the IRP. The driver must use this return value as the return value for the <a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_irp_dispatch.md">EvtDeviceWdmIrpDispatch</a> callback function that called <b>WdfDeviceWdmDispatchIrp</b>.

A bug check occurs if a KMDF  driver supplies an invalid object handle.  If a UMDF driver supplies an invalid handle, the driver host process terminates.




## -remarks



If your driver provides an <a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_irp_dispatch.md">EvtDeviceWdmIrpDispatch</a> callback function, you can call <b>WdfDeviceWdmDispatchIrp</b> from within the callback function to return the IRP to the framework for default processing instead of dispatching it to a specific queue.

 For more information about specifying queues for IRPs as they arrive, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dispatching-irps-to-i-o-queues">Dispatching IRPs to I/O Queues</a>.




## -see-also

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicewdmdispatchirptoioqueue.md">WdfDeviceWdmDispatchIrpToIoQueue</a>



<a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_irp_dispatch.md">EvtDeviceWdmIrpDispatch</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceWdmDispatchIrp method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

