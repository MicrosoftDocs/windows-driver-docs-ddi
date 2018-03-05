---
UID: NC:sercx.EVT_SERCX2_PIO_RECEIVE_ENABLE_READY_NOTIFICATION
title: EVT_SERCX2_PIO_RECEIVE_ENABLE_READY_NOTIFICATION
author: windows-driver-content
description: The EvtSerCx2PioReceiveEnableReadyNotification event callback function is called by version 2 of the serial framework extension (SerCx2) to enable the serial controller driver to notify SerCx2 when the serial controller receives new data.
old-location: serports\evtsercx2pioreceiveenablereadynotification.htm
old-project: serports
ms.assetid: DDD17DF3-9457-40D1-BE18-0A1CAED1389B
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: 2/EvtSerCx2PioReceiveEnableReadyNotification, EVT_SERCX2_PIO_RECEIVE_ENABLE_READY_NOTIFICATION, EvtSerCx2PioReceiveEnableReadyNotification, EvtSerCx2PioReceiveEnableReadyNotification callback function [Serial Ports], serports.evtsercx2pioreceiveenablereadynotification
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: sercx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.1.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Called at IRQL <= DISPATCH_LEVEL.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	2.0\Sercx.h
api_name:
-	EvtSerCx2PioReceiveEnableReadyNotification
product: Windows
targetos: Windows
req.typenames: SENSOR_VALUE_PAIR, *PSENSOR_VALUE_PAIR
req.product: Windows 10 or later.
---

# EVT_SERCX2_PIO_RECEIVE_ENABLE_READY_NOTIFICATION callback


## -description


The <i>EvtSerCx2PioReceiveEnableReadyNotification</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to enable the serial controller driver to notify SerCx2 when the serial controller receives new data.


## -prototype


````
EVT_SERCX2_PIO_RECEIVE_ENABLE_READY_NOTIFICATION EvtSerCx2PioReceiveEnableReadyNotification;

VOID EvtSerCx2PioReceiveEnableReadyNotification(
  _In_ SERCX2PIORECEIVE PioReceive
)
{ ... }
````


## -parameters




### -param PioReceive [in]

A <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIORECEIVE</a> handle to a PIO-receive object. The serial controller driver previously called the <a href="..\sercx\nf-sercx-sercx2pioreceivecreate.md">SerCx2PioReceiveCreate</a> method to create this object.


## -returns



None.




## -remarks



Your serial controller driver must implement this function. The driver registers the function in the <a href="..\sercx\nf-sercx-sercx2pioreceivecreate.md">SerCx2PioReceiveCreate</a> call that creates the PIO-receive object.

After the <i>EvtSerCx2PioReceiveEnableReadyNotification</i> function is called to enable a ready notification for a PIO-receive transaction, the serial controller driver must call the <a href="..\sercx\nf-sercx-sercx2pioreceiveready.md">SerCx2PioReceiveReady</a> method to notify SerCx2 when the driver detects that one or more bytes of data are available to be read from the receive FIFO in the serial controller hardware. If data is already available in the receive FIFO when the ready notification is enabled, the driver immediately calls this method to notify SerCx2.

The ready notification for a PIO-receive transaction is a one-shot notification. After sending a ready notification to SerCx2, the serial controller driver sends no further notifications until SerCx2 calls the <i>EvtSerCx2PioReceiveEnableReadyNotification</i> function to enable another notification.

An <a href="..\sercx\nc-sercx-evt_sercx2_pio_receive_read_buffer.md">EvtSerCx2PioReceiveReadBuffer</a> event callback function call might only partially complete a PIO-receive transaction because no more data is immediately available to be read from the receive FIFO. In this case, SerCx2 calls the <i>EvtSerCx2PioReceiveEnableReadyNotification</i> function to enable a ready notification, in which case the serial controller driver must notify SerCx2 when the receive FIFO contains more data. In response to this notification, SerCx2 resumes the partially completed receive transaction by calling the <i>EvtSerCx2PioReceiveReadBuffer</i> function again.

Typically, an <i>EvtSerCx2PioReceiveEnableReadyNotification</i> function enables an interrupt that occurs when the serial controller has more data available to be read.  In response to this interrupt, the serial controller driver calls <b>SerCx2PioReceiveReady</b>.

No more than one ready notification can be pending at a time. After SerCx2 calls the <i>EvtSerCx2PioReceiveEnableReadyNotification</i> function to enable a ready notification, SerCx2 does not call this function again until the controller driver calls <b>SerCx2PioReceiveReady</b>.

SerCx2 never calls the <i>EvtSerCx2PioReceiveReadBuffer</i> function when the ready notification is enabled.

A pending ready notification can be canceled if the associated read request times out or is canceled. To cancel a ready notification for a PIO-receive transaction, SerCx2 calls the <a href="..\sercx\nc-sercx-evt_sercx2_pio_receive_cancel_ready_notification.md">EvtSerCx2PioReceiveCancelReadyNotification</a> event callback function.

SerCx2 uses ready notifications to efficiently manage interval time-outs that occur during the handling of read requests that are processed as PIO-receive transactions.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265332">SerCx2 PIO-Receive Transactions</a>.


#### Examples

To define an <i>EvtSerCx2PioReceiveEnableReadyNotification</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSerCx2PioReceiveEnableReadyNotification</i> callback function that is named <code>MyPioReceiveEnableReadyNotification</code>, use the <b>EVT_SERCX2_PIO_RECEIVE_ENABLE_READY_NOTIFICATION</b> function type, as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SERCX2_PIO_RECEIVE_ENABLE_READY_NOTIFICATION  MyPioReceiveEnableReadyNotification;</pre>
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
  MyPioReceiveEnableReadyNotification(
    SERCX2PIORECEIVE  PioReceive
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_SERCX2_PIO_RECEIVE_ENABLE_READY_NOTIFICATION</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_PIO_RECEIVE_ENABLE_READY_NOTIFICATION</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also

<a href="..\sercx\nc-sercx-evt_sercx2_pio_receive_cleanup_transaction.md">EvtSerCx2PioReceiveCleanupTransaction</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIORECEIVE</a>



<a href="..\sercx\nf-sercx-sercx2pioreceiveready.md">SerCx2PioReceiveReady</a>



<a href="..\sercx\nc-sercx-evt_sercx2_pio_receive_cancel_ready_notification.md">EvtSerCx2PioReceiveCancelReadyNotification</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a>



<a href="..\sercx\nf-sercx-sercx2pioreceivecreate.md">SerCx2PioReceiveCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX2_PIO_RECEIVE_ENABLE_READY_NOTIFICATION callback function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

