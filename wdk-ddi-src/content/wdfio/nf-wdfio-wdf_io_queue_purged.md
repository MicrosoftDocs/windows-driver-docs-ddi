---
UID: NF:wdfio.WDF_IO_QUEUE_PURGED
title: WDF_IO_QUEUE_PURGED function (wdfio.h)
description: The WDF_IO_QUEUE_PURGED function returns TRUE if an I/O queue's state indicates that the queue is drained.
old-location: wdf\wdf_io_queue_purged.htm
tech.root: wdf
ms.assetid: dbb061a6-a770-411c-9c3a-8453662b4362
ms.date: 02/26/2018
ms.keywords: DFQueueObjectRef_2d745708-c310-494a-aedc-362bdc930650.xml, WDF_IO_QUEUE_PURGED, WDF_IO_QUEUE_PURGED function, kmdf.wdf_io_queue_purged, wdf.wdf_io_queue_purged, wdfio/WDF_IO_QUEUE_PURGED
f1_keywords:
 - "wdfio/WDF_IO_QUEUE_PURGED"
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
- WDF_IO_QUEUE_PURGED
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_IO_QUEUE_PURGED function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_IO_QUEUE_PURGED</b> function returns <b>TRUE</b> if an I/O queue's state indicates that the queue is drained.


## -parameters




### -param State [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/ne-wdfio-_wdf_io_queue_state">WDF_IO_QUEUE_STATE</a>-typed value that <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuegetstate">WdfIoQueueGetState</a> returns.


## -returns



<b>WDF_IO_QUEUE_PURGED</b> returns <b>TRUE</b> if the specified queue state indicates that the queue is purged. Otherwise, the function returns <b>FALSE</b>.




## -remarks



An I/O queue is purged if the queue is empty and not accepting new I/O requests, and if all requests that were in the queue have been canceled.

Your driver can call <b>WDF_IO_QUEUE_PURGED</b> after it has called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdfioqueuegetstate">WdfIoQueueGetState</a>.

For more information about I/O queue states, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/ne-wdfio-_wdf_io_queue_state">WDF_IO_QUEUE_STATE</a>.


#### Examples

The following code example is a routine that returns <b>TRUE</b> if a specified I/O queue is purged.

```cpp
BOOLEAN
IsQueuePurged(
    IN WDFQUEUE Queue
    )
{
    WDF_IO_QUEUE_STATE queueStatus;
    queueStatus = WdfIoQueueGetState(
                                     Queue,
                                     NULL,
                                     NULL
                                     );
    return (WDF_IO_QUEUE_PURGED(queueStatus)) ? TRUE : FALSE;
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdf_io_queue_drained">WDF_IO_QUEUE_DRAINED</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdf_io_queue_idle">WDF_IO_QUEUE_IDLE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdf_io_queue_ready">WDF_IO_QUEUE_READY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nf-wdfio-wdf_io_queue_stopped">WDF_IO_QUEUE_STOPPED</a>
 

 

