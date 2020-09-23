---
UID: NF:sercx.SerCx2SaveReceiveFifoOnD0Exit
title: SerCx2SaveReceiveFifoOnD0Exit function (sercx.h)
description: The SerCx2SaveReceiveFifoOnD0Exit method informs version 2 of the serial framework extension (SerCx2) that the receive FIFO of the serial controller hardware contains data that should be saved before the serial controller enters a device low-power state.
old-location: serports\sercx2savereceivefifoond0exit.htm
tech.root: serports
ms.assetid: 689306DE-F83A-4C5D-B79A-DEBF2D5E79B3
ms.date: 04/23/2018
keywords: ["SerCx2SaveReceiveFifoOnD0Exit function"]
ms.keywords: 2/SerCx2SaveReceiveFifoOnD0Exit, SerCx2SaveReceiveFifoOnD0Exit, SerCx2SaveReceiveFifoOnD0Exit method [Serial Ports], serports.sercx2savereceivefifoond0exit
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
targetos: Windows
req.typenames: 
f1_keywords:
 - SerCx2SaveReceiveFifoOnD0Exit
 - sercx/SerCx2SaveReceiveFifoOnD0Exit
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - 2.0\Sercx.h
api_name:
 - SerCx2SaveReceiveFifoOnD0Exit
---

# SerCx2SaveReceiveFifoOnD0Exit function


## -description

The <b>SerCx2SaveReceiveFifoOnD0Exit</b> method informs version 2 of the serial framework extension (SerCx2) that the receive FIFO of the serial controller hardware contains data that should be saved before the serial controller enters a device low-power state.

## -parameters

### -param PioReceive 

[in]
A <a href="/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIORECEIVE</a> handle to a PIO-receive object. The serial controller driver previously called the <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2pioreceivecreate">SerCx2PioReceiveCreate</a> method to create this object.

### -param FifoSize 

[in]
The number of bytes of unread data that the transmit FIFO contains.

## -remarks

When the serial controller is about to enter a low-power state, SerCx2 and the serial controller driver must save any bytes of unread data that might remain in the receive FIFO. Otherwise, this data will be lost when the serial controller enters the low-power state. To request assistance from SerCx2 to save this data, the driver calls <b>SerCx2SaveReceiveFifoOnD0Exit</b>.

The driver framework calls the driver's <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_exit">EvtDeviceD0Exit</a> or <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_exit_pre_interrupts_disabled">EvtDeviceD0ExitPreInterruptsDisabled</a> event callback function to tell the driver to prepare the serial controller to exit the D0 device state. In response, this function first deasserts the <i>ready to send</i> (RTS) line to tell the device on the other end of the serial connection to not send any more data. Next, the function calls <b>SerCx2SaveReceiveFifoOnD0Exit</b>.

<b>SerCx2SaveReceiveFifoOnD0Exit</b> calls the driver's <a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_receive_read_buffer">EvtSerCx2PioReceiveReadBuffer</a> event callback function to retrieve the data from the receive FIFO. In this call, SerCx2 supplies, as a parameter, a pointer to an internal software buffer that SerCx2 maintains for the purpose of saving unread data from the receive FIFO in preparation to enter a low-power state.

Later, after a client sends a read (<a href="/windows-hardware/drivers/ifs/irp-mj-read">IRP_MJ_READ</a>) request to the serial controller, SerCx2 copies the bytes from this internal software buffer to the read buffer in the request.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_exit">EvtDeviceD0Exit</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_exit_pre_interrupts_disabled">EvtDeviceD0ExitPreInterruptsDisabled</a>



<a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_receive_read_buffer">EvtSerCx2PioReceiveReadBuffer</a>



<a href="/windows-hardware/drivers/ifs/irp-mj-read">IRP_MJ_READ</a>



<a href="/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIORECEIVE</a>



<a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2pioreceivecreate">SerCx2PioReceiveCreate</a>