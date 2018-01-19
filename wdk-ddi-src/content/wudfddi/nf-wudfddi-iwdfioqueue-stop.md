---
UID: NF:wudfddi.IWDFIoQueue.Stop
title: IWDFIoQueue::Stop method
author: windows-driver-content
description: The Stop method prevents an I/O queue from delivering I/O requests, but the queue receives and stores new requests.
old-location: wdf\iwdfioqueue_stop.htm
old-project: wdf
ms.assetid: 4ad9410a-f3ec-445a-b509-7666a81e1427
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IWDFIoQueue, IWDFIoQueue::Stop, Stop
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.alt-api: IWDFIoQueue.Stop
req.alt-loc: WUDFx.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
req.typenames: *PPOWER_ACTION, POWER_ACTION
req.product: Windows 10 or later.
---

# IWDFIoQueue::Stop method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Stop</b> method prevents an I/O queue from delivering I/O requests, but the queue receives and stores new requests.



## -syntax

````
void Stop(
  [in, optional] IQueueCallbackStateChange *pStopComplete
);
````


## -parameters

### -param pStopComplete [in, optional]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iqueuecallbackstatechange.md">IQueueCallbackStateChange</a> interface whose method the framework calls after all outstanding I/O requests, if any, in the driver are completed. This parameter is optional and can be <b>NULL</b>.


## -returns
None


## -remarks
A call to <b>Stop</b> is asynchronous and immediately returns to the driver. The driver is notified through the method of the supplied <a href="..\wudfddi\nn-wudfddi-iqueuecallbackstatechange.md">IQueueCallbackStateChange</a> interface after all outstanding requests in the driver complete.

The driver should ensure that only one of the following methods is in progress at any given time: 

<b>IWDFIoQueue::Stop</b>


<a href="https://msdn.microsoft.com/library/windows/hardware/ff558951">IWDFIoQueue::Drain</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558962">IWDFIoQueue::Purge</a>


For example, if the driver previously called <b>Stop</b>, it should wait for notification from the method of the interface that the <i>pStopComplete</i> parameter points to before the driver calls either <a href="https://msdn.microsoft.com/0356e8a7-de44-4b0f-9067-ca3bb04260d8">Drain</a> or <a href="https://msdn.microsoft.com/c7863713-850f-4516-aec5-9e851c36cf52">Purge</a>. Violating this rule results in termination of the host process.

The <b>Stop</b> method enables the queue to receive new requests, even if the queue was not receiving new requests before the driver called <b>Stop</b>. For example, a driver might call <a href="https://msdn.microsoft.com/library/windows/hardware/ff558951">IWDFIoQueue::Drain</a>, which causes the framework to stop adding new I/O requests to the queue. The driver's subsequent call of <b>Stop</b> causes the framework to resume adding requests to the queue.


## -see-also
<dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfioqueue.md">IWDFIoQueue</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iqueuecallbackstatechange.md">IQueueCallbackStateChange</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558951">IWDFIoQueue::Drain</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558962">IWDFIoQueue::Purge</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoQueue::Stop method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

