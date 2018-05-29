---
UID: NF:wdfio.WDF_IO_QUEUE_IDLE
title: WDF_IO_QUEUE_IDLE function
author: windows-driver-content
description: The WDF_IO_QUEUE_IDLE function returns TRUE if an I/O queue's state indicates that the queue is drained.
old-location: wdf\wdf_io_queue_idle.htm
old-project: wdf
ms.assetid: 9ad3be79-13ca-4bcb-b686-09e7563610f9
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFQueueObjectRef_f836bf9d-8d2c-48db-92cd-fbcef2a0faf6.xml, WDF_IO_QUEUE_IDLE, WDF_IO_QUEUE_IDLE function, kmdf.wdf_io_queue_idle, wdf.wdf_io_queue_idle, wdfio/WDF_IO_QUEUE_IDLE
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	None
-	None.dll
api_name:
-	WDF_IO_QUEUE_IDLE
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_IO_QUEUE_IDLE function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_IO_QUEUE_IDLE</b> function returns <b>TRUE</b> if an I/O queue's state indicates that the queue is drained.


## -parameters




### -param State [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/Ff552373">WDF_IO_QUEUE_STATE</a>-typed value that <a href="https://msdn.microsoft.com/library/windows/hardware/ff548437">WdfIoQueueGetState</a> returns.


## -returns



<b>WDF_IO_QUEUE_IDLE</b> returns <b>TRUE</b> if the specified queue state indicates that the queue is idle. Otherwise, the function returns <b>FALSE</b>.




## -remarks



An I/O queue is idle if the queue contains no I/O requests, and if all delivered requests have been completed or canceled. 

Your driver can call <b>WDF_IO_QUEUE_IDLE</b> after it has called <a href="https://msdn.microsoft.com/library/windows/hardware/ff548437">WdfIoQueueGetState</a>.

For more information about I/O queue states, see <a href="https://msdn.microsoft.com/library/windows/hardware/Ff552373">WDF_IO_QUEUE_STATE</a>.


#### Examples

The following code example is a routine that returns <b>TRUE</b> if a specified I/O queue is idle.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>BOOLEAN
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
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552363">WDF_IO_QUEUE_DRAINED</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552369">WDF_IO_QUEUE_PURGED</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552371">WDF_IO_QUEUE_READY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552375">WDF_IO_QUEUE_STOPPED</a>
 

 

