---
UID: NF:wudfddi.IWDFIoQueue.Drain
title: IWDFIoQueue::Drain (wudfddi.h)
description: The Drain method directs the queue to reject new incoming I/O requests and allow already-queued requests to be delivered to the driver for processing.
old-location: wdf\iwdfioqueue_drain.htm
tech.root: wdf
ms.assetid: 0356e8a7-de44-4b0f-9067-ca3bb04260d8
ms.date: 02/26/2018
ms.keywords: Drain, Drain method, Drain method,IWDFIoQueue interface, IWDFIoQueue interface,Drain method, IWDFIoQueue.Drain, IWDFIoQueue::Drain, UMDFQueueObjectRef_cb7bdc3f-3280-4949-a60a-b78f13492da9.xml, umdf.iwdfioqueue_drain, wdf.iwdfioqueue_drain, wudfddi/IWDFIoQueue::Drain
ms.topic: method
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
- IWDFIoQueue.Drain
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoQueue::Drain


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Drain</b> method directs the queue to reject new incoming I/O requests and allow already-queued requests to be delivered to the driver for processing.


## -parameters




### -param pDrainComplete [in, optional]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iqueuecallbackstatechange">IQueueCallbackStateChange</a> interface whose method the framework calls to deliver queue state to the driver. The framework calls the method after all requests are completed or canceled and the queue is empty. This parameter is optional and can be <b>NULL</b>.


## -returns



None




## -remarks



A driver should ensure that only one of the following methods is in progress at any given time: 

<ul>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfioqueue-stop">IWDFIoQueue::Stop</a>


</li>
<li>
<b>IWDFIoQueue::Drain</b>

</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfioqueue-purge">IWDFIoQueue::Purge</a>


</li>
</ul>
For example, if the driver previously called <b>Drain</b>, it should wait for notification from the method of the interface that the <i>pDrainComplete</i> parameter points to before the driver calls either <a href="https://docs.microsoft.com/windows-hardware/test/wpt/stop-icontrolmanager">Stop</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfioqueue-purge">Purge</a>. Violating this rule results in termination of the host process.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iqueuecallbackstatechange">IQueueCallbackStateChange</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfioqueue">IWDFIoQueue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfioqueue-purge">IWDFIoQueue::Purge</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfioqueue-stop">IWDFIoQueue::Stop</a>
 

 

