---
UID: NF:sercx.SerCx2CustomReceiveTransactionCleanupComplete
title: SerCx2CustomReceiveTransactionCleanupComplete function (sercx.h)
description: The SerCx2CustomReceiveTransactionCleanupComplete method informs version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished cleaning up the serial controller's hardware state after a custom-receive transaction.
old-location: serports\sercx2customreceivetransactioncleanupcomplete.htm
tech.root: serports
ms.assetid: 45CCCD97-94FD-457B-8315-06DC701B22A2
ms.date: 04/23/2018
keywords: ["SerCx2CustomReceiveTransactionCleanupComplete function"]
ms.keywords: 2/SerCx2CustomReceiveTransactionCleanupComplete, SerCx2CustomReceiveTransactionCleanupComplete, SerCx2CustomReceiveTransactionCleanupComplete method [Serial Ports], serports.sercx2customreceivetransactioncleanupcomplete
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
 - SerCx2CustomReceiveTransactionCleanupComplete
 - sercx/SerCx2CustomReceiveTransactionCleanupComplete
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - 2.0\Sercx.h
api_name:
 - SerCx2CustomReceiveTransactionCleanupComplete
---

# SerCx2CustomReceiveTransactionCleanupComplete function


## -description

The <b>SerCx2CustomReceiveTransactionCleanupComplete</b> method informs version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished cleaning up the serial controller's hardware state after a custom-receive transaction.

## -parameters

### -param CustomReceiveTransaction 

[in]
A <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2CUSTOMRECEIVETRANSACTION</a> handle to a custom-receive object. The serial controller driver previously called the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2customreceivetransactioncreate">SerCx2CustomReceiveTransactionCreate</a> method to create this object.

## -remarks

After a custom-receive transaction ends, SerCx2 calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_custom_receive_transaction_cleanup">EvtSerCx2CustomReceiveTransactionCleanup</a> event callback function, if it is implemented, to clean up the serial controller state. In response to this call, the driver should first do any clean-up work that is needed; then the driver must call <b>SerCx2CustomReceiveTransactionCleanupComplete</b> to notify SerCx2. SerCx2 expects this notification and does not start the next transaction until it is notified.

The serial controller driver must call <b>SerCx2CustomReceiveTransactionCleanupComplete</b> only in response to a call to the <i>EvtSerCx2CustomReceiveTransactionCleanup</i> function.

For more information, see <a href="https://docs.microsoft.com/previous-versions/dn265314(v=vs.85)">SerCx2 Custom-Receive Transactions</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_custom_receive_transaction_cleanup">EvtSerCx2CustomReceiveTransactionCleanup</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2CUSTOMRECEIVETRANSACTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2customreceivetransactioncreate">SerCx2CustomReceiveTransactionCreate</a>

