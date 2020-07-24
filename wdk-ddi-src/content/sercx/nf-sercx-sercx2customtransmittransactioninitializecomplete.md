---
UID: NF:sercx.SerCx2CustomTransmitTransactionInitializeComplete
title: SerCx2CustomTransmitTransactionInitializeComplete function (sercx.h)
description: The SerCx2CustomTransmitTransactionInitializeComplete method informs version 2 of the serial framework extension (SerCx2) that the serial driver has finished initializing the serial controller and associated hardware in preparation for a new custom-transmit transaction.
old-location: serports\sercx2customtransmittransactioninitializecomplete.htm
tech.root: serports
ms.assetid: 5C2BF433-11C0-425A-B14A-7A0275F7DF51
ms.date: 04/23/2018
keywords: ["SerCx2CustomTransmitTransactionInitializeComplete function"]
ms.keywords: 2/SerCx2CustomTransmitTransactionInitializeComplete, SerCx2CustomTransmitTransactionInitializeComplete, SerCx2CustomTransmitTransactionInitializeComplete method [Serial Ports], serports.sercx2customtransmittransactioninitializecomplete
f1_keywords:
 - "sercx/SerCx2CustomTransmitTransactionInitializeComplete"
 - "SerCx2CustomTransmitTransactionInitializeComplete"
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- 2.0\Sercx.h
api_name:
- SerCx2CustomTransmitTransactionInitializeComplete
targetos: Windows
req.typenames: 
---

# SerCx2CustomTransmitTransactionInitializeComplete function


## -description


The <b>SerCx2CustomTransmitTransactionInitializeComplete</b> method informs version 2 of the serial framework extension (SerCx2) that the serial driver has finished initializing the serial controller and associated hardware in preparation for a new custom-transmit transaction.


## -parameters




### -param CustomTransmitTransaction [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2CUSTOMTRANSMITTRANSACTION</a> handle to a custom-transmit object. The serial controller driver previously called the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2customtransmittransactioncreate">SerCx2CustomTransmitTransactionCreate</a> method to create this object.


### -param InitSuccess [in]

Whether the initialization was successful. If <b>TRUE</b>, the initialization succeeded. If <b>FALSE</b>, the initialization failed.


## -remarks



Before SerCx2 starts a custom-transmit transaction, SerCx2 calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_custom_transmit_transaction_initialize">EvtSerCx2CustomTransmitTransactionInitialize</a> event callback function, if it is implemented, to initialize the serial controller to perform the transaction. In response to this call, the driver should first do any initialization that is needed; then the driver must call <b>SerCx2CustomTransmitTransactionInitializeComplete</b> to notify SerCx2. SerCx2 expects this notification and does not start the transaction until it is notified.

The serial controller driver must call <b>SerCx2CustomTransmitTransactionInitializeComplete</b> only in response to a call to the <i>EvtSerCx2CustomTransmitTransactionInitialize</i> function.

For more information, see <a href="https://docs.microsoft.com/previous-versions/dn265320(v=vs.85)">SerCx2 Custom-Transmit Transactions</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_custom_transmit_transaction_initialize">EvtSerCx2CustomTransmitTransactionInitialize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2CUSTOMTRANSMITTRANSACTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2customtransmittransactioncreate">SerCx2CustomTransmitTransactionCreate</a>
 

 

