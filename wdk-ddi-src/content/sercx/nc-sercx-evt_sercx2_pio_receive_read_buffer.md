---
UID: NC:sercx.EVT_SERCX2_PIO_RECEIVE_READ_BUFFER
title: EVT_SERCX2_PIO_RECEIVE_READ_BUFFER
author: windows-driver-content
description: The EvtSerCx2PioReceiveReadBuffer event callback function is called by version 2 of the serial framework extension (SerCx2) to use programmed I/O (PIO) to transfer data from the receive FIFO in the serial controller to a read buffer.
old-location: serports\evtsercx2pioreceivereadbuffer.htm
old-project: serports
ms.assetid: B69A128A-B1B0-47BC-9783-32780FC9C447
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: serports.evtsercx2pioreceivereadbuffer, EvtSerCx2PioReceiveReadBuffer callback function [Serial Ports], EvtSerCx2PioReceiveReadBuffer, EVT_SERCX2_PIO_RECEIVE_READ_BUFFER, EVT_SERCX2_PIO_RECEIVE_READ_BUFFER, 2/EvtSerCx2PioReceiveReadBuffer
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	2.0\Sercx.h
apiname: 
-	EvtSerCx2PioReceiveReadBuffer
product: Windows
targetos: Windows
req.typenames: *PSENSOR_VALUE_PAIR, SENSOR_VALUE_PAIR
req.product: Windows 10 or later.
---

# EVT_SERCX2_PIO_RECEIVE_READ_BUFFER callback


## -description


The <i>EvtSerCx2PioReceiveReadBuffer</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to use programmed I/O (PIO) to transfer data from the receive FIFO in the serial controller to a read buffer.


## -prototype


````
EVT_SERCX2_PIO_RECEIVE_READ_BUFFER EvtSerCx2PioReceiveReadBuffer;

ULONG EvtSerCx2PioReceiveReadBuffer(
  _In_  SERCX2PIORECEIVE PioReceive,
  _Out_ PUCHAR           Buffer,
  _In_  ULONG            Length
)
{ ... }
````


## -parameters




### -param PioReceive [in]

A <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIORECEIVE</a> handle to a PIO-receive object. The serial controller driver previously called the <a href="..\sercx\nf-sercx-sercx2pioreceivecreate.md">SerCx2PioReceiveCreate</a> method to create this object.


### -param Buffer [out]

A pointer to the read buffer. This parameter is the virtual address of a locked-down buffer in system memory.


### -param Length [in]

The number of bytes in the read buffer that are available to store received data.


## -returns


The <i>EvtSerCx2PioReceiveReadBuffer</i> function returns the number of bytes of data that it successfully transferred from the receive FIFO in the serial controller hardware to the read buffer.



## -remarks


Your serial controller driver must implement this function. The driver registers the function in the <a href="..\sercx\nf-sercx-sercx2pioreceivecreate.md">SerCx2PioReceiveCreate</a> call that creates the PIO-receive object.

SerCx2 might call the <i>EvtSerCx2PioReceiveReadBuffer</i> function more than once during a PIO-receive transaction. A single <i>EvtSerCx2PioReceiveReadBuffer</i> call is sufficient if this call can fill the read buffer with data from the receive FIFO. Otherwise, SerCx2 continues to call this function, as more data becomes available in the receive FIFO, until the read buffer is filled.

The <i>EvtSerCx2PioReceiveReadBuffer</i> function uses PIO to transfer as many bytes as it can from the receive FIFO to the read buffer. The function continues to transfer data from the FIFO for as long as the buffer passed to this function is not full and the line status register (LSR) indicates that more data is available from the FIFO. If the LSR indicates that the FIFO is empty, the function returns without filling the buffer. Otherwise, the function fills the buffer and returns. In either case, the value returned by this function is the number of bytes of data that were successfully transferred to the read buffer from the receive FIFO.

Typically, the <i>EvtSerCx2PioReceiveReadBuffer</i> function does not enable any interrupts. Instead, if the receive FIFO runs out of data before the function can fill the read buffer, SerCx2 calls the <a href="..\sercx\nc-sercx-evt_sercx2_pio_receive_enable_ready_notification.md">EvtSerCx2PioReceiveEnableReadyNotification</a> event callback function to enable a ready notification, and this function enables an interrupt that occurs when more data is available in the receive FIFO.

For each successive call to the <i>EvtSerCx2PioReceiveReadBuffer</i> function, SerCx2 adjusts <i>Buffer</i> to point to the next buffer region to be filled, and sets <i>Length</i> to the number of bytes of unfilled space that remain in the buffer.

The ready notification is never enabled when SerCx2 calls the <i>EvtSerCx2PioReceiveEnableReadyNotification</i> function. However, SerCx2 might call this function from the same thread from which the driver called the <a href="..\sercx\nf-sercx-sercx2pioreceiveready.md">SerCx2PioReceiveReady</a> method.

If the driver implements an <a href="..\sercx\nc-sercx-evt_sercx2_pio_receive_initialize_transaction.md">EvtSerCx2PioReceiveInitializeTransaction</a> function, SerCx2 calls this function at the start of a PIO-transmit transaction, before the first call to the <i>EvtSerCx2PioReceiveReadBuffer</i> function. If the driver implements an <a href="..\sercx\nc-sercx-evt_sercx2_pio_receive_cleanup_transaction.md">EvtSerCx2PioReceiveCleanupTransaction</a> function, SerCx2 calls this function at the end of a PIO-receive transaction, after the final call to the <i>EvtSerCx2PioReceiveReadBuffer</i> function.

In addition to calling the <i>EvtSerCx2PioReceiveReadBuffer</i> function during PIO-receive transactions, SerCx2 calls this function to save the state of the receive FIFO just before the serial controller exits the D0 device power state. For more information, see <a href="..\sercx\nf-sercx-sercx2savereceivefifoond0exit.md">SerCx2SaveReceiveFifoOnD0Exit</a>.

For more information about PIO-receive transactions, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265332">SerCx2 PIO-Receive Transactions</a>.



## -see-also

<a href="..\sercx\nf-sercx-sercx2pioreceivecreate.md">SerCx2PioReceiveCreate</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIORECEIVE</a>

<a href="..\sercx\nc-sercx-evt_sercx2_pio_receive_enable_ready_notification.md">EvtSerCx2PioReceiveEnableReadyNotification</a>

<a href="..\sercx\nc-sercx-evt_sercx2_pio_receive_cleanup_transaction.md">EvtSerCx2PioReceiveCleanupTransaction</a>

<a href="..\sercx\nc-sercx-evt_sercx2_pio_receive_initialize_transaction.md">EvtSerCx2PioReceiveInitializeTransaction</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX2_PIO_RECEIVE_READ_BUFFER callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

