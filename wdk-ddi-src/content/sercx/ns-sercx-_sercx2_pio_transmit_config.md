---
UID: NS:sercx._SERCX2_PIO_TRANSMIT_CONFIG
title: _SERCX2_PIO_TRANSMIT_CONFIG (sercx.h)
description: The SERCX2_PIO_TRANSMIT_CONFIG structure contains information that version 2 of the serial framework extension (SerCx2) uses to configure a new PIO-transmit object.
old-location: serports\sercx2_pio_transmit_config.htm
tech.root: serports
ms.assetid: E2C1705D-4E5E-4FB5-9889-24503ADB9A3C
ms.date: 04/23/2018
keywords: ["_SERCX2_PIO_TRANSMIT_CONFIG structure"]
ms.keywords: "*PSERCX2_PIO_TRANSMIT_CONFIG, 2/PSERCX2_PIO_TRANSMIT_CONFIG, 2/SERCX2_PIO_TRANSMIT_CONFIG, PSERCX2_PIO_TRANSMIT_CONFIG, PSERCX2_PIO_TRANSMIT_CONFIG structure pointer [Serial Ports], SERCX2_PIO_TRANSMIT_CONFIG, SERCX2_PIO_TRANSMIT_CONFIG structure [Serial Ports], _SERCX2_PIO_TRANSMIT_CONFIG, serports.sercx2_pio_transmit_config"
f1_keywords:
 - "sercx/SERCX2_PIO_TRANSMIT_CONFIG"
 - "SERCX2_PIO_TRANSMIT_CONFIG"
req.header: sercx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.1.
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- 2.0\Sercx.h
api_name:
- SERCX2_PIO_TRANSMIT_CONFIG
targetos: Windows
req.typenames: SERCX2_PIO_TRANSMIT_CONFIG, *PSERCX2_PIO_TRANSMIT_CONFIG
---

# _SERCX2_PIO_TRANSMIT_CONFIG structure


## -description


The <b>SERCX2_PIO_TRANSMIT_CONFIG</b> structure contains information that version 2 of the serial framework extension (SerCx2) uses to configure a new PIO-transmit object.


## -struct-fields




### -field Size

The size, in bytes, of this structure. The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2piotransmitcreate">SerCx2PioTransmitCreate</a> method uses this member to determine which version of the structure the caller is using. The size of this structure might change in future versions of the Sercx.h header file.


### -field EvtSerCx2PioTransmitInitializeTransaction

A pointer to the driver-implemented <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_transmit_initialize_transaction">EvtSerCx2PioTransmitInitializeTransaction</a> event callback function. This member must point to a valid function.


### -field EvtSerCx2PioTransmitCleanupTransaction

A pointer to the driver-implemented <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_transmit_cleanup_transaction">EvtSerCx2PioTransmitCleanupTransaction</a> event callback function. This member must point to a valid function.


### -field EvtSerCx2PioTransmitWriteBuffer

A pointer to the driver-implemented <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_transmit_write_buffer">EvtSerCx2PioTransmitWriteBuffer</a> event callback function. This member must point to a valid function.


### -field EvtSerCx2PioTransmitEnableReadyNotification

A pointer to the driver-implemented <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_transmit_enable_ready_notification">EvtSerCx2PioTransmitEnableReadyNotification</a> event callback function. This member must point to a valid function.


### -field EvtSerCx2PioTransmitCancelReadyNotification

A pointer to the driver-implemented <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_transmit_cancel_ready_notification">EvtSerCx2PioTransmitCancelReadyNotification</a> event callback function. This member must point to a valid function.


### -field EvtSerCx2PioTransmitDrainFifo

A pointer to the driver-implemented <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_transmit_drain_fifo">EvtSerCx2PioTransmitDrainFifo</a> event callback function. This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function. However, a driver that implements this function must also implement <i>EvtSerCx2PioTransmitCancelDrainFifo</i> and <i>EvtSerCx2PioTransmitPurgeFifo</i> functions.


### -field EvtSerCx2PioTransmitCancelDrainFifo

A pointer to the driver-implemented <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_transmit_cancel_drain_fifo">EvtSerCx2PioTransmitCancelDrainFifo</a> event callback function. This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function. However, a driver that implements this function must also implement <i>EvtSerCx2PioTransmitDrainFifo</i> and <i>EvtSerCx2PioTransmitPurgeFifo</i> functions.


### -field EvtSerCx2PioTransmitPurgeFifo

A pointer to the driver-implemented <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_transmit_purge_fifo">EvtSerCx2PioTransmitPurgeFifo</a> event callback function. This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function. However, a driver that implements this function must also implement <i>EvtSerCx2PioTransmitDrainFifo</i> and <i>EvtSerCx2PioTransmitCancelDrainFifo</i> functions.


## -remarks



The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2piotransmitcreate">SerCx2PioTransmitCreate</a> method accepts a pointer to a <b>SERCX2_PIO_TRANSMIT_CONFIG</b> structure as an input parameter. Before calling <b>SerCx2PioTransmitCreate</b>, call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2_pio_transmit_config_init">SERCX2_PIO_TRANSMIT_CONFIG_INIT</a> function to initialize this structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_transmit_cancel_drain_fifo">EvtSerCx2PioTransmitCancelDrainFifo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_transmit_cancel_ready_notification">EvtSerCx2PioTransmitCancelReadyNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_transmit_cleanup_transaction">EvtSerCx2PioTransmitCleanupTransaction</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_transmit_drain_fifo">EvtSerCx2PioTransmitDrainFifo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_transmit_enable_ready_notification">EvtSerCx2PioTransmitEnableReadyNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_transmit_initialize_transaction">EvtSerCx2PioTransmitInitializeTransaction</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_transmit_purge_fifo">EvtSerCx2PioTransmitPurgeFifo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_transmit_write_buffer">EvtSerCx2PioTransmitWriteBuffer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2_pio_transmit_config_init">SERCX2_PIO_TRANSMIT_CONFIG_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2piotransmitcreate">SerCx2PioTransmitCreate</a>
 

 

