---
UID: NF:wdfdevice.WdfDeviceInitSetIoInCallerContextCallback
title: WdfDeviceInitSetIoInCallerContextCallback function
author: windows-driver-content
description: The WdfDeviceInitSetIoInCallerContextCallback method registers a driver's EvtIoInCallerContext event callback function.
old-location: wdf\wdfdeviceinitsetioincallercontextcallback.htm
old-project: wdf
ms.assetid: f0104e8b-9a2f-4f52-a431-bec7de3be968
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_6ef62fc4-094a-4fe7-8ecb-7205566aef77.xml, WdfDeviceInitSetIoInCallerContextCallback, WdfDeviceInitSetIoInCallerContextCallback method, kmdf.wdfdeviceinitsetioincallercontextcallback, wdf.wdfdeviceinitsetioincallercontextcallback, wdfdevice/WdfDeviceInitSetIoInCallerContextCallback
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfDeviceInitSetIoInCallerContextCallback
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceInitSetIoInCallerContextCallback function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceInitSetIoInCallerContextCallback</b> method registers a driver's <a href="https://msdn.microsoft.com/b8bcea29-e404-490e-9d0c-02c96a5690ab">EvtIoInCallerContext</a> event callback function.


## -parameters




### -param DeviceInit [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


### -param EvtIoInCallerContext [in]

A pointer to the driver's <a href="https://msdn.microsoft.com/b8bcea29-e404-490e-9d0c-02c96a5690ab">EvtIoInCallerContext</a> callback function.


## -returns



None




## -remarks



If a driver calls <b>WdfDeviceInitSetIoInCallerContextCallback</b>, it must do so before it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>. For more information about calling <b>WdfDeviceCreate</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.

For more information about the <a href="https://msdn.microsoft.com/b8bcea29-e404-490e-9d0c-02c96a5690ab">EvtIoInCallerContext</a> event callback function, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/managing-i-o-queues">Intercepting an I/O Request before it is Queued</a>.


#### Examples

The following code example registers a driver's <a href="https://msdn.microsoft.com/b8bcea29-e404-490e-9d0c-02c96a5690ab">EvtIoInCallerContext</a> event callback function.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WdfDeviceInitSetIoInCallerContextCallback(
                                          DeviceInit, 
                                          MyEvtIoInCallerContext
                                          );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/b8bcea29-e404-490e-9d0c-02c96a5690ab">EvtIoInCallerContext</a>
 

 

