---
UID: NF:wdfdevice.WdfDeviceGetDefaultQueue
title: WdfDeviceGetDefaultQueue function
author: windows-driver-content
description: The WdfDeviceGetDefaultQueue method returns a handle to a device's default I/O queue.
old-location: wdf\wdfdevicegetdefaultqueue.htm
tech.root: wdf
ms.assetid: 914c4ef8-2210-468c-8720-11f8adf9dce7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_17d2efb6-80ae-4045-baa4-68d610b9e0c3.xml, WdfDeviceGetDefaultQueue, WdfDeviceGetDefaultQueue method, kmdf.wdfdevicegetdefaultqueue, wdf.wdfdevicegetdefaultqueue, wdfdevice/WdfDeviceGetDefaultQueue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfDeviceGetDefaultQueue
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceGetDefaultQueue function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDeviceGetDefaultQueue</b> method returns a handle to a device's default I/O queue.


## -parameters




### -param Device [in]

A handle to a framework device object.


## -returns



If the operation succeeds, the method returns a handle to a framework queue object. If the driver did not create a default I/O queue for the device, the method returns <b>NULL</b>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



For more information about default I/O queues, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-i-o-queues">Creating I/O Queues</a>.


#### Examples

The following code example obtains a handle to a device's default I/O queue.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDFQUEUE DefaultQueue;

DefaultQueue = WdfDeviceGetDefaultQueue(Device);</pre>
</td>
</tr>
</table></span></div>


