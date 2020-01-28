---
UID: NC:sercx.EVT_SERCX2_PIO_TRANSMIT_ENABLE_READY_NOTIFICATION
title: EVT_SERCX2_PIO_TRANSMIT_ENABLE_READY_NOTIFICATION (sercx.h)
description: The EvtSerCx2PioTransmitEnableReadyNotification event callback function is called by version 2 of the serial framework extension (SerCx2) to enable the serial controller driver to notify SerCx2 when the transmit FIFO in the serial controller is ready to accept more data.
old-location: serports\evtsercx2piotransmitenablereadynotification.htm
tech.root: serports
ms.assetid: 05E5F48B-4E82-4BC3-B6D1-7E9E3435BDB3
ms.date: 04/23/2018
ms.keywords: 2/EvtSerCx2PioTransmitEnableReadyNotification, EVT_SERCX2_PIO_TRANSMIT_ENABLE_READY_NOTIFICATION, EVT_SERCX2_PIO_TRANSMIT_ENABLE_READY_NOTIFICATION callback, EvtSerCx2PioTransmitEnableReadyNotification, EvtSerCx2PioTransmitEnableReadyNotification callback function [Serial Ports], serports.evtsercx2piotransmitenablereadynotification
f1_keywords:
 - "sercx/EvtSerCx2PioTransmitEnableReadyNotification"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- 2.0\Sercx.h
api_name:
- EvtSerCx2PioTransmitEnableReadyNotification
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_SERCX2_PIO_TRANSMIT_ENABLE_READY_NOTIFICATION callback function


## -description


The <i>EvtSerCx2PioTransmitEnableReadyNotification</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to enable the serial controller driver to notify SerCx2 when the transmit FIFO in the serial controller is ready to accept more data.


## -parameters




### -param PioTransmit [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a> handle to a PIO-transmit object. The serial controller driver previously called the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2piotransmitcreate">SerCx2PioTransmitCreate</a> method to create this object.


## -remarks



Your serial controller driver must implement this function. The driver registers the function in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2piotransmitcreate">SerCx2PioTransmitCreate</a> call that creates the PIO-transmit object.

If the ready notification for PIO-transmit transactions is enabled, the serial controller driver must call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2piotransmitready">SerCx2PioTransmitReady</a> method to notify SerCx2 when the driver detects that the transmit FIFO in the serial controller hardware is ready to accept more data. If the transmit FIFO is ready to accept data when the ready notification is enabled, the driver immediately calls this method to notify SerCx2.

The ready notification for a PIO-transmit transaction is a one-shot notification. After sending a ready notification to SerCx2, the serial controller driver sends no further notifications until SerCx2 calls the <i>EvtSerCx2PioTransmitEnableReadyNotification</i> function to enable another notification.

An <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_transmit_write_buffer">EvtSerCx2PioTransmitWriteBuffer</a> function call might only partially complete a PIO-transmit transaction because no more room is immediately available in the transmit FIFO to write more data. In this case, SerCx2 calls the <i>EvtSerCx2PioTransmitEnableReadyNotification</i> function to enable a ready notification, in which case the serial controller driver must notify SerCx2 when the transmit FIFO has room for more data. In response to this notification, SerCx2 resumes the partially completed transmit transaction by calling the <i>EvtSerCx2PioTransmitWriteBuffer</i> function again.

Typically, an <i>EvtSerCx2PioTransmitEnableReadyNotification</i> function enables an interrupt that occurs when the transmit FIFO in the serial controller is ready to accept more data. In response to this interrupt, the serial controller driver calls <b>SerCx2PioTransmitReady</b>.

No more than one ready notification can be pending at a time. SerCx2 never calls the <i>EvtSerCx2PioTransmitEnableReadyNotification</i> function if the ready notification is already enabled.

SerCx2 never calls the <i>EvtSerCx2PioTransmitWriteBuffer</i> function when the ready notification is enabled.

A pending ready notification can be canceled if the associated write request times out or is canceled. To cancel a ready notification for a PIO-transmit transaction, SerCx2 calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_transmit_cancel_ready_notification">EvtSerCx2PioTransmitCancelReadyNotification</a> event callback function.

For more information, see <a href="https://docs.microsoft.com/previous-versions/dn265336(v=vs.85)">SerCx2 PIO-Transmit Transactions</a>.


#### Examples

To define an <i>EvtSerCx2PioTransmitEnableReadyNotification</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSerCx2PioTransmitEnableReadyNotification</i> callback function that is named <code>MyPioTransmitEnableReadyNotification</code>, use the <b>EVT_SERCX2_PIO_TRANSMIT_ENABLE_READY_NOTIFICATION</b> function type, as shown in this code example:

<div class="code"><span codelanguage="cpp"><table>
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

<div class="code"><span codelanguage="cpp"><table>
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
The <b>EVT_SERCX2_PIO_TRANSMIT_ENABLE_READY_NOTIFICATION</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_PIO_TRANSMIT_ENABLE_READY_NOTIFICATION</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_transmit_write_buffer">EvtSerCx2PioTransmitWriteBuffer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-write">IRP_MJ_WRITE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2piotransmitcreate">SerCx2PioTransmitCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2piotransmitready">SerCx2PioTransmitReady</a>
 

 

