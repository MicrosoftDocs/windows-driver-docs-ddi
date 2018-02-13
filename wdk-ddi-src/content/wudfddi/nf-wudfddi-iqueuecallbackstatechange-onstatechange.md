---
UID: NF:wudfddi.IQueueCallbackStateChange.OnStateChange
title: IQueueCallbackStateChange::OnStateChange method
author: windows-driver-content
description: The OnStateChange method is called when the state of the I/O queue object changes.
old-location: wdf\iqueuecallbackstatechange_onstatechange.htm
old-project: wdf
ms.assetid: 69a422a1-b878-496e-b1b9-e04b7c3db121
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.iqueuecallbackstatechange_onstatechange, wudfddi/IQueueCallbackStateChange::OnStateChange, umdf.iqueuecallbackstatechange_onstatechange, IQueueCallbackStateChange interface, OnStateChange method, IQueueCallbackStateChange::OnStateChange, UMDFQueueObjectRef_194f5013-22a2-40c4-8913-9371aa281009.xml, OnStateChange method, IQueueCallbackStateChange interface, IQueueCallbackStateChange, OnStateChange method, OnStateChange
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: wudfddi.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Wudfddi.h
apiname:
-	IQueueCallbackStateChange.OnStateChange
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---

# IQueueCallbackStateChange::OnStateChange method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnStateChange</b> method is called when the state of the I/O queue object changes. 


## -syntax


````
void OnStateChange(
  [in] IWDFIoQueue        *pWdfQueue,
  [in] WDF_IO_QUEUE_STATE QueueState
);
````


## -parameters




### -param pWdfQueue [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfioqueue.md">IWDFIoQueue</a> interface for the I/O queue object whose state changes. 


### -param QueueState [in]

A valid bitwise OR of <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_io_queue_state.md">WDF_IO_QUEUE_STATE</a>-typed values that indicates status for the queue.


## -returns



None




## -remarks



A driver registers the <a href="..\wudfddi\nn-wudfddi-iqueuecallbackstatechange.md">IQueueCallbackStateChange</a> interface when the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557020">IWDFDevice::CreateIoQueue</a> method to create an I/O queue or to configure the default I/O queue. The driver can optionally register the <b>IQueueCallbackStateChange</b> interface only for a manual queue. The driver must not register <b>IQueueCallbackStateChange</b> for a sequential or a parallel queue.




## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfioqueue.md">IWDFIoQueue</a>



<a href="..\wudfddi_types\ne-wudfddi_types-_wdf_io_queue_state.md">WDF_IO_QUEUE_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557020">IWDFDevice::CreateIoQueue</a>



<a href="..\wudfddi\nn-wudfddi-iqueuecallbackstatechange.md">IQueueCallbackStateChange</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IQueueCallbackStateChange::OnStateChange method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

