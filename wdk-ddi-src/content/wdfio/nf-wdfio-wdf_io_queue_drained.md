---
UID: NF:wdfio.WDF_IO_QUEUE_DRAINED
title: WDF_IO_QUEUE_DRAINED function (wdfio.h)
description: The WDF_IO_QUEUE_DRAINED function returns TRUE if the I/O queue's state indicates that the queue is drained.
old-location: wdf\wdf_io_queue_drained.htm
tech.root: wdf
ms.assetid: 1b2384c3-6438-4456-b4fc-44211b8a3fb1
ms.date: 02/26/2018
keywords: ["WDF_IO_QUEUE_DRAINED function"]
ms.keywords: DFQueueObjectRef_ddc761b3-266a-4942-94ed-8ecca07575d1.xml, WDF_IO_QUEUE_DRAINED, WDF_IO_QUEUE_DRAINED function, kmdf.wdf_io_queue_drained, wdf.wdf_io_queue_drained, wdfio/WDF_IO_QUEUE_DRAINED
f1_keywords:
 - "wdfio/WDF_IO_QUEUE_DRAINED"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- None
- None.dll
api_name:
- WDF_IO_QUEUE_DRAINED
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_IO_QUEUE_DRAINED function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_IO_QUEUE_DRAINED</b> function returns <b>TRUE</b> if the I/O queue's state indicates that the queue is drained.


## -parameters




### -param State [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/ne-wdfio-_wdf_io_queue_state">WDF_IO_QUEUE_STATE</a>-typed value that <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuegetstate">WdfIoQueueGetState</a> returns.


## -returns



<b>WDF_IO_QUEUE_DRAINED</b> returns <b>TRUE</b> if the specified queue state indicates that the queue is drained. Otherwise, the function returns <b>FALSE</b>.




## -remarks



An I/O queue is drained if it is not accepting new I/O requests, and if all requests that were in the queue have been delivered to the driver.

Your driver can call <b>WDF_IO_QUEUE_DRAINED</b> after it has called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuegetstate">WdfIoQueueGetState</a>.

For more information about I/O queue states, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/ne-wdfio-_wdf_io_queue_state">WDF_IO_QUEUE_STATE</a>.


#### Examples

The following code example is a routine that returns <b>TRUE</b> if a specified I/O queue is drained.

```cpp
BOOLEAN
IsQueueDrained(
    IN WDFQUEUE Queue
    )
{
    WDF_IO_QUEUE_STATE queueStatus;
    queueStatus = WdfIoQueueGetState(
                                     Queue,
                                     NULL,
                                     NULL
                                     );
    return (WDF_IO_QUEUE_DRAINED(queueStatus)) ? TRUE : FALSE;
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdf_io_queue_idle">WDF_IO_QUEUE_IDLE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdf_io_queue_purged">WDF_IO_QUEUE_PURGED</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdf_io_queue_ready">WDF_IO_QUEUE_READY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdf_io_queue_stopped">WDF_IO_QUEUE_STOPPED</a>
 

 

