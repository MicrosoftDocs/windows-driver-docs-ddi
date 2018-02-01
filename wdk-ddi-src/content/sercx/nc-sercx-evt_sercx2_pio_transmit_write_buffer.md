---
UID: NC:sercx.EVT_SERCX2_PIO_TRANSMIT_WRITE_BUFFER
title: EVT_SERCX2_PIO_TRANSMIT_WRITE_BUFFER
author: windows-driver-content
description: The EvtSerCx2PioTransmitWriteBuffer event callback function is called by version 2 of the serial framework extension (SerCx2) to use programmed I/O (PIO) to transfer the contents of a write buffer to the transmit FIFO in the serial controller.
old-location: serports\evtsercx2piotransmitwritebuffer.htm
old-project: serports
ms.assetid: 28DD175B-9869-4CFC-9BDD-172DA7E015DE
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: serports.evtsercx2piotransmitwritebuffer, EvtSerCx2PioTransmitWriteBuffer callback function [Serial Ports], EvtSerCx2PioTransmitWriteBuffer, EVT_SERCX2_PIO_TRANSMIT_WRITE_BUFFER, EVT_SERCX2_PIO_TRANSMIT_WRITE_BUFFER, 2/EvtSerCx2PioTransmitWriteBuffer
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
-	EvtSerCx2PioTransmitWriteBuffer
product: Windows
targetos: Windows
req.typenames: SENSOR_VALUE_PAIR, *PSENSOR_VALUE_PAIR
req.product: Windows 10 or later.
---

# EVT_SERCX2_PIO_TRANSMIT_WRITE_BUFFER callback


## -description


The <i>EvtSerCx2PioTransmitWriteBuffer</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to use programmed I/O (PIO) to transfer the contents of a write buffer to the transmit FIFO in the serial controller.


## -prototype


````
EVT_SERCX2_PIO_TRANSMIT_WRITE_BUFFER EvtSerCx2PioTransmitWriteBuffer;

ULONG EvtSerCx2PioTransmitWriteBuffer(
  _In_ SERCX2PIOTRANSMIT PioTransmit,
  _In_ PUCHAR            Buffer,
  _In_ ULONG             Length
)
{ ... }
````


## -parameters




### -param PioTransmit [in]

A <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a> handle to a PIO-transmit object. The serial controller driver previously called the <a href="..\sercx\nf-sercx-sercx2piotransmitcreate.md">SerCx2PioTransmitCreate</a> method to create this object.


### -param Buffer [in]

A pointer to the write buffer. This parameter is the virtual address of a locked-down buffer in system memory.


### -param Length [in]

The number of bytes in the write buffer that are available to be transmitted.


## -returns


The <i>EvtSerCx2PioTransmitWriteBuffer</i> function returns the number of bytes of data it successfully transferred from the write buffer to the transmit FIFO in the serial controller hardware.



## -remarks


Your serial controller driver must implement this function. The driver registers the function in the <a href="..\sercx\nf-sercx-sercx2piotransmitcreate.md">SerCx2PioTransmitCreate</a> call that creates the PIO-transmit object.

SerCx2 might call the <i>EvtSerCx2PioTransmitWriteBuffer</i> function more than once during a PIO-transmit transaction. A single <i>EvtSerCx2PioTransmitWriteBuffer</i> call is sufficient if this call can transfer the full contents of the write buffer to the transmit FIFO. Otherwise, SerCx2 continues to call this function, as more space becomes available in the transmit FIFO, until the write buffer is emptied.

Starting with the first byte in the write buffer, the <i>EvtSerCx2PioTransmitWriteBuffer</i> function uses PIO to transfer as many bytes as it can from the buffer to the transmit FIFO. The function continues to transfer data from the buffer for as long as the buffer is not empty and the <i>line status register</i> (LSR) indicates that the FIFO can accept more data. If the LSR indicates that the FIFO can accept no more data, the function returns without emptying the buffer. Otherwise, the function transfers all the bytes in the buffer and returns. In either case, the value returned by this function is the number of bytes of data that were successfully transferred from the write buffer to the transmit FIFO.

Typically, the <i>EvtSerCx2PioTransmitWriteBuffer</i> function does not enable any interrupts. Instead, if the function is unable to transfer the entire contents of the write buffer to the transmit FIFO, SerCx2 calls the <a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_enable_ready_notification.md">EvtSerCx2PioTransmitEnableReadyNotification</a> event callback function to enable a ready notification, and this function enables an interrupt that occurs when the transmit FIFO becomes empty.

For each successive call to the <i>EvtSerCx2PioTransmitWriteBuffer</i> function, SerCx2 adjusts <i>Buffer</i> to point to the remaining data in the buffer, and sets <i>Length</i> to the number of data bytes that remain in the buffer.

The ready notification is never enabled when SerCx2 calls the <i>EvtSerCx2PioTransmitEnableReadyNotification</i> function. However, SerCx2 might call this function from the same thread from which the driver called the <a href="..\sercx\nf-sercx-sercx2piotransmitready.md">SerCx2PioTransmitReady</a> method.

If the driver implements an <a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_initialize_transaction.md">EvtSerCx2PioTransmitInitializeTransaction</a> function, SerCx2 calls this function at the start of a PIO-transmit transaction, before the first call to the <i>EvtSerCx2PioTransmitWriteBuffer</i> function. If the driver implements an <a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_cleanup_transaction.md">EvtSerCx2PioTransmitCleanupTransaction</a> function, SerCx2 calls this function at the end of a PIO-transmit transaction, after the last <i>EvtSerCx2PioTransmitWriteBuffer</i> call, and after any calls to the <a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_drain_fifo.md">EvtSerCx2PioTransmitDrainFifo</a>, <a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_cancel_drain_fifo.md">EvtSerCx2PioTransmitCancelDrainFifo</a>, and <a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_purge_fifo.md">EvtSerCx2PioTransmitPurgeFifo</a> functions, if they are implemented.

For more information about PIO-transmit transactions, see <a href="https://msdn.microsoft.com/3BEF9A3D-1FEF-4626-B07F-1670359062AF">SerCx2 PIO-Transmit Transactions</a>.



## -see-also

<a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_cancel_drain_fifo.md">EvtSerCx2PioTransmitCancelDrainFifo</a>

<a href="..\sercx\nf-sercx-sercx2piotransmitcreate.md">SerCx2PioTransmitCreate</a>

<a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_drain_fifo.md">EvtSerCx2PioTransmitDrainFifo</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a>

<a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_enable_ready_notification.md">EvtSerCx2PioTransmitEnableReadyNotification</a>

<a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_purge_fifo.md">EvtSerCx2PioTransmitPurgeFifo</a>

<a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_initialize_transaction.md">EvtSerCx2PioTransmitInitializeTransaction</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX2_PIO_TRANSMIT_WRITE_BUFFER callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

