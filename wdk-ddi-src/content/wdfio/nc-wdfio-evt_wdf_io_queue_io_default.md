---
UID: NC:wdfio.EVT_WDF_IO_QUEUE_IO_DEFAULT
title: EVT_WDF_IO_QUEUE_IO_DEFAULT
author: windows-driver-content
description: A driver's EvtIoDefault event callback function processes a specified I/O request.
old-location: wdf\evtiodefault.htm
tech.root: wdf
ms.assetid: 0b834d01-5603-43e8-9b74-9292610cc06d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFQueueObjectRef_aca0c34e-8d7d-4eba-b1ac-c91928db896e.xml, EVT_WDF_IO_QUEUE_IO_DEFAULT, EVT_WDF_IO_QUEUE_IO_DEFAULT callback, EvtIoDefault, EvtIoDefault callback function, kmdf.evtiodefault, wdf.evtiodefault, wdfio/EvtIoDefault
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Universal
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdfio.h
api_name:
-	EvtIoDefault
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_IO_QUEUE_IO_DEFAULT callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtIoDefault</i> event callback function processes a specified I/O request.


## -parameters




### -param Queue [in]

A handle to the framework queue object that is associated with the I/O request.


### -param Request [in]

A handle to a framework request object.


## -returns



None




## -remarks



A driver registers an <i>EvtIoDefault</i> callback function when it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff547401">WdfIoQueueCreate</a>. For more information about calling <b>WdfIoQueueCreate</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-i-o-queues">Creating I/O Queues</a>.

If a driver has registered an <i>EvtIoDefault</i> callback function for a device's I/O queue, the callback function receives every I/O request from the queue, unless request-specific callback functions have also been registered. For more information about request-specific callback functions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/request-handlers">Request Handlers</a>. 

A driver's <i>EvtIoDefault</i> callback function can also receive file creation requests. For more information about receiving file creation requests, see <a href="https://msdn.microsoft.com/93ec5dd7-8ef0-4cea-9253-ea5d7869d4b8">Framework File Objects</a>.

The <i>EvtIoDefault</i> callback function must process each received I/O request in some manner. For more information, see <a href="https://msdn.microsoft.com/90b1cc51-da40-45c1-9d6c-57f637f474d9">Processing I/O Requests</a>.

Most I/O operations require an input buffer, an output buffer, or both. For information about how the driver can access a request's buffers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers in Framework-Based Drivers</a>.

This callback function can be called at IRQL &lt;= DISPATCH_LEVEL, unless the <b>ExecutionLevel</b> member of the device or driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure is set to <b>WdfExecutionLevelPassive</b>.

If the IRQL is PASSIVE_LEVEL, the framework calls the callback function within a <a href="https://msdn.microsoft.com/3781498a-45e9-4f24-8fd2-830eed61298c">critical region</a>.

For more information about IRQL levels for request handlers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-automatic-synchronization">Using Automatic Synchronization</a>.

A driver's <i>EvtIoDefault</i> callback function should not call the following queue object methods:<dl>
<dd>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547412">WdfIoQueueDrainSynchronously</a>
</dd>
<dd>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548449">WdfIoQueuePurgeSynchronously</a>
</dd>
<dd>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548489">WdfIoQueueStopSynchronously</a>
</dd>
</dl>



#### Examples

To define an <i>EvtIoDefault</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtIoDefault</i> callback function that is named <i>MyIoDefault</i>, use the <b>EVT_WDF_IO_QUEUE_IO_DEFAULT</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_IO_QUEUE_IO_DEFAULT  MyIoDefault;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
 MyIoDefault (
    WDFQUEUE  Queue,
    WDFREQUEST  Request
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_IO_QUEUE_IO_DEFAULT</b> function type is defined in the Wdfio.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_IO_QUEUE_IO_DEFAULT</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also




<a href="https://msdn.microsoft.com/3e3c4c53-e557-4bd1-8b7d-be59dde4b9ce">EvtIoDeviceControl</a>



<a href="https://msdn.microsoft.com/268d2323-57a3-4674-90e6-d7142804175b">EvtIoInternalDeviceControl</a>



<a href="https://msdn.microsoft.com/d6fbb153-1355-4e94-b5d3-a218bd8c565d">EvtIoRead</a>



<a href="https://msdn.microsoft.com/5a0fa3b4-d020-4664-afa4-352573d4f079">EvtIoWrite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547401">WdfIoQueueCreate</a>
 

 

