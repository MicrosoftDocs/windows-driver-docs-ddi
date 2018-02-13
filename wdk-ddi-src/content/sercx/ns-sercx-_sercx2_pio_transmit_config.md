---
UID: NS:sercx._SERCX2_PIO_TRANSMIT_CONFIG
title: "_SERCX2_PIO_TRANSMIT_CONFIG"
author: windows-driver-content
description: The SERCX2_PIO_TRANSMIT_CONFIG structure contains information that version 2 of the serial framework extension (SerCx2) uses to configure a new PIO-transmit object.
old-location: serports\sercx2_pio_transmit_config.htm
old-project: serports
ms.assetid: E2C1705D-4E5E-4FB5-9889-24503ADB9A3C
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PSERCX2_PIO_TRANSMIT_CONFIG structure pointer [Serial Ports], 2/PSERCX2_PIO_TRANSMIT_CONFIG, serports.sercx2_pio_transmit_config, PSERCX2_PIO_TRANSMIT_CONFIG, SERCX2_PIO_TRANSMIT_CONFIG, SERCX2_PIO_TRANSMIT_CONFIG structure [Serial Ports], _SERCX2_PIO_TRANSMIT_CONFIG, *PSERCX2_PIO_TRANSMIT_CONFIG, 2/SERCX2_PIO_TRANSMIT_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: Any IRQL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	2.0\Sercx.h
apiname:
-	SERCX2_PIO_TRANSMIT_CONFIG
product: Windows
targetos: Windows
req.typenames: SERCX2_PIO_TRANSMIT_CONFIG, *PSERCX2_PIO_TRANSMIT_CONFIG
req.product: Windows 10 or later.
---

# _SERCX2_PIO_TRANSMIT_CONFIG structure


## -description


The <b>SERCX2_PIO_TRANSMIT_CONFIG</b> structure contains information that version 2 of the serial framework extension (SerCx2) uses to configure a new PIO-transmit object.


## -syntax


````
typedef struct _SERCX2_PIO_TRANSMIT_CONFIG {
  ULONG                                             Size;
  PFN_SERCX2_PIO_TRANSMIT_INITIALIZE_TRANSACTION    EvtSerCx2PioTransmitInitializeTransaction;
  PFN_SERCX2_PIO_TRANSMIT_CLEANUP_TRANSACTION       EvtSerCx2PioTransmitCleanupTransaction;
  PFN_SERCX2_PIO_TRANSMIT_WRITE_BUFFER              EvtSerCx2PioTransmitWriteBuffer;
  PFN_SERCX2_PIO_TRANSMIT_ENABLE_READY_NOTIFICATION EvtSerCx2PioTransmitEnableReadyNotification;
  PFN_SERCX2_PIO_TRANSMIT_CANCEL_READY_NOTIFICATION EvtSerCx2PioTransmitCancelReadyNotification;
  PFN_SERCX2_PIO_TRANSMIT_DRAIN_FIFO                EvtSerCx2PioTransmitDrainFifo;
  PFN_SERCX2_PIO_TRANSMIT_CANCEL_DRAIN_FIFO         EvtSerCx2PioTransmitCancelDrainFifo;
  PFN_SERCX2_PIO_TRANSMIT_PURGE_FIFO                EvtSerCx2PioTransmitPurgeFifo;
} SERCX2_PIO_TRANSMIT_CONFIG, *PSERCX2_PIO_TRANSMIT_CONFIG;
````


## -struct-fields




### -field Size

The size, in bytes, of this structure. The <a href="..\sercx\nf-sercx-sercx2piotransmitcreate.md">SerCx2PioTransmitCreate</a> method uses this member to determine which version of the structure the caller is using. The size of this structure might change in future versions of the Sercx.h header file.


### -field EvtSerCx2PioTransmitInitializeTransaction

A pointer to the driver-implemented <a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_initialize_transaction.md">EvtSerCx2PioTransmitInitializeTransaction</a> event callback function. This member must point to a valid function.


