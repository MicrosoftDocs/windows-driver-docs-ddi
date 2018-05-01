---
UID: NF:wdfio.WdfIoQueuePurge
title: WdfIoQueuePurge function
author: windows-driver-content
description: The WdfIoQueuePurge method causes the framework to stop queuing I/O requests to an I/O queue and to cancel unprocessed requests.
old-location: wdf\wdfioqueuepurge.htm
old-project: wdf
ms.assetid: bd6e9583-774f-4ca2-9c23-4d32b233daff
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFQueueObjectRef_611371f2-862e-41c5-9f8f-d0a61c7e731e.xml, WdfIoQueuePurge, WdfIoQueuePurge method, kmdf.wdfioqueuepurge, wdf.wdfioqueuepurge, wdfio/WdfIoQueuePurge
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: ChangeQueueState, DriverCreate, EvtSurpriseRemoveNoSuspendQueue, KmdfIrql, KmdfIrql2, NoCancelFromEvtSurpriseRemove
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
-	WdfIoQueuePurge
product: Windows
targetos: Windows
req.typenames: 
---

# WdfIoQueuePurge function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfIoQueuePurge</b> method causes the framework to stop queuing I/O requests to an I/O queue and to cancel unprocessed requests. 


## -parameters




### -param Queue [in]

A handle to a framework queue object.


### -param PurgeComplete [in, optional]

A pointer to a driver-supplied <a href="https://msdn.microsoft.com/14999036-c137-4056-b6f7-53a8476fd385">EvtIoQueueState</a> callback function. This parameter is optional and can be <b>NULL</b>.


### -param Context [in, optional]

An untyped pointer to driver-supplied context information that the framework passes to the <a href="https://msdn.microsoft.com/14999036-c137-4056-b6f7-53a8476fd385">EvtIoQueueState</a> callback function. This parameter is optional and can be <b>NULL</b>.


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



After a driver calls <b>WdfIoQueuePurge</b>, the framework stops adding I/O requests to the specified queue. The framework <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/canceling-i-o-requests">cancels</a> all requests that it has not delivered to the target device and calls the driver's  <a href="https://msdn.microsoft.com/7d3eb4d6-9fc7-4924-9b95-f5824713049b">CompletionRoutine</a> callback function  for each. The framework also attempts to cancel (by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff548338">IoCancelIrp</a>) any requests delivered to the target device that were not marked <a href="https://msdn.microsoft.com/0d561e0f-ca7e-44ed-9025-1a6513e4cd28">WDF_REQUEST_SEND_OPTION_IGNORE_TARGET_STATE</a>.

If the framework receives additional requests for the queue, it completes them with a completion status value of STATUS_INVALID_DEVICE_STATE.

If the driver supplies an <a href="https://msdn.microsoft.com/14999036-c137-4056-b6f7-53a8476fd385">EvtIoQueueState</a> callback function, the framework calls it after all requests that were delivered to the driver have been completed or canceled.

After a driver has purged an I/O queue, it can restart the queue by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff548478">WdfIoQueueStart</a>.

If the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff550012">WdfRequestRequeue</a> after calling <b>WdfIoQueuePurge</b>, the requeue attempt may succeed before the purge is complete. In versions 1.9 and earlier of KMDF, this 
sequence causes the operating system to crash.  This problem is fixed in KMDF version 1.11 and later.

For more information about the <b>WdfIoQueuePurge</b> method, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/managing-i-o-queues">Managing I/O Queues</a>.


#### Examples

The following code example purges an I/O queue and does not call a callback function when all requests that were delivered to the driver have been completed or canceled.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WdfIoQueuePurge(
                ReadQueue, 
                WDF_NO_EVENT_CALLBACK, 
                WDF_NO_CONTEXT 
                );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/14999036-c137-4056-b6f7-53a8476fd385">EvtIoQueueState</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547406">WdfIoQueueDrain</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548449">WdfIoQueuePurgeSynchronously</a>
 

 

