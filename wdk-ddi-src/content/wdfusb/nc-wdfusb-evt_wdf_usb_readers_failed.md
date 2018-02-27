---
UID: NC:wdfusb.EVT_WDF_USB_READERS_FAILED
title: EVT_WDF_USB_READERS_FAILED
author: windows-driver-content
description: A driver's EvtUsbTargetPipeReadersFailed event callback function informs the driver that a continuous reader has reported an error while processing a read request.
old-location: wdf\evtusbtargetpipereadersfailed.htm
old-project: wdf
ms.assetid: a9e21f47-1a60-419a-839e-8869f9fd4dd7
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DFUsbRef_ba1b1293-cdd5-481e-8dd1-3633eb9084b9.xml, EVT_WDF_USB_READERS_FAILED, EvtUsbTargetPipeReadersFailed, EvtUsbTargetPipeReadersFailed callback function, kmdf.evtusbtargetpipereadersfailed, wdf.evtusbtargetpipereadersfailed, wdfusb/EvtUsbTargetPipeReadersFailed
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	WdfUsb.h
apiname:
-	EvtUsbTargetPipeReadersFailed
product: Windows
targetos: Windows
req.typenames: WDF_TRI_STATE, *PWDF_TRI_STATE
req.product: Windows 10 or later.
---

# EVT_WDF_USB_READERS_FAILED callback


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtUsbTargetPipeReadersFailed</i> event callback function informs the driver that a continuous reader has reported an error while processing a read request.


## -prototype


````
EVT_WDF_USB_READERS_FAILED EvtUsbTargetPipeReadersFailed;

BOOLEAN EvtUsbTargetPipeReadersFailed(
  _In_ WDFUSBPIPE  Pipe,
  _In_ NTSTATUS    Status,
  _In_ USBD_STATUS UsbdStatus
)
{ ... }
````


## -parameters




### -param Pipe [in]

A handle to a framework pipe object.


### -param Status [in]

The <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS value</a> that the pipe's I/O target returned.


### -param UsbdStatus [in]

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff539136">USBD_STATUS</a>-typed status value that the pipe's I/O target returned.


## -returns



The <i>EvtUsbTargetPipeReadersFailed</i> event callback function returns a Boolean value that, if <b>TRUE</b>, causes the framework to reset the USB pipe and then restart the continuous reader. If this function returns <b>FALSE</b>, the framework does not reset the device or restart the continuous reader. 




## -remarks



To register an <i>EvtUsbTargetPipeReadersFailed</i> callback function, the driver must place the function's address in a <a href="..\wdfusb\ns-wdfusb-_wdf_usb_continuous_reader_config.md">WDF_USB_CONTINUOUS_READER_CONFIG</a> structure. For  information about when to add this function pointer, see the Remarks section of <a href="..\wdfusb\nf-wdfusb-wdf_usb_continuous_reader_config_init.md">WDF_USB_CONTINUOUS_READER_CONFIG_INIT</a>.

If a driver has created a continuous reader for a USB pipe, the framework calls the driver's <i>EvtUsbTargetPipeReadersFailed</i> callback function if the driver's I/O target reports an error when it completes a read request. (If the I/O target successfully completes the request, the framework calls the driver's <a href="..\wdfusb\nc-wdfusb-evt_wdf_usb_reader_completion_routine.md">EvtUsbTargetPipeReadComplete</a> callback function.) 

Before the framework calls a driver's <i>EvtUsbTargetPipeReadersFailed</i> callback function, it tries to cancel all in-progress read requests. No read requests are in progress when the framework calls the <i>EvtUsbTargetPipeReadersFailed</i> callback function. The framework does not queue any additional read requests until the <i>EvtUsbTargetPipeReadersFailed</i> callback function returns.

For information about how the framework synchronizes calls to the <i>EvtUsbTargetPipeReadersFailed</i> callback function with calls to other callback functions, see the Remarks section of <a href="..\wdfusb\nc-wdfusb-evt_wdf_usb_reader_completion_routine.md">EvtUsbTargetPipeReadComplete</a>.

The <i>EvtUsbTargetPipeReadersFailed</i> callback function must not call <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetstop.md">WdfIoTargetStop</a> to stop the continuous reader's USB target. (In fact, calling <b>WdfIoTargetStop</b> in an <i>EvtUsbTargetPipeReadersFailed</i> callback function causes a deadlock.) In addition, the callback function must not call <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetstart.md">WdfIoTargetStart</a> to restart the continuous reader. Instead, the framework restarts the reader if the callback function returns <b>TRUE</b>. For more information about when to call <b>WdfIoTargetStart</b> and <b>WdfIoTargetStop</b> for a continuous reader, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/working-with-usb-pipes">Working with USB Pipes</a>.

If a driver does not provide an <i>EvtUsbTargetPipeReadersFailed</i> callback function and the driver's I/O target reports an error, the framework resets the USB pipe and restarts the continuous reader. 

For more information about the <i>EvtUsbTargetPipeReadersFailed</i> callback function and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.


#### Examples

To define an <i>EvtUsbTargetPipeReadersFailed</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtUsbTargetPipeReadersFailed</i> callback function that is named <i>MyUsbTargetPipeReadersFailed</i>, use the <b>EVT_WDF_USB_READERS_FAILED</b> type as shown in this code example:

To define an <i>EvtUsbTargetPipeReadersFailed</i> callback function that is named <b>MyUsbTargetPipeReadersFailed</b>, you must first provide a function declaration that SDV and other verification tools require, as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_USB_READERS_FAILED  MyUsbTargetPipeReadersFailed;</pre>
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
BOOLEAN
 MyUsbTargetPipeReadersFailed (
    WDFUSBPIPE  Pipe,
    NTSTATUS  Status,
    USBD_STATUS  UsbdStatus
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_USB_READERS_FAILED</b> function type is defined in the WdfUsb.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_USB_READERS_FAILED</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also

<a href="..\wdfusb\ns-wdfusb-_wdf_usb_continuous_reader_config.md">WDF_USB_CONTINUOUS_READER_CONFIG</a>



<a href="..\wdfusb\nc-wdfusb-evt_wdf_usb_reader_completion_routine.md">EvtUsbTargetPipeReadComplete</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_USB_READERS_FAILED callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

