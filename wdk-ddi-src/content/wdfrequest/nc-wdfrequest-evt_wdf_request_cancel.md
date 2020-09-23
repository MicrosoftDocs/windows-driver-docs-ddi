---
UID: NC:wdfrequest.EVT_WDF_REQUEST_CANCEL
title: EVT_WDF_REQUEST_CANCEL (wdfrequest.h)
description: A driver's EvtRequestCancel event callback function handles operations that must be performed when an I/O request is canceled.
old-location: wdf\evtrequestcancel.htm
tech.root: wdf
ms.assetid: db54fa76-d3e0-4f8c-aa3f-bab268dd9b4d
ms.date: 02/26/2018
keywords: ["EVT_WDF_REQUEST_CANCEL callback function"]
ms.keywords: DFRequestObjectRef_fe2e3eee-9f6a-4fd8-afa7-23eb740ccd01.xml, EVT_WDF_REQUEST_CANCEL, EVT_WDF_REQUEST_CANCEL callback, EvtRequestCancel, EvtRequestCancel callback function, kmdf.evtrequestcancel, wdf.evtrequestcancel, wdfrequest/EvtRequestCancel
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_WDF_REQUEST_CANCEL
 - wdfrequest/EVT_WDF_REQUEST_CANCEL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdfrequest.h
api_name:
 - EvtRequestCancel
---

# EVT_WDF_REQUEST_CANCEL callback function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtRequestCancel</i> event callback function handles operations that must be performed when an I/O request is canceled.

## -parameters

### -param Request 

[in]
A handle to a framework request object that represents the I/O request that is being canceled.

## -remarks

To register an <i>EvtRequestCancel</i> callback function, the driver must call <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestmarkcancelable">WdfRequestMarkCancelable</a> or <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestmarkcancelableex">WdfRequestMarkCancelableEx</a>.

 When the framework calls your driver's <i>EvtRequestCancel</i> callback function, if the driver can cancel the request, it must:

<ol>
<li>
Finish or stop processing the request, along with subrequests that it might have created.

</li>
<li>
Call <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcomplete">WdfRequestComplete</a>, specifying a status value of STATUS_CANCELLED.

</li>
</ol>
For more information about this callback function, see <a href="/windows-hardware/drivers/wdf/canceling-i-o-requests">Canceling I/O Requests</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcomplete">WdfRequestComplete</a>



<a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestmarkcancelable">WdfRequestMarkCancelable</a>



<a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestmarkcancelableex">WdfRequestMarkCancelableEx</a>