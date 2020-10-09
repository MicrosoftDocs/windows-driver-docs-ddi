---
UID: NC:sercx.EVT_SERCX2_PIO_RECEIVE_READ_BUFFER
title: EVT_SERCX2_PIO_RECEIVE_READ_BUFFER (sercx.h)
description: The EvtSerCx2PioReceiveReadBuffer event callback function is called by version 2 of the serial framework extension (SerCx2) to use programmed I/O (PIO) to transfer data from the receive FIFO in the serial controller to a read buffer.
old-location: serports\evtsercx2pioreceivereadbuffer.htm
tech.root: serports
ms.assetid: B69A128A-B1B0-47BC-9783-32780FC9C447
ms.date: 04/23/2018
keywords: ["EVT_SERCX2_PIO_RECEIVE_READ_BUFFER callback function"]
ms.keywords: 2/EvtSerCx2PioReceiveReadBuffer, EVT_SERCX2_PIO_RECEIVE_READ_BUFFER, EVT_SERCX2_PIO_RECEIVE_READ_BUFFER callback, EvtSerCx2PioReceiveReadBuffer, EvtSerCx2PioReceiveReadBuffer callback function [Serial Ports], serports.evtsercx2pioreceivereadbuffer
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
 - EVT_SERCX2_PIO_RECEIVE_READ_BUFFER
 - sercx/EVT_SERCX2_PIO_RECEIVE_READ_BUFFER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - 2.0\Sercx.h
api_name:
 - EvtSerCx2PioReceiveReadBuffer
---

# EVT_SERCX2_PIO_RECEIVE_READ_BUFFER callback function


## -description

The <i>EvtSerCx2PioReceiveReadBuffer</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to use programmed I/O (PIO) to transfer data from the receive FIFO in the serial controller to a read buffer.

## -parameters

### -param PioReceive 

[in]
A <a href="/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIORECEIVE</a> handle to a PIO-receive object. The serial controller driver previously called the <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2pioreceivecreate">SerCx2PioReceiveCreate</a> method to create this object.

### -param Buffer 

[out]
A pointer to the read buffer. This parameter is the virtual address of a locked-down buffer in system memory.

### -param Length 

[in]
The number of bytes in the read buffer that are available to store received data.

## -returns

The <i>EvtSerCx2PioReceiveReadBuffer</i> function returns the number of bytes of data that it successfully transferred from the receive FIFO in the serial controller hardware to the read buffer.

## -remarks

Your serial controller driver must implement this function. The driver registers the function in the <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2pioreceivecreate">SerCx2PioReceiveCreate</a> call that creates the PIO-receive object.

SerCx2 might call the <i>EvtSerCx2PioReceiveReadBuffer</i> function more than once during a PIO-receive transaction. A single <i>EvtSerCx2PioReceiveReadBuffer</i> call is sufficient if this call can fill the read buffer with data from the receive FIFO. Otherwise, SerCx2 continues to call this function, as more data becomes available in the receive FIFO, until the read buffer is filled.

The <i>EvtSerCx2PioReceiveReadBuffer</i> function uses PIO to transfer as many bytes as it can from the receive FIFO to the read buffer. The function continues to transfer data from the FIFO for as long as the buffer passed to this function is not full and the line status register (LSR) indicates that more data is available from the FIFO. If the LSR indicates that the FIFO is empty, the function returns without filling the buffer. Otherwise, the function fills the buffer and returns. In either case, the value returned by this function is the number of bytes of data that were successfully transferred to the read buffer from the receive FIFO.

Typically, the <i>EvtSerCx2PioReceiveReadBuffer</i> function does not enable any interrupts. Instead, if the receive FIFO runs out of data before the function can fill the read buffer, SerCx2 calls the <a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_receive_enable_ready_notification">EvtSerCx2PioReceiveEnableReadyNotification</a> event callback function to enable a ready notification, and this function enables an interrupt that occurs when more data is available in the receive FIFO.

For each successive call to the <i>EvtSerCx2PioReceiveReadBuffer</i> function, SerCx2 adjusts <i>Buffer</i> to point to the next buffer region to be filled, and sets <i>Length</i> to the number of bytes of unfilled space that remain in the buffer.

The ready notification is never enabled when SerCx2 calls the <i>EvtSerCx2PioReceiveEnableReadyNotification</i> function. However, SerCx2 might call this function from the same thread from which the driver called the <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2pioreceiveready">SerCx2PioReceiveReady</a> method.

If the driver implements an <a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_receive_initialize_transaction">EvtSerCx2PioReceiveInitializeTransaction</a> function, SerCx2 calls this function at the start of a PIO-transmit transaction, before the first call to the <i>EvtSerCx2PioReceiveReadBuffer</i> function. If the driver implements an <a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_receive_cleanup_transaction">EvtSerCx2PioReceiveCleanupTransaction</a> function, SerCx2 calls this function at the end of a PIO-receive transaction, after the final call to the <i>EvtSerCx2PioReceiveReadBuffer</i> function.

In addition to calling the <i>EvtSerCx2PioReceiveReadBuffer</i> function during PIO-receive transactions, SerCx2 calls this function to save the state of the receive FIFO just before the serial controller exits the D0 device power state. For more information, see <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2savereceivefifoond0exit">SerCx2SaveReceiveFifoOnD0Exit</a>.

For more information about PIO-receive transactions, see <a href="/previous-versions/dn265332(v=vs.85)">SerCx2 PIO-Receive Transactions</a>.


#### Examples

To define an <i>EvtSerCx2PioReceiveReadBuffer</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSerCx2PioReceiveReadBuffer</i> callback function that is named <code>MyPioReceiveReadBuffer</code>, use the <b>EVT_SERCX2_PIO_RECEIVE_READ_BUFFER</b> function type, as shown in this code example:


```cpp
EVT_SERCX2_PIO_RECEIVE_READ_BUFFER  MyPioReceiveReadBuffer;
```

Then, implement your callback function as follows:


```cpp
_Use_decl_annotations_
ULONG
  MyPioReceiveReadBuffer(
    SERCX2PIORECEIVE  PioReceive,
    PUCHAR  Buffer,
    ULONG  Length

    )
  {...}
```

The <b>EVT_SERCX2_PIO_RECEIVE_READ_BUFFER</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_PIO_RECEIVE_READ_BUFFER</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_receive_cleanup_transaction">EvtSerCx2PioReceiveCleanupTransaction</a>



<a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_receive_enable_ready_notification">EvtSerCx2PioReceiveEnableReadyNotification</a>



<a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_receive_initialize_transaction">EvtSerCx2PioReceiveInitializeTransaction</a>



<a href="/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIORECEIVE</a>



<a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2pioreceivecreate">SerCx2PioReceiveCreate</a>