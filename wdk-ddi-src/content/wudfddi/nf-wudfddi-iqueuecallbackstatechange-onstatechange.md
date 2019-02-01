---
UID: NF:wudfddi.IQueueCallbackStateChange.OnStateChange
title: IQueueCallbackStateChange::OnStateChange (wudfddi.h)
description: The OnStateChange method is called when the state of the I/O queue object changes.
old-location: wdf\iqueuecallbackstatechange_onstatechange.htm
tech.root: wdf
ms.assetid: 69a422a1-b878-496e-b1b9-e04b7c3db121
ms.date: 02/26/2018
ms.keywords: IQueueCallbackStateChange interface,OnStateChange method, IQueueCallbackStateChange.OnStateChange, IQueueCallbackStateChange::OnStateChange, OnStateChange, OnStateChange method, OnStateChange method,IQueueCallbackStateChange interface, UMDFQueueObjectRef_194f5013-22a2-40c4-8913-9371aa281009.xml, umdf.iqueuecallbackstatechange_onstatechange, wdf.iqueuecallbackstatechange_onstatechange, wudfddi/IQueueCallbackStateChange::OnStateChange
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Wudfddi.h
api_name:
-	IQueueCallbackStateChange.OnStateChange
product:
- Windows
targetos: Windows
req.typenames: 
---

# IQueueCallbackStateChange::OnStateChange


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnStateChange</b> method is called when the state of the I/O queue object changes. 


## -parameters




### -param pWdfQueue [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558943">IWDFIoQueue</a> interface for the I/O queue object whose state changes. 


### -param QueueState [in]

A valid bitwise OR of <a href="https://msdn.microsoft.com/library/windows/hardware/ff561417">WDF_IO_QUEUE_STATE</a>-typed values that indicates status for the queue.


## -returns



None




## -remarks



A driver registers the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556877">IQueueCallbackStateChange</a> interface when the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557020">IWDFDevice::CreateIoQueue</a> method to create an I/O queue or to configure the default I/O queue. The driver can optionally register the <b>IQueueCallbackStateChange</b> interface only for a manual queue. The driver must not register <b>IQueueCallbackStateChange</b> for a sequential or a parallel queue.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556877">IQueueCallbackStateChange</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557020">IWDFDevice::CreateIoQueue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558943">IWDFIoQueue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561417">WDF_IO_QUEUE_STATE</a>
 

 

