---
UID: NC:sercx.EVT_SERCX2_PIO_RECEIVE_ENABLE_READY_NOTIFICATION
title: EVT_SERCX2_PIO_RECEIVE_ENABLE_READY_NOTIFICATION (sercx.h)
description: The EvtSerCx2PioReceiveEnableReadyNotification event callback function is called by version 2 of the serial framework extension (SerCx2) to enable the serial controller driver to notify SerCx2 when the serial controller receives new data.
old-location: serports\evtsercx2pioreceiveenablereadynotification.htm
tech.root: serports
ms.date: 04/23/2018
keywords: ["EVT_SERCX2_PIO_RECEIVE_ENABLE_READY_NOTIFICATION callback function"]
ms.keywords: 2/EvtSerCx2PioReceiveEnableReadyNotification, EVT_SERCX2_PIO_RECEIVE_ENABLE_READY_NOTIFICATION, EVT_SERCX2_PIO_RECEIVE_ENABLE_READY_NOTIFICATION callback, EvtSerCx2PioReceiveEnableReadyNotification, EvtSerCx2PioReceiveEnableReadyNotification callback function [Serial Ports], serports.evtsercx2pioreceiveenablereadynotification
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
 - EVT_SERCX2_PIO_RECEIVE_ENABLE_READY_NOTIFICATION
 - sercx/EVT_SERCX2_PIO_RECEIVE_ENABLE_READY_NOTIFICATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - 2.0\Sercx.h
api_name:
 - EVT_SERCX2_PIO_RECEIVE_ENABLE_READY_NOTIFICATION
---

# EVT_SERCX2_PIO_RECEIVE_ENABLE_READY_NOTIFICATION callback function


## -description

The <i>EvtSerCx2PioReceiveEnableReadyNotification</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to enable the serial controller driver to notify SerCx2 when the serial controller receives new data.

## -parameters

### -param PioReceive [in]


A <a href="/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIORECEIVE</a> handle to a PIO-receive object. The serial controller driver previously called the <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2pioreceivecreate">SerCx2PioReceiveCreate</a> method to create this object.

## -remarks

Your serial controller driver must implement this function. The driver registers the function in the <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2pioreceivecreate">SerCx2PioReceiveCreate</a> call that creates the PIO-receive object.

After the <i>EvtSerCx2PioReceiveEnableReadyNotification</i> function is called to enable a ready notification for a PIO-receive transaction, the serial controller driver must call the <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2pioreceiveready">SerCx2PioReceiveReady</a> method to notify SerCx2 when the driver detects that one or more bytes of data are available to be read from the receive FIFO in the serial controller hardware. If data is already available in the receive FIFO when the ready notification is enabled, the driver immediately calls this method to notify SerCx2.

The ready notification for a PIO-receive transaction is a one-shot notification. After sending a ready notification to SerCx2, the serial controller driver sends no further notifications until SerCx2 calls the <i>EvtSerCx2PioReceiveEnableReadyNotification</i> function to enable another notification.

An <a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_receive_read_buffer">EvtSerCx2PioReceiveReadBuffer</a> event callback function call might only partially complete a PIO-receive transaction because no more data is immediately available to be read from the receive FIFO. In this case, SerCx2 calls the <i>EvtSerCx2PioReceiveEnableReadyNotification</i> function to enable a ready notification, in which case the serial controller driver must notify SerCx2 when the receive FIFO contains more data. In response to this notification, SerCx2 resumes the partially completed receive transaction by calling the <i>EvtSerCx2PioReceiveReadBuffer</i> function again.

Typically, an <i>EvtSerCx2PioReceiveEnableReadyNotification</i> function enables an interrupt that occurs when the serial controller has more data available to be read.  In response to this interrupt, the serial controller driver calls <b>SerCx2PioReceiveReady</b>.

No more than one ready notification can be pending at a time. After SerCx2 calls the <i>EvtSerCx2PioReceiveEnableReadyNotification</i> function to enable a ready notification, SerCx2 does not call this function again until the controller driver calls <b>SerCx2PioReceiveReady</b>.

SerCx2 never calls the <i>EvtSerCx2PioReceiveReadBuffer</i> function when the ready notification is enabled.

A pending ready notification can be canceled if the associated read request times out or is canceled. To cancel a ready notification for a PIO-receive transaction, SerCx2 calls the <a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_receive_cancel_ready_notification">EvtSerCx2PioReceiveCancelReadyNotification</a> event callback function.

SerCx2 uses ready notifications to efficiently manage interval time-outs that occur during the handling of read requests that are processed as PIO-receive transactions.

For more information, see <a href="/previous-versions/dn265332(v=vs.85)">SerCx2 PIO-Receive Transactions</a>.


#### Examples

To define an <i>EvtSerCx2PioReceiveEnableReadyNotification</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSerCx2PioReceiveEnableReadyNotification</i> callback function that is named <code>MyPioReceiveEnableReadyNotification</code>, use the <b>EVT_SERCX2_PIO_RECEIVE_ENABLE_READY_NOTIFICATION</b> function type, as shown in this code example:


```cpp
EVT_SERCX2_PIO_RECEIVE_ENABLE_READY_NOTIFICATION  MyPioReceiveEnableReadyNotification;
```

Then, implement your callback function as follows:


```cpp
_Use_decl_annotations_
VOID
  MyPioReceiveEnableReadyNotification(
    SERCX2PIORECEIVE  PioReceive
    )
  {...}
```

The <b>EVT_SERCX2_PIO_RECEIVE_ENABLE_READY_NOTIFICATION</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_PIO_RECEIVE_ENABLE_READY_NOTIFICATION</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_receive_cancel_ready_notification">EvtSerCx2PioReceiveCancelReadyNotification</a>



<a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_receive_cleanup_transaction">EvtSerCx2PioReceiveCleanupTransaction</a>



<a href="/windows-hardware/drivers/ifs/irp-mj-read">IRP_MJ_READ</a>



<a href="/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIORECEIVE</a>



<a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2pioreceivecreate">SerCx2PioReceiveCreate</a>



<a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2pioreceiveready">SerCx2PioReceiveReady</a>

