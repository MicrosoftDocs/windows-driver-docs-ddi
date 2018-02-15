---
UID: NE:wudfddi_types._WDF_IO_QUEUE_STATE
title: "_WDF_IO_QUEUE_STATE"
author: windows-driver-content
description: The WDF_IO_QUEUE_STATE enumeration contains values that identify the state of an I/O queue.
old-location: wdf\wdf_io_queue_state_umdf.htm
old-project: wdf
ms.assetid: c91b9ea0-8c42-4199-b161-2b43ba4a1833
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfIoQueueDriverNoRequests, wudfddi/WdfIoQueueNoRequests, *PWDF_IO_QUEUE_STATE, WdfIoQueueAcceptRequests, WDF_IO_QUEUE_STATE, umdf.wdf_io_queue_state, WdfIoQueueDispatchRequests, _WDF_IO_QUEUE_STATE, wudfddi/WdfIoQueueDriverNoRequests, wudfddi/WdfIoQueueAcceptRequests, wudfddi/WdfIoQueuePnpHeld, wudfddi/WDF_IO_QUEUE_STATE, WDF_IO_QUEUE_STATE enumeration, wdf.wdf_io_queue_state_umdf, umdfstructs_b0fa52c7-c536-43d3-b9a7-f63977ccb619.xml, wudfddi/WdfIoQueueDispatchRequests, WdfIoQueuePnpHeld, WdfIoQueueNoRequests
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wudfddi.h
apiname:
-	WDF_IO_QUEUE_STATE
product: Windows
targetos: Windows
req.typenames: "*PWDF_IO_QUEUE_STATE, WDF_IO_QUEUE_STATE"
req.product: Windows 10 or later.
---

# _WDF_IO_QUEUE_STATE enumeration


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


      The <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_io_queue_state.md">WDF_IO_QUEUE_STATE</a> enumeration contains values that identify the state of an I/O queue.


## -syntax


````
typedef enum _WDF_IO_QUEUE_STATE { 
  WdfIoQueueAcceptRequests    = 0x1,
  WdfIoQueueDispatchRequests  = 0x2,
  WdfIoQueueNoRequests        = 0x4,
  WdfIoQueueDriverNoRequests  = 0x8,
  WdfIoQueuePnpHeld           = 0x10
} WDF_IO_QUEUE_STATE;
````


## -enum-fields




### -field WdfIoQueueAcceptRequests

If this value is set to 1, the queue accepts requests by automatically forwarding them through the setting of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558946">IWDFIoQueue::ConfigureRequestDispatching</a> method or by manually forwarding each request through a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559081">IWDFIoRequest::ForwardToIoQueue</a> method. 

If this value is set to 0, the queue completes any automatically forwarded requests with "status canceled" or fails <a href="https://msdn.microsoft.com/library/windows/hardware/ff559081">IWDFIoRequest::ForwardToIoQueue</a> with "status busy".


### -field WdfIoQueueDispatchRequests

If this value is set to 1, the queue automatically presents requests to the driver, unless the queue is a <b>WdfIoQueueDispatchManual</b> type (see <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_io_queue_dispatch_type.md">WDF_IO_QUEUE_DISPATCH_TYPE</a>). 

If this value is set to 0, the queue does not automatically dispatch requests to the driver. The setting of this status does not prevent the driver from calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558967">IWDFIoQueue::RetrieveNextRequest</a> method to manually retrieve a request from the queue.


### -field WdfIoQueueNoRequests

If this value is set to 1, no requests are in the queue, even requests that can be presented to the driver and that can be returned from <a href="https://msdn.microsoft.com/library/windows/hardware/ff558967">IWDFIoQueue::RetrieveNextRequest</a>.


### -field WdfIoQueueDriverNoRequests

If this value is set to 1, there are no requests that the driver currently operates on that it received from the queue. 


### -field WdfIoQueuePnpHeld

If this value is set to 1, an event from the Plug and Play (PnP) subsystem suspended the queue from processing requests.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558946">IWDFIoQueue::ConfigureRequestDispatching</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558967">IWDFIoQueue::RetrieveNextRequest</a>



<a href="..\wudfddi_types\ne-wudfddi_types-_wdf_io_queue_dispatch_type.md">WDF_IO_QUEUE_DISPATCH_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559081">IWDFIoRequest::ForwardToIoQueue</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_IO_QUEUE_STATE enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

