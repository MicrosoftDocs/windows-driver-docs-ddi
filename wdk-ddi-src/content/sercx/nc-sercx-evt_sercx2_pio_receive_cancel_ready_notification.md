---
UID: NC:sercx.EVT_SERCX2_PIO_RECEIVE_CANCEL_READY_NOTIFICATION
title: EVT_SERCX2_PIO_RECEIVE_CANCEL_READY_NOTIFICATION (sercx.h)
description: The EvtSerCx2PioReceiveCancelReadyNotification event callback function is called by version 2 of the serial framework extension (SerCx2) to cancel a ready notification that SerCx2 enabled in a previous call to the EvtSerCx2PioReceiveEnableReadyNotification event callback function.
old-location: serports\evtsercx2pioreceivecancelreadynotification.htm
tech.root: serports
ms.assetid: 6173896B-FF8C-42A0-A42A-963F6311C059
ms.date: 04/23/2018
keywords: ["EVT_SERCX2_PIO_RECEIVE_CANCEL_READY_NOTIFICATION callback function"]
ms.keywords: 2/EvtSerCx2PioReceiveCancelReadyNotification, EVT_SERCX2_PIO_RECEIVE_CANCEL_READY_NOTIFICATION, EVT_SERCX2_PIO_RECEIVE_CANCEL_READY_NOTIFICATION callback, EvtSerCx2PioReceiveCancelReadyNotification, EvtSerCx2PioReceiveCancelReadyNotification callback function [Serial Ports], serports.evtsercx2pioreceivecancelreadynotification
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
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_SERCX2_PIO_RECEIVE_CANCEL_READY_NOTIFICATION
 - sercx/EVT_SERCX2_PIO_RECEIVE_CANCEL_READY_NOTIFICATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - 2.0\Sercx.h
api_name:
 - EvtSerCx2PioReceiveCancelReadyNotification
---

# EVT_SERCX2_PIO_RECEIVE_CANCEL_READY_NOTIFICATION callback function


## -description

The <i>EvtSerCx2PioReceiveCancelReadyNotification</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to cancel a ready notification that SerCx2 enabled in a previous call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_receive_enable_ready_notification">EvtSerCx2PioReceiveEnableReadyNotification</a> event callback function.

## -parameters

### -param PioReceive 

[in]
A <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIORECEIVE</a> handle to a PIO-receive object. The serial controller driver previously called the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2pioreceivecreate">SerCx2PioReceiveCreate</a> method to create this object.

## -returns

The <i>EvtSerCx2PioReceiveCancelReadyNotification</i> function returns <b>TRUE</b> if the ready notification was successfully disabled and the serial controller driver can guarantee that this notification will not cause the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2pioreceiveready">SerCx2PioReceiveReady</a> method to be called. The function returns <b>FALSE</b> if the driver has already called <b>SerCx2PioReceiveReady</b>, or is about to call this method.

## -remarks

Your serial controller driver must implement this function. The driver registers the function in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2pioreceivecreate">SerCx2PioReceiveCreate</a> call that creates the PIO-receive object.

If the associated read request times out or is canceled while a ready notification is enabled, SerCx2 calls the <i>EvtSerCx2PioReceiveCancelReadyNotification</i> function to cancel the pending notification. If this call returns <b>FALSE</b>, SerCx2 expects the serial controller driver to call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2pioreceiveready">SerCx2PioReceiveReady</a>; only after this call does SerCx2 call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_receive_cleanup_transaction">EvtSerCx2PioReceiveCleanupTransaction</a> event callback function, if it is implemented, and complete the request.

To cancel the ready notification, the <i>EvtSerCx2PioReceiveCancelReadyNotification</i> function typically disables the interrupt in the serial controller that indicates that more data is available to be read from the receive FIFO. This interrupt was enabled by a previous call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_receive_enable_ready_notification">EvtSerCx2PioReceiveEnableReadyNotification</a> function.

For more information, see <a href="https://docs.microsoft.com/previous-versions/dn265332(v=vs.85)">SerCx2 PIO-Receive Transactions</a>.


#### Examples

To define an <i>EvtSerCx2PioReceiveCancelReadyNotification</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSerCx2PioReceiveCancelReadyNotification</i> callback function that is named <code>MyPioReceiveCancelReadyNotification</code>, use the <b>EVT_SERCX2_PIO_RECEIVE_CANCEL_READY_NOTIFICATION</b> function type, as shown in this code example:

<div class="code"><span codelanguage="cpp"><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SERCX2_PIO_RECEIVE_CANCEL_READY_NOTIFICATION  MyPioReceiveCancelReadyNotification;</pre>
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
BOOLEAN
  MyPioReceiveCancelReadyNotification(
    SERCX2PIORECEIVE  PioReceive
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_SERCX2_PIO_RECEIVE_CANCEL_READY_NOTIFICATION</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_PIO_RECEIVE_CANCEL_READY_NOTIFICATION</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_receive_enable_ready_notification">EvtSerCx2PioReceiveEnableReadyNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIORECEIVE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2pioreceivecreate">SerCx2PioReceiveCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2pioreceiveready">SerCx2PioReceiveReady</a>

