---
UID: NC:wdfusb.EVT_WDF_USB_READER_COMPLETION_ROUTINE
title: EVT_WDF_USB_READER_COMPLETION_ROUTINE (wdfusb.h)
description: A driver's EvtUsbTargetPipeReadComplete event callback function informs the driver that a continuous reader has successfully completed a read request.
old-location: wdf\evtusbtargetpipereadcomplete.htm
tech.root: wdf
ms.assetid: da762d78-6d73-4ab9-83a8-297c6f48855b
ms.date: 02/26/2018
ms.keywords: DFUsbRef_6c37ab84-2c88-41d5-8a63-3e74207083ed.xml, EVT_WDF_USB_READER_COMPLETION_ROUTINE, EVT_WDF_USB_READER_COMPLETION_ROUTINE callback, EvtUsbTargetPipeReadComplete, EvtUsbTargetPipeReadComplete callback function, kmdf.evtusbtargetpipereadcomplete, wdf.evtusbtargetpipereadcomplete, wdfusb/EvtUsbTargetPipeReadComplete
ms.topic: callback
f1_keywords:
 - "wdfusb/EvtUsbTargetPipeReadComplete"
req.header: wdfusb.h
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
req.irql: "<=DISPATCH_LEVEL  (See Remarks section.)"
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- WdfUsb.h
api_name:
- EvtUsbTargetPipeReadComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_USB_READER_COMPLETION_ROUTINE callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtUsbTargetPipeReadComplete</i> event callback function informs the driver that a continuous reader has successfully completed a read request.


## -parameters




### -param Pipe [in]

A handle to a framework pipe object.


### -param Buffer [in]

A handle to a framework memory object that represents a buffer that contains data from the device.


### -param NumBytesTransferred [in]

The number of bytes of data that are in the read buffer.


### -param Context [in]

Driver-defined context information that the driver specified in the <b>EvtUsbTargetPipeReadCompleteContext</b> member of the pipe's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/ns-wdfusb-_wdf_usb_continuous_reader_config">WDF_USB_CONTINUOUS_READER_CONFIG</a> structure. 


## -returns



None




## -remarks



To register an <i>EvtUsbTargetPipeReadComplete</i> callback function, the driver must place the function's address in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/ns-wdfusb-_wdf_usb_continuous_reader_config">WDF_USB_CONTINUOUS_READER_CONFIG</a> structure.

