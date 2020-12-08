---
UID: NF:wudfddi.IWDFIoQueue.Purge
title: IWDFIoQueue::Purge (wudfddi.h)
description: The Purge method directs the framework to reject new incoming I/O requests and to cancel all outstanding requests.
old-location: wdf\iwdfioqueue_purge.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["IWDFIoQueue::Purge"]
ms.keywords: IWDFIoQueue interface,Purge method, IWDFIoQueue.Purge, IWDFIoQueue::Purge, Purge, Purge method, Purge method,IWDFIoQueue interface, UMDFQueueObjectRef_5d2113b9-d2e3-4a27-af75-60f4bf7bddbf.xml, umdf.iwdfioqueue_purge, wdf.iwdfioqueue_purge, wudfddi/IWDFIoQueue::Purge
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDFIoQueue::Purge
 - wudfddi/IWDFIoQueue::Purge
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFIoQueue.Purge
---

# IWDFIoQueue::Purge


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Purge</b> method directs the framework to reject new incoming I/O requests and to cancel all outstanding requests.

## -parameters

### -param pPurgeComplete 

[in, optional]
A pointer to the <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iqueuecallbackstatechange">IQueueCallbackStateChange</a> interface whose method the framework calls to deliver queue state to the driver. The framework calls the method after all requests are canceled. This parameter is optional and can be <b>NULL</b>.

## -remarks

The framework cancels unprocessed requests in the queue. For requests that are delivered to the driver and marked cancelable, the framework calls <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-irequestcallbackcancel-oncancel">IRequestCallbackCancel::OnCancel</a>. 

The driver should ensure that only one of the following methods is in progress at any given time: 

<ul>
<li>

<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfioqueue-stop">IWDFIoQueue::Stop</a>


</li>
<li>

<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfioqueue-drain">IWDFIoQueue::Drain</a>


</li>
<li>
<b>IWDFIoQueue::Purge</b>

</li>
</ul>
For example, if the driver previously called <b>Purge</b>, it should wait for notification from the method of the interface that the <i>pPurgeComplete</i> parameter points to before it calls either <a href="/windows-hardware/test/wpt/stop-icontrolmanager">Stop</a> or <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfioqueue-drain">Drain</a>. Violating this rule results in termination of the host process.


#### Examples

The following code example shows how to stop requests to a queue.


```
VOID
CUmdfHidFile::OnCleanupFile(
    __in IWDFFile* /* WdfFile */
    )
/*++
    This method handles the cleanup operation for the file object.  
    Because the file is disabled, no new reports should be added to the ring buffer.
--*/
{
    this->Disable();

    //
    // Stop all current requests to read reports.
    //

    m_GetReportQueue->Purge(NULL);
}
```


## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iqueuecallbackstatechange">IQueueCallbackStateChange</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-irequestcallbackcancel-oncancel">IRequestCallbackCancel::OnCancel</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfioqueue">IWDFIoQueue</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfioqueue-drain">IWDFIoQueue::Drain</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfioqueue-stop">IWDFIoQueue::Stop</a>
