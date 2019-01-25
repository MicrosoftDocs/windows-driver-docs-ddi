---
UID: NC:sercx.EVT_SERCX2_PIO_TRANSMIT_CANCEL_READY_NOTIFICATION
title: EVT_SERCX2_PIO_TRANSMIT_CANCEL_READY_NOTIFICATION (sercx.h)
description: The EvtSerCx2PioTransmitCancelReadyNotification event callback function is called by version 2 of the serial framework extension (SerCx2) to cancel a ready notification that SerCx2 enabled in a previous call to the EvtSerCx2PioTransmitEnableReadyNotification event callback function.
old-location: serports\evtsercx2piotransmitcancelreadynotification.htm
tech.root: serports
ms.assetid: 2483F6A6-67FE-4C75-9872-53F66B4BD658
ms.date: 04/23/2018
ms.keywords: 2/EvtSerCx2PioTransmitCancelReadyNotification, EVT_SERCX2_PIO_TRANSMIT_CANCEL_READY_NOTIFICATION, EVT_SERCX2_PIO_TRANSMIT_CANCEL_READY_NOTIFICATION callback, EvtSerCx2PioTransmitCancelReadyNotification, EvtSerCx2PioTransmitCancelReadyNotification callback function [Serial Ports], serports.evtsercx2piotransmitcancelreadynotification
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
-	EvtSerCx2PioTransmitCancelReadyNotification
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_SERCX2_PIO_TRANSMIT_CANCEL_READY_NOTIFICATION callback function


## -description


The <i>EvtSerCx2PioTransmitCancelReadyNotification</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to cancel a ready notification that SerCx2 enabled in a previous call to the <a href="https://msdn.microsoft.com/05E5F48B-4E82-4BC3-B6D1-7E9E3435BDB3">EvtSerCx2PioTransmitEnableReadyNotification</a> event callback function.


## -parameters




### -param PioTransmit [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a> handle to a PIO-transmit object. The serial controller driver previously called the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265269">SerCx2PioTransmitCreate</a> method to create this object.


## -returns



The <i>EvtSerCx2PioTransmitCancelReadyNotification</i> function returns <b>TRUE</b> if the ready notification was successfully disabled and the serial controller driver can guarantee that this notification will not cause the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265273">SerCx2PioTransmitReady</a> method to be called. 

The function returns <b>FALSE</b> if the driver has already called <b>SerCx2PioTransmitReady</b>, or is about to call this method.




## -remarks



Your serial controller driver must implement this function. The driver registers the function in the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265269">SerCx2PioTransmitCreate</a> call that creates the PIO-transmit object.

If the associated write request times out or is canceled while a ready notification is enabled, SerCx2 calls the <i>EvtSerCx2PioTransmitCancelReadyNotification</i> function to cancel the pending notification. If this call returns <b>FALSE</b>, SerCx2 expects the serial controller driver to call <a href="https://msdn.microsoft.com/library/windows/hardware/dn265273">SerCx2PioTransmitReady</a>; only after this call does SerCx2 call the <a href="https://msdn.microsoft.com/48300C50-47B7-47DC-BDE5-3847E1EAE820">EvtSerCx2PioTransmitCleanupTransaction</a> event callback function, if it is implemented, and complete the request.

To cancel a previously enabled ready notification, the <i>EvtSerCx2PioTransmitCancelReadyNotification</i> function typically disables the interrupt in the serial controller that indicates that the transmit FIFO is ready to accept more data. SerCx2 enabled this interrupt in a previous call to the <a href="https://msdn.microsoft.com/05E5F48B-4E82-4BC3-B6D1-7E9E3435BDB3">EvtSerCx2PioTransmitEnableReadyNotification</a> function.

For more information, see <a href="https://msdn.microsoft.com/3BEF9A3D-1FEF-4626-B07F-1670359062AF">SerCx2 PIO-Transmit Transactions</a>.


#### Examples

To define an <i>EvtSerCx2PioTransmitCancelReadyNotification</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSerCx2PioTransmitCancelReadyNotification</i> callback function that is named <code>MyPioTransmitCancelReadyNotification</code>, use the <b>EVT_SERCX2_PIO_TRANSMIT_CANCEL_READY_NOTIFICATION</b> function type, as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SERCX2_PIO_TRANSMIT_CANCEL_READY_NOTIFICATION  MyPioTransmitCancelReadyNotification;</pre>
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
  MyPioTransmitCancelReadyNotification(
    SERCX2PIOTRANSMIT  PioTransmit
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_SERCX2_PIO_TRANSMIT_CANCEL_READY_NOTIFICATION</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_PIO_TRANSMIT_CANCEL_READY_NOTIFICATION</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/05E5F48B-4E82-4BC3-B6D1-7E9E3435BDB3">EvtSerCx2PioTransmitEnableReadyNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265269">SerCx2PioTransmitCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265273">SerCx2PioTransmitReady</a>
 

 

