---
UID: NF:wudfddi.IWDFIoQueue.Purge
title: IWDFIoQueue::Purge method
author: windows-driver-content
description: The Purge method directs the framework to reject new incoming I/O requests and to cancel all outstanding requests.
old-location: wdf\iwdfioqueue_purge.htm
old-project: wdf
ms.assetid: c7863713-850f-4516-aec5-9e851c36cf52
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: Purge method, IWDFIoQueue interface, wudfddi/IWDFIoQueue::Purge, Purge, Purge method, IWDFIoQueue interface, Purge method, wdf.iwdfioqueue_purge, umdf.iwdfioqueue_purge, UMDFQueueObjectRef_5d2113b9-d2e3-4a27-af75-60f4bf7bddbf.xml, IWDFIoQueue, IWDFIoQueue::Purge
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: wudfddi.h
req.dll: WUDFx.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WUDFx.dll
apiname:
-	IWDFIoQueue.Purge
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFIoQueue::Purge method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Purge</b> method directs the framework to reject new incoming I/O requests and to cancel all outstanding requests. 


## -syntax


````
void Purge(
  [in, optional] IQueueCallbackStateChange *pPurgeComplete
);
````


## -parameters




### -param pPurgeComplete [in, optional]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iqueuecallbackstatechange.md">IQueueCallbackStateChange</a> interface whose method the framework calls to deliver queue state to the driver. The framework calls the method after all requests are canceled. This parameter is optional and can be <b>NULL</b>.


## -returns



None




## -remarks



The framework cancels unprocessed requests in the queue. For requests that are delivered to the driver and marked cancelable, the framework calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff556903">IRequestCallbackCancel::OnCancel</a>. 

The driver should ensure that only one of the following methods is in progress at any given time: 

<ul>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558980">IWDFIoQueue::Stop</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558951">IWDFIoQueue::Drain</a>


</li>
<li>
<b>IWDFIoQueue::Purge</b>

</li>
</ul>
For example, if the driver previously called <b>Purge</b>, it should wait for notification from the method of the interface that the <i>pPurgeComplete</i> parameter points to before it calls either <a href="https://msdn.microsoft.com/library/windows/hardware/dn927275">Stop</a> or <a href="https://msdn.microsoft.com/0356e8a7-de44-4b0f-9067-ca3bb04260d8">Drain</a>. Violating this rule results in termination of the host process.


#### Examples

The following code example shows how to stop requests to a queue.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
CUmdfHidFile::OnCleanupFile(
    __in IWDFFile* /* WdfFile */
    )
/*++
    This method handles the cleanup operation for the file object.  
    Because the file is disabled, no new reports should be added to the ring buffer.
--*/
{
    this-&gt;Disable();

    //
    // Stop all current requests to read reports.
    //

    m_GetReportQueue-&gt;Purge(NULL);
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558980">IWDFIoQueue::Stop</a>



<a href="..\wudfddi\nn-wudfddi-iwdfioqueue.md">IWDFIoQueue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556903">IRequestCallbackCancel::OnCancel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558951">IWDFIoQueue::Drain</a>



<a href="..\wudfddi\nn-wudfddi-iqueuecallbackstatechange.md">IQueueCallbackStateChange</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoQueue::Purge method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

