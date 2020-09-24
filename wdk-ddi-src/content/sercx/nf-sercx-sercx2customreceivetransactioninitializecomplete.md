---
UID: NF:sercx.SerCx2CustomReceiveTransactionInitializeComplete
title: SerCx2CustomReceiveTransactionInitializeComplete function (sercx.h)
description: The SerCx2CustomReceiveTransactionInitializeComplete method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished initializing the serial controller and associated hardware in preparation for a new custom-receive transaction.
old-location: serports\sercx2customreceivetransactioninitializecomplete.htm
tech.root: serports
ms.assetid: C2D7C955-B63E-4D99-BC20-F7684C8D61F8
ms.date: 04/23/2018
keywords: ["SerCx2CustomReceiveTransactionInitializeComplete function"]
ms.keywords: 2/SerCx2CustomReceiveTransactionInitializeComplete, SerCx2CustomReceiveTransactionInitializeComplete, SerCx2CustomReceiveTransactionInitializeComplete method [Serial Ports], serports.sercx2customreceivetransactioninitializecomplete
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
targetos: Windows
req.typenames: 
f1_keywords:
 - SerCx2CustomReceiveTransactionInitializeComplete
 - sercx/SerCx2CustomReceiveTransactionInitializeComplete
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - 2.0\Sercx.h
api_name:
 - SerCx2CustomReceiveTransactionInitializeComplete
---

# SerCx2CustomReceiveTransactionInitializeComplete function


## -description

The <b>SerCx2CustomReceiveTransactionInitializeComplete</b> method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished initializing the serial controller and associated hardware in preparation for  a new custom-receive transaction.

## -parameters

### -param CustomReceiveTransaction 

[in]
A <a href="/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2CUSTOMRECEIVETRANSACTION</a> handle to a custom-receive object. The serial controller driver previously called the <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2customreceivetransactioncreate">SerCx2CustomReceiveTransactionCreate</a> method to create this object.

### -param InitSuccess 

[in]
Whether the initialization was successful. If <b>TRUE</b>, the initialization succeeded. If <b>FALSE</b>, the initialization failed.

## -remarks

Before SerCx2 starts a custom-receive transaction, SerCx2 calls the <a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_custom_receive_transaction_initialize">EvtSerCx2CustomReceiveTransactionInitialize</a> event callback function, if it is implemented, to initialize the serial controller to perform the transaction. In response to this call, the driver should first do any initialization that is needed; then the driver must call <b>SerCx2CustomReceiveTransactionInitializeComplete</b> to notify SerCx2. SerCx2 expects this notification and does not start the transaction until it is notified.

The serial controller driver must call <b>SerCx2CustomReceiveTransactionInitializeComplete</b> only in response to a call to the <i>EvtSerCx2CustomReceiveTransactionInitialize</i> function.

For more information, see <a href="/previous-versions/dn265314(v=vs.85)">SerCx2 Custom-Receive Transactions</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_custom_receive_transaction_initialize">EvtSerCx2CustomReceiveTransactionInitialize</a>



<a href="/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2CUSTOMRECEIVETRANSACTION</a>



<a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2customreceivetransactioncreate">SerCx2CustomReceiveTransactionCreate</a>