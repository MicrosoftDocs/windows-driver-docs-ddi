---
UID: NF:wdfdevice.WdfDeviceInitSetIoInCallerContextCallback
title: WdfDeviceInitSetIoInCallerContextCallback function
author: windows-driver-content
description: The WdfDeviceInitSetIoInCallerContextCallback method registers a driver's EvtIoInCallerContext event callback function.
old-location: wdf\wdfdeviceinitsetioincallercontextcallback.htm
old-project: wdf
ms.assetid: f0104e8b-9a2f-4f52-a431-bec7de3be968
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfdevice/WdfDeviceInitSetIoInCallerContextCallback, WdfDeviceInitSetIoInCallerContextCallback method, WdfDeviceInitSetIoInCallerContextCallback, wdf.wdfdeviceinitsetioincallercontextcallback, kmdf.wdfdeviceinitsetioincallercontextcallback, DFDeviceObjectGeneralRef_6ef62fc4-094a-4fe7-8ecb-7205566aef77.xml, PFN_WDFDEVICEINITSETIOINCALLERCONTEXTCALLBACK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: ChildDeviceInitAPI, ControlDeviceInitAPI, DeviceInitAPI, DriverCreate, KmdfIrql, KmdfIrql2, PdoDeviceInitAPI
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
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
apiname:
-	WdfDeviceInitSetIoInCallerContextCallback
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceInitSetIoInCallerContextCallback function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceInitSetIoInCallerContextCallback</b> method registers a driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_io_in_caller_context.md">EvtIoInCallerContext</a> event callback function.


## -syntax


````
VOID WdfDeviceInitSetIoInCallerContextCallback(
  _In_ PWDFDEVICE_INIT              DeviceInit,
  _In_ PFN_WDF_IO_IN_CALLER_CONTEXT EvtIoInCallerContext
);
````


## -parameters




#### - DeviceInit [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


#### - EvtIoInCallerContext [in]

A pointer to the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_io_in_caller_context.md">EvtIoInCallerContext</a> callback function.


## -returns


None



## -remarks


If a driver calls <b>WdfDeviceInitSetIoInCallerContextCallback</b>, it must do so before it calls <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>. For more information about calling <b>WdfDeviceCreate</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.

For more information about the <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_io_in_caller_context.md">EvtIoInCallerContext</a> event callback function, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/managing-i-o-queues">Intercepting an I/O Request before it is Queued</a>.



## -see-also

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_io_in_caller_context.md">EvtIoInCallerContext</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceInitSetIoInCallerContextCallback method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

