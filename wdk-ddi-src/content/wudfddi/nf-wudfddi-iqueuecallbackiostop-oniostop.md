---
UID: NF:wudfddi.IQueueCallbackIoStop.OnIoStop
title: IQueueCallbackIoStop::OnIoStop (wudfddi.h)
description: The OnIoStop callback function stops the processing of the specified I/O request from the specified queue.
old-location: wdf\iqueuecallbackiostop_oniostop.htm
tech.root: wdf
ms.assetid: baa48d1b-b7da-4f89-b2e8-9a9ae2086527
ms.date: 02/26/2018
keywords: ["IQueueCallbackIoStop::OnIoStop"]
ms.keywords: IQueueCallbackIoStop interface,OnIoStop method, IQueueCallbackIoStop.OnIoStop, IQueueCallbackIoStop::OnIoStop, OnIoStop, OnIoStop method, OnIoStop method,IQueueCallbackIoStop interface, UMDFQueueObjectRef_5de69aa4-be79-45c4-9ee4-1628741ca249.xml, umdf.iqueuecallbackiostop_oniostop, wdf.iqueuecallbackiostop_oniostop, wudfddi/IQueueCallbackIoStop::OnIoStop
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IQueueCallbackIoStop::OnIoStop
 - wudfddi/IQueueCallbackIoStop::OnIoStop
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Wudfddi.h
api_name:
 - IQueueCallbackIoStop.OnIoStop
---

# IQueueCallbackIoStop::OnIoStop


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnIoStop</b> callback function stops the processing of the specified I/O request from the specified queue.

## -parameters

### -param pWdfQueue 

[in]
A pointer to the <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfioqueue">IWDFIoQueue</a> interface for the I/O queue object that processing of the I/O request is stopped from.

### -param pWdfRequest 

[in]
A pointer to the <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequest">IWDFIoRequest</a> interface that represents the framework request object whose processing is stopped.

### -param ActionFlags 

[in]
A valid bitwise OR of <a href="/windows-hardware/drivers/ddi/wudfddi_types/ne-wudfddi_types-_wdf_request_stop_action_flags">WDF_REQUEST_STOP_ACTION_FLAGS</a>-typed values that identifies the state of a stop action request.

## -remarks

A driver registers the <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iqueuecallbackiostop">IQueueCallbackIoStop</a> interface when the driver calls the <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice-createioqueue">IWDFDevice::CreateIoQueue</a> method to create an I/O queue or to configure the default I/O queue. 

If a driver registers an <b>OnIoStop</b> callback function for an I/O queue, the framework calls it when the queue's underlying device is leaving its working (D0) state. The framework calls the <b>OnIoStop</b> callback function for every I/O request that the driver has not completed, including requests that the driver owns and those that it has forwarded to an I/O target.

The <b>OnIoStop</b> callback function must complete, cancel, or postpone further processing of the I/O request. You must use the following rules:

If the driver owns the I/O request, it must call <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-complete">IWDFIoRequest::Complete</a> to complete or cancel the request, or it must postpone further processing of the request and then call <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest2-stopacknowledge">IWDFIoRequest2::StopAcknowledge</a>.

If the driver has forwarded the I/O request to an I/O target, it must call <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-cancelsentrequest">IWDFIoRequest::CancelSentRequest</a> to attempt to cancel the request, or it must postpone further processing of the request and then call <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest2-stopacknowledge">StopAcknowledge</a>.

If the <b>WdfRequestStopRequestCancelable</b> flag is set in the <i>ActionFlags</i> parameter, the driver must call <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-unmarkcancelable">IWDFIoRequest::UnmarkCancelable</a> before calling <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-complete">IWDFIoRequest::Complete</a> to complete (or cancel) the request or calling <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest2-stopacknowledge">IWDFIoRequest2::StopAcknowledge</a> to requeue the request.

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iqueuecallbackiostop">IQueueCallbackIoStop</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice-createioqueue">IWDFDevice::CreateIoQueue</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfioqueue">IWDFIoQueue</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequest">IWDFIoRequest</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest2-stopacknowledge">IWDFIoRequest2::StopAcknowledge</a>



<a href="/windows-hardware/drivers/ddi/wudfddi_types/ne-wudfddi_types-_wdf_request_stop_action_flags">WDF_REQUEST_STOP_ACTION_FLAGS</a>