---
UID: NC:sercx.EVT_SERCX2_PIO_TRANSMIT_ENABLE_READY_NOTIFICATION
title: EVT_SERCX2_PIO_TRANSMIT_ENABLE_READY_NOTIFICATION
author: windows-driver-content
description: The EvtSerCx2PioTransmitEnableReadyNotification event callback function is called by version 2 of the serial framework extension (SerCx2) to enable the serial controller driver to notify SerCx2 when the transmit FIFO in the serial controller is ready to accept more data.
old-location: serports\evtsercx2piotransmitenablereadynotification.htm
old-project: serports
ms.assetid: 05E5F48B-4E82-4BC3-B6D1-7E9E3435BDB3
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: 2/EvtSerCx2PioTransmitEnableReadyNotification, EVT_SERCX2_PIO_TRANSMIT_ENABLE_READY_NOTIFICATION, EvtSerCx2PioTransmitEnableReadyNotification, EvtSerCx2PioTransmitEnableReadyNotification callback function [Serial Ports], serports.evtsercx2piotransmitenablereadynotification
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
-	EvtSerCx2PioTransmitEnableReadyNotification
product: Windows
targetos: Windows
req.typenames: SENSOR_VALUE_PAIR, *PSENSOR_VALUE_PAIR
req.product: Windows 10 or later.
---

# EVT_SERCX2_PIO_TRANSMIT_ENABLE_READY_NOTIFICATION callback


## -description


The <i>EvtSerCx2PioTransmitEnableReadyNotification</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to enable the serial controller driver to notify SerCx2 when the transmit FIFO in the serial controller is ready to accept more data.


## -parameters




### -param PioTransmit [in]

A <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a> handle to a PIO-transmit object. The serial controller driver previously called the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265269">SerCx2PioTransmitCreate</a> method to create this object.


## -returns



None.




## -remarks



Your serial controller driver must implement this function. The driver registers the function in the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265269">SerCx2PioTransmitCreate</a> call that creates the PIO-transmit object.

If the ready notification for PIO-transmit transactions is enabled, the serial controller driver must call the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265273">SerCx2PioTransmitReady</a> method to notify SerCx2 when the driver detects that the transmit FIFO in the serial controller hardware is ready to accept more data. If the transmit FIFO is ready to accept data when the ready notification is enabled, the driver immediately calls this method to notify SerCx2.

The ready notification for a PIO-transmit transaction is a one-shot notification. After sending a ready notification to SerCx2, the serial controller driver sends no further notifications until SerCx2 calls the <i>EvtSerCx2PioTransmitEnableReadyNotification</i> function to enable another notification.

An <a href="https://msdn.microsoft.com/28DD175B-9869-4CFC-9BDD-172DA7E015DE">EvtSerCx2PioTransmitWriteBuffer</a> function call might only partially complete a PIO-transmit transaction because no more room is immediately available in the transmit FIFO to write more data. In this case, SerCx2 calls the <i>EvtSerCx2PioTransmitEnableReadyNotification</i> function to enable a ready notification, in which case the serial controller driver must notify SerCx2 when the transmit FIFO has room for more data. In response to this notification, SerCx2 resumes the partially completed transmit transaction by calling the <i>EvtSerCx2PioTransmitWriteBuffer</i> function again.

Typically, an <i>EvtSerCx2PioTransmitEnableReadyNotification</i> function enables an interrupt that occurs when the transmit FIFO in the serial controller is ready to accept more data. In response to this interrupt, the serial controller driver calls <b>SerCx2PioTransmitReady</b>.

No more than one ready notification can be pending at a time. SerCx2 never calls the <i>EvtSerCx2PioTransmitEnableReadyNotification</i> function if the ready notification is already enabled.

SerCx2 never calls the <i>EvtSerCx2PioTransmitWriteBuffer</i> function when the ready notification is enabled.

A pending ready notification can be canceled if the associated write request times out or is canceled. To cancel a ready notification for a PIO-transmit transaction, SerCx2 calls the <a href="https://msdn.microsoft.com/2483F6A6-67FE-4C75-9872-53F66B4BD658">EvtSerCx2PioTransmitCancelReadyNotification</a> event callback function.

For more information, see <a href="https://msdn.microsoft.com/3BEF9A3D-1FEF-4626-B07F-1670359062AF">SerCx2 PIO-Transmit Transactions</a>.


#### Examples

To define an <i>EvtSerCx2PioTransmitEnableReadyNotification</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSerCx2PioTransmitEnableReadyNotification</i> callback function that is named <code>MyPioTransmitEnableReadyNotification</code>, use the <b>EVT_SERCX2_PIO_TRANSMIT_ENABLE_READY_NOTIFICATION</b> function type, as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SERCX2_PIO_TRANSMIT_ENABLE_READY_NOTIFICATION  MyPioTransmitEnableReadyNotification;</pre>
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
  MyPioTransmitEnableReadyNotification(
    SERCX2PIOTRANSMIT  PioTransmit
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_SERCX2_PIO_TRANSMIT_ENABLE_READY_NOTIFICATION</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_PIO_TRANSMIT_ENABLE_READY_NOTIFICATION</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/28DD175B-9869-4CFC-9BDD-172DA7E015DE">EvtSerCx2PioTransmitWriteBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265269">SerCx2PioTransmitCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265273">SerCx2PioTransmitReady</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX2_PIO_TRANSMIT_ENABLE_READY_NOTIFICATION callback function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

