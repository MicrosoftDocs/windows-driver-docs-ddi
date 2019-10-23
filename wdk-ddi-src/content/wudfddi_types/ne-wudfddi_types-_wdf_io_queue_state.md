---
UID: NE:wudfddi_types._WDF_IO_QUEUE_STATE
title: _WDF_IO_QUEUE_STATE (wudfddi_types.h)
description: The WDF_IO_QUEUE_STATE enumeration contains values that identify the state of an I/O queue.
old-location: wdf\wdf_io_queue_state_umdf.htm
tech.root: wdf
ms.assetid: c91b9ea0-8c42-4199-b161-2b43ba4a1833
ms.date: 02/26/2018
ms.keywords: "*PWDF_IO_QUEUE_STATE, WDF_IO_QUEUE_STATE, WDF_IO_QUEUE_STATE enumeration, WdfIoQueueAcceptRequests, WdfIoQueueDispatchRequests, WdfIoQueueDriverNoRequests, WdfIoQueueNoRequests, WdfIoQueuePnpHeld, _WDF_IO_QUEUE_STATE, umdf.wdf_io_queue_state, umdfstructs_b0fa52c7-c536-43d3-b9a7-f63977ccb619.xml, wdf.wdf_io_queue_state_umdf, wudfddi/WDF_IO_QUEUE_STATE, wudfddi/WdfIoQueueAcceptRequests, wudfddi/WdfIoQueueDispatchRequests, wudfddi/WdfIoQueueDriverNoRequests, wudfddi/WdfIoQueueNoRequests, wudfddi/WdfIoQueuePnpHeld"
ms.topic: enum
f1_keywords:
 - "wudfddi_types/WDF_IO_QUEUE_STATE"
req.header: wudfddi_types.h
req.include-header: Wudfddi_types.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wudfddi.h
api_name:
- WDF_IO_QUEUE_STATE
product:
- Windows
targetos: Windows
req.typenames: WDF_IO_QUEUE_STATE, *PWDF_IO_QUEUE_STATE
---

# _WDF_IO_QUEUE_STATE enumeration


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi_types/ne-wudfddi_types-_wdf_io_queue_state">WDF_IO_QUEUE_STATE</a> enumeration contains values that identify the state of an I/O queue.


## -enum-fields




### -field WdfIoQueueAcceptRequests

If this value is set to 1, the queue accepts requests by automatically forwarding them through the setting of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfioqueue-configurerequestdispatching">IWDFIoQueue::ConfigureRequestDispatching</a> method or by manually forwarding each request through a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-forwardtoioqueue">IWDFIoRequest::ForwardToIoQueue</a> method. 

If this value is set to 0, the queue completes any automatically forwarded requests with "status canceled" or fails <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-forwardtoioqueue">IWDFIoRequest::ForwardToIoQueue</a> with "status busy".


### -field WdfIoQueueDispatchRequests

If this value is set to 1, the queue automatically presents requests to the driver, unless the queue is a <b>WdfIoQueueDispatchManual</b> type (see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/ne-wdfio-_wdf_io_queue_dispatch_type">WDF_IO_QUEUE_DISPATCH_TYPE</a>). 

If this value is set to 0, the queue does not automatically dispatch requests to the driver. The setting of this status does not prevent the driver from calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfioqueue-retrievenextrequest">IWDFIoQueue::RetrieveNextRequest</a> method to manually retrieve a request from the queue.


### -field WdfIoQueueNoRequests

If this value is set to 1, no requests are in the queue, even requests that can be presented to the driver and that can be returned from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfioqueue-retrievenextrequest">IWDFIoQueue::RetrieveNextRequest</a>.


### -field WdfIoQueueDriverNoRequests

If this value is set to 1, there are no requests that the driver currently operates on that it received from the queue. 


### -field WdfIoQueuePnpHeld

If this value is set to 1, an event from the Plug and Play (PnP) subsystem suspended the queue from processing requests.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfioqueue-configurerequestdispatching">IWDFIoQueue::ConfigureRequestDispatching</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfioqueue-retrievenextrequest">IWDFIoQueue::RetrieveNextRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-forwardtoioqueue">IWDFIoRequest::ForwardToIoQueue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/ne-wdfio-_wdf_io_queue_dispatch_type">WDF_IO_QUEUE_DISPATCH_TYPE</a>
 

 

