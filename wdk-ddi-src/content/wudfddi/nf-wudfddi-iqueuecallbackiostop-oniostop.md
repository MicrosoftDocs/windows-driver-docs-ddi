---
UID: NF:wudfddi.IQueueCallbackIoStop.OnIoStop
title: IQueueCallbackIoStop::OnIoStop
author: windows-driver-content
description: The OnIoStop callback function stops the processing of the specified I/O request from the specified queue.
old-location: wdf\iqueuecallbackiostop_oniostop.htm
old-project: wdf
ms.assetid: baa48d1b-b7da-4f89-b2e8-9a9ae2086527
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IQueueCallbackIoStop interface,OnIoStop method, IQueueCallbackIoStop.OnIoStop, IQueueCallbackIoStop::OnIoStop, OnIoStop, OnIoStop method, OnIoStop method,IQueueCallbackIoStop interface, UMDFQueueObjectRef_5de69aa4-be79-45c4-9ee4-1628741ca249.xml, umdf.iqueuecallbackiostop_oniostop, wdf.iqueuecallbackiostop_oniostop, wudfddi/IQueueCallbackIoStop::OnIoStop
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
-	IQueueCallbackIoStop.OnIoStop
product: Windows
targetos: Windows
req.typenames: 
---

# IQueueCallbackIoStop::OnIoStop


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnIoStop</b> callback function stops the processing of the specified I/O request from the specified queue. 


## -parameters




### -param pWdfQueue [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558943">IWDFIoQueue</a> interface for the I/O queue object that processing of the I/O request is stopped from. 


### -param pWdfRequest [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558985">IWDFIoRequest</a> interface that represents the framework request object whose processing is stopped. 


### -param ActionFlags [in]

A valid bitwise OR of <a href="https://msdn.microsoft.com/library/windows/hardware/ff561465">WDF_REQUEST_STOP_ACTION_FLAGS</a>-typed values that identifies the state of a stop action request.


## -returns



None




## -remarks



A driver registers the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556868">IQueueCallbackIoStop</a> interface when the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557020">IWDFDevice::CreateIoQueue</a> method to create an I/O queue or to configure the default I/O queue. 

If a driver registers an <b>OnIoStop</b> callback function for an I/O queue, the framework calls it when the queue's underlying device is leaving its working (D0) state. The framework calls the <b>OnIoStop</b> callback function for every I/O request that the driver has not completed, including requests that the driver owns and those that it has forwarded to an I/O target.

The <b>OnIoStop</b> callback function must complete, cancel, or postpone further processing of the I/O request. You must use the following rules:

If the driver owns the I/O request, it must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff559070">IWDFIoRequest::Complete</a> to complete or cancel the request, or it must postpone further processing of the request and then call <a href="https://msdn.microsoft.com/library/windows/hardware/ff559051">IWDFIoRequest2::StopAcknowledge</a>.

If the driver has forwarded the I/O request to an I/O target, it must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff559067">IWDFIoRequest::CancelSentRequest</a> to attempt to cancel the request, or it must postpone further processing of the request and then call <a href="https://msdn.microsoft.com/af4ae2c0-b1e1-45af-bd0e-3b9a91566caa">StopAcknowledge</a>.

If the <b>WdfRequestStopRequestCancelable</b> flag is set in the <i>ActionFlags</i> parameter, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff559163">IWDFIoRequest::UnmarkCancelable</a> before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff559070">IWDFIoRequest::Complete</a> to complete (or cancel) the request or calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff559051">IWDFIoRequest2::StopAcknowledge</a> to requeue the request.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556868">IQueueCallbackIoStop</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557020">IWDFDevice::CreateIoQueue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558943">IWDFIoQueue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558985">IWDFIoRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559051">IWDFIoRequest2::StopAcknowledge</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561465">WDF_REQUEST_STOP_ACTION_FLAGS</a>
 

 

