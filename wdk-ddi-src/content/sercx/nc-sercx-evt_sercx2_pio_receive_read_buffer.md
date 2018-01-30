---
UID: NC:sercx.EVT_SERCX2_PIO_RECEIVE_READ_BUFFER
title: EVT_SERCX2_PIO_RECEIVE_READ_BUFFER
author: windows-driver-content
description: The EvtSerCx2PioReceiveReadBuffer event callback function is called by version 2 of the serial framework extension (SerCx2) to use programmed I/O (PIO) to transfer data from the receive FIFO in the serial controller to a read buffer.
old-location: serports\evtsercx2pioreceivereadbuffer.htm
old-project: Benchmark
ms.assetid: B69A128A-B1B0-47BC-9783-32780FC9C447
ms.author: windowsdriverdev
ms.date: 1/12/2018
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
req.typenames: "*PSDP_TREE_ROOT_NODE, SDP_TREE_ROOT_NODE"
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

A <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIORECEIVE</a> handle to a PIO-receive object. The serial controller driver previously called the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265264">SerCx2PioReceiveCreate</a> method to create this object.


### -param Buffer [out]

A pointer to the read buffer. This parameter is the virtual address of a locked-down buffer in system memory.


### -param Length [in]

The number of bytes in the read buffer that are available to store received data.


## -returns


The <i>EvtSerCx2PioReceiveReadBuffer</i> function returns the number of bytes of data that it successfully transferred from the receive FIFO in the serial controller hardware to the read buffer.



## -remarks


Your serial controller driver must implement this function. The driver registers the function in the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265264">SerCx2PioReceiveCreate</a> call that creates the PIO-receive object.

SerCx2 might call the <i>EvtSerCx2PioReceiveReadBuffer</i> function more than once during a PIO-receive transaction. A single <i>EvtSerCx2PioReceiveReadBuffer</i> call is sufficient if this call can fill the read buffer with data from the receive FIFO. Otherwise, SerCx2 continues to call this function, as more data becomes available in the receive FIFO, until the read buffer is filled.

The <i>EvtSerCx2PioReceiveReadBuffer</i> function uses PIO to transfer as many bytes as it can from the receive FIFO to the read buffer. The function continues to transfer data from the FIFO for as long as the buffer passed to this function is not full and the line status register (LSR) indicates that more data is available from the FIFO. If the LSR indicates that the FIFO is empty, the function returns without filling the buffer. Otherwise, the function fills the buffer and returns. In either case, the value returned by this function is the number of bytes of data that were successfully transferred to the read buffer from the receive FIFO.

Typically, the <i>EvtSerCx2PioReceiveReadBuffer</i> function does not enable any interrupts. Instead, if the receive FIFO runs out of data before the function can fill the read buffer, SerCx2 calls the <a href="https://msdn.microsoft.com/DDD17DF3-9457-40D1-BE18-0A1CAED1389B">EvtSerCx2PioReceiveEnableReadyNotification</a> event callback function to enable a ready notification, and this function enables an interrupt that occurs when more data is available in the receive FIFO.

For each successive call to the <i>EvtSerCx2PioReceiveReadBuffer</i> function, SerCx2 adjusts <i>Buffer</i> to point to the next buffer region to be filled, and sets <i>Length</i> to the number of bytes of unfilled space that remain in the buffer.

The ready notification is never enabled when SerCx2 calls the <i>EvtSerCx2PioReceiveEnableReadyNotification</i> function. However, SerCx2 might call this function from the same thread from which the driver called the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265266">SerCx2PioReceiveReady</a> method.

If the driver implements an <a href="https://msdn.microsoft.com/E03B5319-BBBE-4396-8D03-8BC82FB97D15">EvtSerCx2PioReceiveInitializeTransaction</a> function, SerCx2 calls this function at the start of a PIO-transmit transaction, before the first call to the <i>EvtSerCx2PioReceiveReadBuffer</i> function. If the driver implements an <a href="https://msdn.microsoft.com/2CFCF5D9-23F8-4571-972A-0BE48EB2D046">EvtSerCx2PioReceiveCleanupTransaction</a> function, SerCx2 calls this function at the end of a PIO-receive transaction, after the final call to the <i>EvtSerCx2PioReceiveReadBuffer</i> function.

In addition to calling the <i>EvtSerCx2PioReceiveReadBuffer</i> function during PIO-receive transactions, SerCx2 calls this function to save the state of the receive FIFO just before the serial controller exits the D0 device power state. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265276">SerCx2SaveReceiveFifoOnD0Exit</a>.

For more information about PIO-receive transactions, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265332">SerCx2 PIO-Receive Transactions</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn265264">SerCx2PioReceiveCreate</a>

<a href="https://msdn.microsoft.com/DDD17DF3-9457-40D1-BE18-0A1CAED1389B">EvtSerCx2PioReceiveEnableReadyNotification</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIORECEIVE</a>

<a href="https://msdn.microsoft.com/2CFCF5D9-23F8-4571-972A-0BE48EB2D046">EvtSerCx2PioReceiveCleanupTransaction</a>

<a href="https://msdn.microsoft.com/E03B5319-BBBE-4396-8D03-8BC82FB97D15">EvtSerCx2PioReceiveInitializeTransaction</a>

 

 

