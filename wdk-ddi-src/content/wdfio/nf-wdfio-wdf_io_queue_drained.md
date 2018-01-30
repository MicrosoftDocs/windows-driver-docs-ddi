---
UID: NF:wdfio.WDF_IO_QUEUE_DRAINED
title: WDF_IO_QUEUE_DRAINED function
author: windows-driver-content
description: The WDF_IO_QUEUE_DRAINED function returns TRUE if the I/O queue's state indicates that the queue is drained.
old-location: wdf\wdf_io_queue_drained.htm
old-project: wdf
ms.assetid: 1b2384c3-6438-4456-b4fc-44211b8a3fb1
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: DFQueueObjectRef_ddc761b3-266a-4942-94ed-8ecca07575d1.xml, WDF_IO_QUEUE_DRAINED, WDF_IO_QUEUE_DRAINED function, kmdf.wdf_io_queue_drained, wdf.wdf_io_queue_drained, wdfio/WDF_IO_QUEUE_DRAINED
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: None
req.dll: 
req.irql: Any IRQL.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	None
-	None.dll
apiname:
-	WDF_IO_QUEUE_DRAINED
product: Windows
targetos: Windows
req.typenames: WDF_IO_QUEUE_STATE
req.product: Windows 10 or later.
---

# WDF_IO_QUEUE_DRAINED function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_IO_QUEUE_DRAINED</b> function returns <b>TRUE</b> if the I/O queue's state indicates that the queue is drained.


## -syntax


````
BOOLEAN WDF_IO_QUEUE_DRAINED(
  _In_ WDF_IO_QUEUE_STATE State
);
````


## -parameters




### -param State [in]

A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_io_queue_state.md">WDF_IO_QUEUE_STATE</a>-typed value that <a href="..\wdfio\nf-wdfio-wdfioqueuegetstate.md">WdfIoQueueGetState</a> returns.


## -returns


<b>WDF_IO_QUEUE_DRAINED</b> returns <b>TRUE</b> if the specified queue state indicates that the queue is drained. Otherwise, the function returns <b>FALSE</b>.



## -remarks


An I/O queue is drained if it is not accepting new I/O requests, and if all requests that were in the queue have been delivered to the driver.

Your driver can call <b>WDF_IO_QUEUE_DRAINED</b> after it has called <a href="..\wdfio\nf-wdfio-wdfioqueuegetstate.md">WdfIoQueueGetState</a>.

For more information about I/O queue states, see <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_io_queue_state.md">WDF_IO_QUEUE_STATE</a>.



## -see-also

<a href="..\wdfio\nf-wdfio-wdf_io_queue_ready.md">WDF_IO_QUEUE_READY</a>

<a href="..\wdfio\nf-wdfio-wdf_io_queue_idle.md">WDF_IO_QUEUE_IDLE</a>

<a href="..\wdfio\nf-wdfio-wdf_io_queue_stopped.md">WDF_IO_QUEUE_STOPPED</a>

<a href="..\wdfio\nf-wdfio-wdf_io_queue_purged.md">WDF_IO_QUEUE_PURGED</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_IO_QUEUE_DRAINED function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

