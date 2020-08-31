---
UID: NF:wdfio.WDF_IO_QUEUE_IDLE
title: WDF_IO_QUEUE_IDLE function (wdfio.h)
description: The WDF_IO_QUEUE_IDLE function returns TRUE if an I/O queue's state indicates that the queue is drained.
old-location: wdf\wdf_io_queue_idle.htm
tech.root: wdf
ms.assetid: 9ad3be79-13ca-4bcb-b686-09e7563610f9
ms.date: 02/26/2018
keywords: ["WDF_IO_QUEUE_IDLE function"]
ms.keywords: DFQueueObjectRef_f836bf9d-8d2c-48db-92cd-fbcef2a0faf6.xml, WDF_IO_QUEUE_IDLE, WDF_IO_QUEUE_IDLE function, kmdf.wdf_io_queue_idle, wdf.wdf_io_queue_idle, wdfio/WDF_IO_QUEUE_IDLE
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
targetos: Windows
req.typenames: 
f1_keywords:
 - WDF_IO_QUEUE_IDLE
 - wdfio/WDF_IO_QUEUE_IDLE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - None
 - None.dll
api_name:
 - WDF_IO_QUEUE_IDLE
---

# WDF_IO_QUEUE_IDLE function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_IO_QUEUE_IDLE</b> function returns <b>TRUE</b> if an I/O queue's state indicates that the queue is drained.

## -parameters

### -param State 

[in]
A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/ne-wdfio-_wdf_io_queue_state">WDF_IO_QUEUE_STATE</a>-typed value that <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuegetstate">WdfIoQueueGetState</a> returns.

## -returns

<b>WDF_IO_QUEUE_IDLE</b> returns <b>TRUE</b> if the specified queue state indicates that the queue is idle. Otherwise, the function returns <b>FALSE</b>.

## -remarks

An I/O queue is idle if the queue contains no I/O requests, and if all delivered requests have been completed or canceled. 

Your driver can call <b>WDF_IO_QUEUE_IDLE</b> after it has called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuegetstate">WdfIoQueueGetState</a>.

For more information about I/O queue states, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/ne-wdfio-_wdf_io_queue_state">WDF_IO_QUEUE_STATE</a>.


#### Examples

The following code example is a routine that returns <b>TRUE</b> if a specified I/O queue is idle.

```cpp
BOOLEAN
IsQueueIdle(
    IN WDFQUEUE Queue
    )
{
    WDF_IO_QUEUE_STATE queueStatus;
    queueStatus = WdfIoQueueGetState(
                                     Queue,
                                     NULL,
                                     NULL
                                     );
    return (WDF_IO_QUEUE_IDLE(queueStatus)) ? TRUE : FALSE;
}
```

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdf_io_queue_drained">WDF_IO_QUEUE_DRAINED</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdf_io_queue_purged">WDF_IO_QUEUE_PURGED</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdf_io_queue_ready">WDF_IO_QUEUE_READY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdf_io_queue_stopped">WDF_IO_QUEUE_STOPPED</a>