If a driver has created a continuous reader for a USB pipe, the framework calls the driver's <i>EvtUsbTargetPipeReadComplete</i> callback function each time the driver's I/O target successfully completes a read request. The callback function is called at the IRQL at which the I/O target completed the read request, which is typically IRQL = DISPATCH_LEVEL, but no higher than DISPATCH_LEVEL. (If the I/O target does not successfully complete a request, the framework calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nc-wdfusb-evt_wdf_usb_readers_failed">EvtUsbTargetPipeReadersFailed</a> callback function.) 

To access the buffer that contains data that was read from the device, the driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfmemory/nf-wdfmemory-wdfmemorygetbuffer">WdfMemoryGetBuffer</a>. The framework writes the data into the buffer, after the header that is defined by the <b>HeaderLength</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/ns-wdfusb-_wdf_usb_continuous_reader_config">WDF_USB_CONTINUOUS_READER_CONFIG</a> structure. Note that the pointer that <b>WdfMemoryGetBuffer</b> returns points to the beginning of the header, but the <i>EvtUsbTargetPipeReadComplete</i> callback function's <i>NumBytesTransferred</i> parameter does <i>not</i> include the header's length.

By default, the framework deletes the buffer's memory object after the <i>EvtUsbTargetPipeReadComplete</i> callback function returns. However, you might want the memory object to remain valid after the callback function returns. For example, you might want your driver to store the object handle in the framework pipe object's context space so that the driver can process the memory object's contents after the callback function returns. To extend the lifetime of the memory object, the callback function must pass the memory object's handle to <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfobjectreference">WdfObjectReference</a>. Subsequently, the driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfobjectdereference">WdfObjectDereference</a> so that the framework can delete the object.

The framework synchronizes calls to the <i>EvtUsbTargetPipeReadComplete</i> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nc-wdfusb-evt_wdf_usb_readers_failed">EvtUsbTargetPipeReadersFailed</a> callback functions according to the following rules:

<ul>
<li>
These callback functions do not run simultaneously for an individual USB pipe.

</li>
<li>
If the driver creates multiple continuous readers for multiple USB pipes, with multiple <i>EvtUsbTargetPipeReadComplete</i> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nc-wdfusb-evt_wdf_usb_readers_failed">EvtUsbTargetPipeReadersFailed</a> callback functions, the multiple callback functions can run simultaneously.

</li>
<li>
If the driver has specified the default <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/ns-wdfusb-_wdf_usb_continuous_reader_config">NumPendingReads</a> value or a value that is greater than 1, and if a read request completes while the <i>EvtUsbTargetPipeReadComplete</i> callback function is executing, the framework can call the <i>EvtUsbTargetPipeReadComplete</i> callback function again before the callback function returns.

</li>
<li>
The framework does not synchronize these callback functions with any other callback functions.

</li>
</ul>
In the <b>BufferAttributes</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/ns-wdfusb-_wdf_usb_continuous_reader_config">WDF_USB_CONTINUOUS_READER_CONFIG</a> structure, your driver can specify <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/nc-wdfobject-evt_wdf_object_context_cleanup">EvtCleanupCallback</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/nc-wdfobject-evt_wdf_object_context_destroy">EvtDestroyCallback</a> callback functions for the memory object. If you specify an <i>EvtCleanupCallback</i> callback function, the framework will call that callback function when it attempts to delete the memory object, after the <i>EvtUsbTargetPipeReadComplete</i> callback function returns. If the <i>EvtUsbTargetPipeReadComplete</i> callback function has called <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfobjectreference">WdfObjectReference</a>, the <i>EvtCleanupCallback</i> callback function (if provided) must not call <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfobjectdereference">WdfObjectDereference</a>.

The driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfobjectdereference">WdfObjectDereference</a> when it has finished using the memory object. The framework can then call the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/nc-wdfobject-evt_wdf_object_context_destroy">EvtDestroyCallback</a> callback function (if provided) and delete the memory object.

For more information about the <i>EvtUsbTargetPipeReadComplete</i> callback function and USB I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/usb-i-o-targets">USB I/O Targets</a>.


#### Examples

To define an <i>EvtUsbTargetPipeReadComplete</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtUsbTargetPipeReadComplete</i> callback function that is named <i>MyUsbTargetPipeReadComplete</i>, use the <b>EVT_WDF_USB_READER_COMPLETION_ROUTINE</b> type as shown in this code example:

To define an <i>EvtUsbTargetPipeReadComplete</i> callback function that is named <b>MyUsbTargetPipeReadComplete</b>, you must first provide a function declaration that SDV and other verification tools require, as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_USB_READER_COMPLETION_ROUTINE  MyUsbTargetPipeReadComplete;</pre>
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
 MyUsbTargetPipeReadComplete (
    WDFUSBPIPE  Pipe,
    WDFMEMORY  Buffer,
    size_t  NumBytesTransferred,
    WDFCONTEXT  Context
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_USB_READER_COMPLETION_ROUTINE</b> function type is defined in the WdfUsb.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_USB_READER_COMPLETION_ROUTINE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nc-wdfusb-evt_wdf_usb_readers_failed">EvtUsbTargetPipeReadersFailed</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/ns-wdfusb-_wdf_usb_continuous_reader_config">WDF_USB_CONTINUOUS_READER_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfmemory/nf-wdfmemory-wdfmemorygetbuffer">WdfMemoryGetBuffer</a>
 

 

