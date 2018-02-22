---
UID: NF:wdfio.WDF_IO_QUEUE_STOPPED
title: WDF_IO_QUEUE_STOPPED function
author: windows-driver-content
description: The WDF_IO_QUEUE_STOPPED function returns TRUE if an I/O queue's state indicates that the queue is stopped.
old-location: wdf\wdf_io_queue_stopped.htm
old-project: wdf
ms.assetid: 8257c636-824d-4909-b0cb-76d72ac980fa
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: WDF_IO_QUEUE_STOPPED function, wdfio/WDF_IO_QUEUE_STOPPED, wdf.wdf_io_queue_stopped, WDF_IO_QUEUE_STOPPED, kmdf.wdf_io_queue_stopped, DFQueueObjectRef_55457efd-0074-4be5-b078-bb223963bfca.xml
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
-	WDF_IO_QUEUE_STOPPED
product: Windows
targetos: Windows
req.typenames: WDF_IO_QUEUE_STATE
req.product: Windows 10 or later.
---

# WDF_IO_QUEUE_STOPPED function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_IO_QUEUE_STOPPED</b> function returns <b>TRUE</b> if an I/O queue's state indicates that the queue is stopped.


## -syntax


````
BOOLEAN WDF_IO_QUEUE_STOPPED(
  _In_ WDF_IO_QUEUE_STATE State
);
````


## -parameters




### -param State [in]

A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_io_queue_state.md">WDF_IO_QUEUE_STATE</a>-typed value that <a href="..\wdfio\nf-wdfio-wdfioqueuegetstate.md">WdfIoQueueGetState</a> returns.


## -returns



<b>WDF_IO_QUEUE_STOPPED</b> returns <b>TRUE</b> if the specified queue state indicates that the queue is stopped. Otherwise, the function returns <b>FALSE</b>.




## -remarks



An I/O queue is stopped if it can accept new I/O requests but the framework is not delivering them to the driver. 

Your driver can call <b>WDF_IO_QUEUE_STOPPED</b> after it has called <a href="..\wdfio\nf-wdfio-wdfioqueuegetstate.md">WdfIoQueueGetState</a>.

For more information about I/O queue states, see <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_io_queue_state.md">WDF_IO_QUEUE_STATE</a>.


#### Examples

The following code example is a routine that returns <b>TRUE</b> if a specified I/O queue is stopped.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>BOOLEAN
IsQueueStopped(
    IN WDFQUEUE Queue
    )
{
    WDF_IO_QUEUE_STATE queueStatus;
    queueStatus = WdfIoQueueGetState(
                                     Queue,
                                     NULL,
                                     NULL
                                     );
    return (WDF_IO_QUEUE_STOPPED(queueStatus)) ? TRUE : FALSE;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfio\nf-wdfio-wdf_io_queue_idle.md">WDF_IO_QUEUE_IDLE</a>



<a href="..\wdfio\nf-wdfio-wdf_io_queue_idle.md">WDF_IO_QUEUE_IDLE</a>



<a href="..\wdfio\nf-wdfio-wdf_io_queue_ready.md">WDF_IO_QUEUE_READY</a>



<a href="..\wdfio\nf-wdfio-wdf_io_queue_ready.md">WDF_IO_QUEUE_READY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_IO_QUEUE_STOPPED function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