### -field EvtSerCx2PioTransmitCleanupTransaction

A pointer to the driver-implemented <a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_cleanup_transaction.md">EvtSerCx2PioTransmitCleanupTransaction</a> event callback function. This member must point to a valid function.


### -field EvtSerCx2PioTransmitWriteBuffer

A pointer to the driver-implemented <a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_write_buffer.md">EvtSerCx2PioTransmitWriteBuffer</a> event callback function. This member must point to a valid function.


### -field EvtSerCx2PioTransmitEnableReadyNotification

A pointer to the driver-implemented <a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_enable_ready_notification.md">EvtSerCx2PioTransmitEnableReadyNotification</a> event callback function. This member must point to a valid function.


### -field EvtSerCx2PioTransmitCancelReadyNotification

A pointer to the driver-implemented <a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_cancel_ready_notification.md">EvtSerCx2PioTransmitCancelReadyNotification</a> event callback function. This member must point to a valid function.


### -field EvtSerCx2PioTransmitDrainFifo

A pointer to the driver-implemented <a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_drain_fifo.md">EvtSerCx2PioTransmitDrainFifo</a> event callback function. This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function. However, a driver that implements this function must also implement <i>EvtSerCx2PioTransmitCancelDrainFifo</i> and <i>EvtSerCx2PioTransmitPurgeFifo</i> functions.


### -field EvtSerCx2PioTransmitCancelDrainFifo

A pointer to the driver-implemented <a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_cancel_drain_fifo.md">EvtSerCx2PioTransmitCancelDrainFifo</a> event callback function. This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function. However, a driver that implements this function must also implement <i>EvtSerCx2PioTransmitDrainFifo</i> and <i>EvtSerCx2PioTransmitPurgeFifo</i> functions.


### -field EvtSerCx2PioTransmitPurgeFifo

A pointer to the driver-implemented <a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_purge_fifo.md">EvtSerCx2PioTransmitPurgeFifo</a> event callback function. This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function. However, a driver that implements this function must also implement <i>EvtSerCx2PioTransmitDrainFifo</i> and <i>EvtSerCx2PioTransmitCancelDrainFifo</i> functions.


## -remarks



The <a href="..\sercx\nf-sercx-sercx2piotransmitcreate.md">SerCx2PioTransmitCreate</a> method accepts a pointer to a <b>SERCX2_PIO_TRANSMIT_CONFIG</b> structure as an input parameter. Before calling <b>SerCx2PioTransmitCreate</b>, call the <a href="..\sercx\nf-sercx-sercx2_pio_transmit_config_init.md">SERCX2_PIO_TRANSMIT_CONFIG_INIT</a> function to initialize this structure.




## -see-also

<a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_cancel_ready_notification.md">EvtSerCx2PioTransmitCancelReadyNotification</a>



<a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_write_buffer.md">EvtSerCx2PioTransmitWriteBuffer</a>



<a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_initialize_transaction.md">EvtSerCx2PioTransmitInitializeTransaction</a>



<a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_purge_fifo.md">EvtSerCx2PioTransmitPurgeFifo</a>



<a href="..\sercx\nf-sercx-sercx2_pio_transmit_config_init.md">SERCX2_PIO_TRANSMIT_CONFIG_INIT</a>



<a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_cleanup_transaction.md">EvtSerCx2PioTransmitCleanupTransaction</a>



<a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_drain_fifo.md">EvtSerCx2PioTransmitDrainFifo</a>



<a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_enable_ready_notification.md">EvtSerCx2PioTransmitEnableReadyNotification</a>



<a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_cancel_drain_fifo.md">EvtSerCx2PioTransmitCancelDrainFifo</a>



<a href="..\sercx\nf-sercx-sercx2piotransmitcreate.md">SerCx2PioTransmitCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SERCX2_PIO_TRANSMIT_CONFIG structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

