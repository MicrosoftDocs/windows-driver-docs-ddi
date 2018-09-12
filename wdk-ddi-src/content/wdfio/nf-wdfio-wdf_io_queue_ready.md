---
UID: NF:wdfio.WDF_IO_QUEUE_READY
title: WDF_IO_QUEUE_READY function
author: windows-driver-content
description: The WDF_IO_QUEUE_READY function returns TRUE if an I/O queue's state indicates that the queue is drained.
old-location: wdf\wdf_io_queue_ready.htm
tech.root: wdf
ms.assetid: 622e09eb-37ae-403e-9d18-acf2e7761b43
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFQueueObjectRef_d5c37eea-044b-41b6-9c0a-f910fef04d00.xml, WDF_IO_QUEUE_READY, WDF_IO_QUEUE_READY function, kmdf.wdf_io_queue_ready, wdf.wdf_io_queue_ready, wdfio/WDF_IO_QUEUE_READY
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
-	WDF_IO_QUEUE_READY
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_IO_QUEUE_READY function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_IO_QUEUE_READY</b> function returns <b>TRUE</b> if an I/O queue's state indicates that the queue is drained.


## -parameters




### -param State [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/Ff552373">WDF_IO_QUEUE_STATE</a>-typed value that <a href="https://msdn.microsoft.com/library/windows/hardware/ff548437">WdfIoQueueGetState</a> returns.


## -returns



<b>WDF_IO_QUEUE_READY</b> returns <b>TRUE</b> if the specified queue state indicates that the queue is ready. Otherwise, the function returns <b>FALSE</b>.




## -remarks



An I/O queue is ready if the queue can accept and dispatch I/O requests.

Your driver can call <b>WDF_IO_QUEUE_READY</b> after it has called <a href="https://msdn.microsoft.com/library/windows/hardware/ff548437">WdfIoQueueGetState</a>.

For more information about I/O queue states, see <a href="https://msdn.microsoft.com/library/windows/hardware/Ff552373">WDF_IO_QUEUE_STATE</a>.


#### Examples

The following code example is a routine that returns <b>TRUE</b> if a specified I/O queue is ready.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>BOOLEAN
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
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552363">WDF_IO_QUEUE_DRAINED</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552368">WDF_IO_QUEUE_IDLE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552369">WDF_IO_QUEUE_PURGED</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552375">WDF_IO_QUEUE_STOPPED</a>
 

 

