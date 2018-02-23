---
UID: NE:wdfio._WDF_IO_QUEUE_STATE
title: "_WDF_IO_QUEUE_STATE"
author: windows-driver-content
description: The WDF_IO_QUEUE_STATE enumeration type identifies the status of a framework queue object. The enumerators are used as bit masks.
old-location: wdf\wdf_io_queue_state.htm
old-project: wdf
ms.assetid: d89c4d4c-d3c2-47fc-9eb8-e2eb8424d5cc
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: WdfIoQueueNoRequests, WDF_IO_QUEUE_STATE, WdfIoQueueAcceptRequests, wdfio/WdfIoQueuePnpHeld, wdfio/WdfIoQueueNoRequests, wdfio/WdfIoQueueDriverNoRequests, DFQueueObjectRef_210e9189-4d80-4c0f-930b-319af65697d2.xml, _WDF_IO_QUEUE_STATE, kmdf.wdf_io_queue_state, WDF_IO_QUEUE_STATE enumeration, wdfio/WdfIoQueueAcceptRequests, wdf.wdf_io_queue_state, WdfIoQueueDispatchRequests, WdfIoQueuePnpHeld, WdfIoQueueDriverNoRequests, wdfio/WdfIoQueueDispatchRequests, wdfio/WDF_IO_QUEUE_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Windows
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
req.irql: "<= DISPATCH_LEVEL (see Remarks section)"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfio.h
apiname:
-	WDF_IO_QUEUE_STATE
product: Windows
targetos: Windows
req.typenames: WDF_IO_QUEUE_STATE
req.product: Windows 10 or later.
---

# _WDF_IO_QUEUE_STATE enumeration


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_IO_QUEUE_STATE</b> enumeration type identifies the status of a framework queue object. The enumerators are used as bit masks.


## -syntax


````
typedef enum _WDF_IO_QUEUE_STATE { 
  WdfIoQueueAcceptRequests    = 0x01,
  WdfIoQueueDispatchRequests  = 0x02,
  WdfIoQueueNoRequests        = 0x04,
  WdfIoQueueDriverNoRequests  = 0x08,
  WdfIoQueuePnpHeld           = 0x10
} WDF_IO_QUEUE_STATE;
````


## -enum-fields




### -field WdfIoQueueAcceptRequests

If set, the I/O queue can accept new I/O requests from the I/O manager and requests that are forwarded by the <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceconfigurerequestdispatching.md">WdfDeviceConfigureRequestDispatching</a> and <a href="..\wdfrequest\nf-wdfrequest-wdfrequestforwardtoioqueue.md">WdfRequestForwardToIoQueue</a> (or <a href="..\wdfrequest\nf-wdfrequest-wdfrequestforwardtoparentdeviceioqueue.md">WdfRequestForwardToParentDeviceIoQueue</a>) methods. 

If not set, the framework cancels requests from the I/O manager and <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceconfigurerequestdispatching.md">WdfDeviceConfigureRequestDispatching</a> and fails requests from <a href="..\wdfrequest\nf-wdfrequest-wdfrequestforwardtoioqueue.md">WdfRequestForwardToIoQueue</a> (or <a href="..\wdfrequest\nf-wdfrequest-wdfrequestforwardtoparentdeviceioqueue.md">WdfRequestForwardToParentDeviceIoQueue</a>) with STATUS_WDF_BUSY.


### -field WdfIoQueueDispatchRequests

If set, the framework delivers the queue's requests to the driver (unless the <b>WdfIoQueuePnpHeld</b> bit is also set). If not set, the driver cannot obtain requests from the queue. 


### -field WdfIoQueueNoRequests

If set, the I/O queue is empty.


### -field WdfIoQueueDriverNoRequests

If set, all requests that have been delivered to the driver have been completed. 


### -field WdfIoQueuePnpHeld

If set, the framework has stopped delivering requests to the driver because the underlying device is not in its working (D0) state.


## -remarks



The WDF_IO_QUEUE_STATE enumeration type is used as the return value for the <a href="..\wdfio\nf-wdfio-wdfioqueuegetstate.md">WdfIoQueueGetState</a> method.

The following functions are defined in <i>wdfio.h</i>:






## -see-also

<a href="..\wdfio\nf-wdfio-wdfioqueuegetstate.md">WdfIoQueueGetState</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_IO_QUEUE_STATE enumeration%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

