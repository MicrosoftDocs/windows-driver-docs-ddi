---
UID: NF:wdfio.WDF_IO_QUEUE_READY
title: WDF_IO_QUEUE_READY function (wdfio.h)
description: The WDF_IO_QUEUE_READY function returns TRUE if an I/O queue's state indicates that the queue is drained.
old-location: wdf\wdf_io_queue_ready.htm
tech.root: wdf
ms.assetid: 622e09eb-37ae-403e-9d18-acf2e7761b43
ms.date: 02/26/2018
keywords: ["WDF_IO_QUEUE_READY function"]
ms.keywords: DFQueueObjectRef_d5c37eea-044b-41b6-9c0a-f910fef04d00.xml, WDF_IO_QUEUE_READY, WDF_IO_QUEUE_READY function, kmdf.wdf_io_queue_ready, wdf.wdf_io_queue_ready, wdfio/WDF_IO_QUEUE_READY
f1_keywords:
 - "wdfio/WDF_IO_QUEUE_READY"
 - "WDF_IO_QUEUE_READY"
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
- WDF_IO_QUEUE_READY
targetos: Windows
req.typenames: 
---

# WDF_IO_QUEUE_READY function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_IO_QUEUE_READY</b> function returns <b>TRUE</b> if an I/O queue's state indicates that the queue is drained.


## -parameters




### -param State [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/ne-wdfio-_wdf_io_queue_state">WDF_IO_QUEUE_STATE</a>-typed value that <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuegetstate">WdfIoQueueGetState</a> returns.


## -returns



<b>WDF_IO_QUEUE_READY</b> returns <b>TRUE</b> if the specified queue state indicates that the queue is ready. Otherwise, the function returns <b>FALSE</b>.




## -remarks



An I/O queue is ready if the queue can accept and dispatch I/O requests.

Your driver can call <b>WDF_IO_QUEUE_READY</b> after it has called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuegetstate">WdfIoQueueGetState</a>.

For more information about I/O queue states, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/ne-wdfio-_wdf_io_queue_state">WDF_IO_QUEUE_STATE</a>.


#### Examples

The following code example is a routine that returns <b>TRUE</b> if a specified I/O queue is ready.

```cpp
BOOLEAN
IsQueueReady(
    IN WDFQUEUE Queue
    )
{
    WDF_IO_QUEUE_STATE queueStatus;
    queueStatus = WdfIoQueueGetState(
                                     Queue,
                                     NULL,
                                     NULL
                                     );
    return (WDF_IO_QUEUE_READY(queueStatus)) ? TRUE : FALSE;
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdf_io_queue_drained">WDF_IO_QUEUE_DRAINED</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdf_io_queue_idle">WDF_IO_QUEUE_IDLE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdf_io_queue_purged">WDF_IO_QUEUE_PURGED</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdf_io_queue_stopped">WDF_IO_QUEUE_STOPPED</a>
 

 

