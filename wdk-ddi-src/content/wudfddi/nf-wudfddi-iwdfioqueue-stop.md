---
UID: NF:wudfddi.IWDFIoQueue.Stop
title: IWDFIoQueue::Stop (wudfddi.h)
description: The Stop method prevents an I/O queue from delivering I/O requests, but the queue receives and stores new requests.
old-location: wdf\iwdfioqueue_stop.htm
tech.root: wdf
ms.assetid: 4ad9410a-f3ec-445a-b509-7666a81e1427
ms.date: 02/26/2018
keywords: ["IWDFIoQueue::Stop"]
ms.keywords: IWDFIoQueue interface,Stop method, IWDFIoQueue.Stop, IWDFIoQueue::Stop, Stop, Stop method, Stop method,IWDFIoQueue interface, UMDFQueueObjectRef_c45e9686-2484-4c8d-857d-4dc12c8f2fd7.xml, umdf.iwdfioqueue_stop, wdf.iwdfioqueue_stop, wudfddi/IWDFIoQueue::Stop
f1_keywords:
 - "wudfddi/IWDFIoQueue.Stop"
 - "IWDFIoQueue.Stop"
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFIoQueue.Stop
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoQueue::Stop


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Stop</b> method prevents an I/O queue from delivering I/O requests, but the queue receives and stores new requests.


## -parameters




### -param pStopComplete [in, optional]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iqueuecallbackstatechange">IQueueCallbackStateChange</a> interface whose method the framework calls after all outstanding I/O requests, if any, in the driver are completed. This parameter is optional and can be <b>NULL</b>.


## -remarks



A call to <b>Stop</b> is asynchronous and immediately returns to the driver. The driver is notified through the method of the supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iqueuecallbackstatechange">IQueueCallbackStateChange</a> interface after all outstanding requests in the driver complete.

The driver should ensure that only one of the following methods is in progress at any given time: 

<ul>
<li>
<b>IWDFIoQueue::Stop</b>

</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfioqueue-drain">IWDFIoQueue::Drain</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfioqueue-purge">IWDFIoQueue::Purge</a>


</li>
</ul>
For example, if the driver previously called <b>Stop</b>, it should wait for notification from the method of the interface that the <i>pStopComplete</i> parameter points to before the driver calls either <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfioqueue-drain">Drain</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfioqueue-purge">Purge</a>. Violating this rule results in termination of the host process.

The <b>Stop</b> method enables the queue to receive new requests, even if the queue was not receiving new requests before the driver called <b>Stop</b>. For example, a driver might call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfioqueue-drain">IWDFIoQueue::Drain</a>, which causes the framework to stop adding new I/O requests to the queue. The driver's subsequent call of <b>Stop</b> causes the framework to resume adding requests to the queue.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iqueuecallbackstatechange">IQueueCallbackStateChange</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfioqueue">IWDFIoQueue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfioqueue-drain">IWDFIoQueue::Drain</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfioqueue-purge">IWDFIoQueue::Purge</a>
 

 

