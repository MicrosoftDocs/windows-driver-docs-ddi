---
UID: NS:sercx._SERCX2_PIO_RECEIVE_CONFIG
title: _SERCX2_PIO_RECEIVE_CONFIG (sercx.h)
description: The SERCX2_PIO_RECEIVE_CONFIG structure contains information that version 2 of the serial framework extension (SerCx2) uses to configure a new PIO-receive object.
old-location: serports\sercx2_pio_receive_config.htm
tech.root: serports
ms.assetid: D95B1E7F-1966-4130-A410-3975B0438608
ms.date: 04/23/2018
keywords: ["SERCX2_PIO_RECEIVE_CONFIG structure"]
ms.keywords: "*PSERCX2_PIO_RECEIVE_CONFIG, 2/PSERCX2_PIO_RECEIVE_CONFIG, 2/SERCX2_PIO_RECEIVE_CONFIG, PSERCX2_PIO_RECEIVE_CONFIG, PSERCX2_PIO_RECEIVE_CONFIG structure pointer [Serial Ports], SERCX2_PIO_RECEIVE_CONFIG, SERCX2_PIO_RECEIVE_CONFIG structure [Serial Ports], _SERCX2_PIO_RECEIVE_CONFIG, serports.sercx2_pio_receive_config"
f1_keywords:
 - "sercx/SERCX2_PIO_RECEIVE_CONFIG"
 - "SERCX2_PIO_RECEIVE_CONFIG"
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
- SERCX2_PIO_RECEIVE_CONFIG
targetos: Windows
req.typenames: SERCX2_PIO_RECEIVE_CONFIG, *PSERCX2_PIO_RECEIVE_CONFIG
---

# _SERCX2_PIO_RECEIVE_CONFIG structure


## -description


The <b>SERCX2_PIO_RECEIVE_CONFIG</b> structure contains information that version 2 of the serial framework extension (SerCx2) uses to configure a new PIO-receive object.


## -struct-fields




### -field Size

The size, in bytes, of this structure. The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2pioreceivecreate">SerCx2PioReceiveCreate</a> method uses this member to determine which version of the structure the caller is using. The size of this structure might change in future versions of the Sercx.h header file.


### -field EvtSerCx2PioReceiveInitializeTransaction

A pointer to the driver-implemented <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_receive_initialize_transaction">EvtSerCx2PioReceiveInitializeTransaction</a> event callback function. This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function.


### -field EvtSerCx2PioReceiveCleanupTransaction

A pointer to the driver-implemented <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_receive_cleanup_transaction">EvtSerCx2PioReceiveCleanupTransaction</a> event callback function. This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function.


### -field EvtSerCx2PioReceiveReadBuffer

A pointer to the driver-implemented <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_receive_read_buffer">EvtSerCx2PioReceiveReadBuffer</a> event callback function. This member must point to a valid function.


### -field EvtSerCx2PioReceiveEnableReadyNotification

A pointer to the driver-implemented <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_receive_enable_ready_notification">EvtSerCx2PioReceiveEnableReadyNotification</a> event callback function. This member must point to a valid function.


### -field EvtSerCx2PioReceiveCancelReadyNotification

A pointer to the driver-implemented <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_receive_cancel_ready_notification">EvtSerCx2PioReceiveCancelReadyNotification</a> event callback function. This member must point to a valid function.


## -remarks



The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2pioreceivecreate">SerCx2PioReceiveCreate</a> method accepts a pointer to a <b>SERCX2_PIO_RECEIVE_CONFIG</b> structure as an input parameter. Before calling <b>SerCx2PioReceiveCreate</b>, call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2_pio_receive_config_init">SERCX2_PIO_RECEIVE_CONFIG_INIT</a> function to initialize this structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_receive_cancel_ready_notification">EvtSerCx2PioReceiveCancelReadyNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_receive_cleanup_transaction">EvtSerCx2PioReceiveCleanupTransaction</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_receive_enable_ready_notification">EvtSerCx2PioReceiveEnableReadyNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_receive_initialize_transaction">EvtSerCx2PioReceiveInitializeTransaction</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_receive_read_buffer">EvtSerCx2PioReceiveReadBuffer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2_pio_receive_config_init">SERCX2_PIO_RECEIVE_CONFIG_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2pioreceivecreate">SerCx2PioReceiveCreate</a>
 

 

