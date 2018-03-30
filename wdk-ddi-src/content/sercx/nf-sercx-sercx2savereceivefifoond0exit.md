---
UID: NF:sercx.SerCx2SaveReceiveFifoOnD0Exit
title: SerCx2SaveReceiveFifoOnD0Exit function
author: windows-driver-content
description: The SerCx2SaveReceiveFifoOnD0Exit method informs version 2 of the serial framework extension (SerCx2) that the receive FIFO of the serial controller hardware contains data that should be saved before the serial controller enters a device low-power state.
old-location: serports\sercx2savereceivefifoond0exit.htm
old-project: serports
ms.assetid: 689306DE-F83A-4C5D-B79A-DEBF2D5E79B3
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: 2/SerCx2SaveReceiveFifoOnD0Exit, SerCx2SaveReceiveFifoOnD0Exit, SerCx2SaveReceiveFifoOnD0Exit method [Serial Ports], serports.sercx2savereceivefifoond0exit
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sercx.h
req.include-header: 
req.target-type: Universal
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	2.0\Sercx.h
api_name:
-	SerCx2SaveReceiveFifoOnD0Exit
product: Windows
targetos: Windows
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---

# SerCx2SaveReceiveFifoOnD0Exit function


## -description


The <b>SerCx2SaveReceiveFifoOnD0Exit</b> method informs version 2 of the serial framework extension (SerCx2) that the receive FIFO of the serial controller hardware contains data that should be saved before the serial controller enters a device low-power state.


## -parameters




### -param PioReceive [in]

A <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIORECEIVE</a> handle to a PIO-receive object. The serial controller driver previously called the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265264">SerCx2PioReceiveCreate</a> method to create this object.


### -param FifoSize [in]

The number of bytes of unread data that the transmit FIFO contains.


## -returns



None.




## -remarks



When the serial controller is about to enter a low-power state, SerCx2 and the serial controller driver must save any bytes of unread data that might remain in the receive FIFO. Otherwise, this data will be lost when the serial controller enters the low-power state. To request assistance from SerCx2 to save this data, the driver calls <b>SerCx2SaveReceiveFifoOnD0Exit</b>.

The driver framework calls the driver's <a href="https://msdn.microsoft.com/bc3af732-f9ab-43a4-bc6f-7fa0b4c05a66">EvtDeviceD0Exit</a> or <a href="https://msdn.microsoft.com/8f57c3b3-2dcf-44a3-a3c2-c9585bdfa253">EvtDeviceD0ExitPreInterruptsDisabled</a> event callback function to tell the driver to prepare the serial controller to exit the D0 device state. In response, this function first deasserts the <i>ready to send</i> (RTS) line to tell the device on the other end of the serial connection to not send any more data. Next, the function calls <b>SerCx2SaveReceiveFifoOnD0Exit</b>.

<b>SerCx2SaveReceiveFifoOnD0Exit</b> calls the driver's <a href="https://msdn.microsoft.com/B69A128A-B1B0-47BC-9783-32780FC9C447">EvtSerCx2PioReceiveReadBuffer</a> event callback function to retrieve the data from the receive FIFO. In this call, SerCx2 supplies, as a parameter, a pointer to an internal software buffer that SerCx2 maintains for the purpose of saving unread data from the receive FIFO in preparation to enter a low-power state.

Later, after a client sends a read (<a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a>) request to the serial controller, SerCx2 copies the bytes from this internal software buffer to the read buffer in the request.




## -see-also




<a href="https://msdn.microsoft.com/bc3af732-f9ab-43a4-bc6f-7fa0b4c05a66">EvtDeviceD0Exit</a>



<a href="https://msdn.microsoft.com/8f57c3b3-2dcf-44a3-a3c2-c9585bdfa253">EvtDeviceD0ExitPreInterruptsDisabled</a>



<a href="https://msdn.microsoft.com/B69A128A-B1B0-47BC-9783-32780FC9C447">EvtSerCx2PioReceiveReadBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIORECEIVE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265264">SerCx2PioReceiveCreate</a>
 

 

