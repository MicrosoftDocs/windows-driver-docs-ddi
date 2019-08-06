---
UID: NF:sercx.SerCx2CustomReceiveTransactionReportProgress
title: SerCx2CustomReceiveTransactionReportProgress function (sercx.h)
description: The SerCx2CustomReceiveTransactionReportProgress method reports whether progress is being made toward completing the current custom-receive transaction.
old-location: serports\sercx2customreceivetransactionreportprogress.htm
tech.root: serports
ms.assetid: FBC776FE-1056-4D3B-BECB-124FC41DD68F
ms.date: 04/23/2018
ms.keywords: 2/SerCx2CustomReceiveTransactionReportProgress, SerCx2CustomReceiveTransactionReportProgress, SerCx2CustomReceiveTransactionReportProgress method [Serial Ports], serports.sercx2customreceivetransactionreportprogress
ms.topic: function
f1_keywords:
 - "sercx/SerCx2CustomReceiveTransactionReportProgress"
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
- SerCx2CustomReceiveTransactionReportProgress
product:
- Windows
targetos: Windows
req.typenames: 
---

# SerCx2CustomReceiveTransactionReportProgress function


## -description


The <b>SerCx2CustomReceiveTransactionReportProgress</b> method reports whether progress is being made toward completing the current custom-receive transaction.


## -parameters




### -param CustomReceiveTransaction

<p>A <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles"><b>SERCX2CUSTOMRECEIVETRANSACTION</b></a> handle to a custom-receive object. The serial controller driver previously called the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercx2customreceivetransactioncreate"><b>SerCx2CustomReceiveTransactionCreate</b></a> method to create this object.</p>


### -param Progress [in]

Whether progress is being made toward completing the custom-receive transaction. Set this parameter to one of the following enumeration constants:

<ul>
<li>SERCX2_CUSTOM_RECEIVE_NO_PROGRESS</li>
<li>SERCX2_CUSTOM_RECEIVE_BYTES_TRANSFERRED</li>
</ul>
For more information about these enumeration constants, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/ne-sercx-_sercx2_custom_receive_transaction_progress">SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS</a>.


## -returns



None.




## -remarks



To determine whether the serial controller is making progress toward completing the current custom-receive transaction, SerCx2 periodically calls the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/dn265203(v=vs.85)">EvtSerCx2CustomReceiveTransactionQueryProgress</a> event callback function. In response to this call, the serial controller driver calls <b>SerCx2CustomReceiveTransactionReportProgress</b> to provide a progress report.

Each <b>SerCx2CustomReceiveTransactionReportProgress</b> call reports whether any data bytes have been transferred in the current custom-receive transaction since either the previous call to this method or the start of the transaction, whichever is more recent. If one or more bytes have been transferred, the call reports that the serial controller is making progress. If no bytes have been transferred, the call reports that there is no progress.

The serial controller driver must call this method only in response to a call from SerCx2 to the <i>EvtSerCx2CustomReceiveTransactionQueryProgress</i> function.

For more information, see <a href="https://docs.microsoft.com/previous-versions/dn265314(v=vs.85)">SerCx2 Custom-Receive Transactions</a>.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/dn265203(v=vs.85)">EvtSerCx2CustomReceiveTransactionQueryProgress</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2CUSTOMRECEIVETRANSACTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/ne-sercx-_sercx2_custom_receive_transaction_progress">SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercx2customreceivetransactioncreate">SerCx2CustomReceiveTransactionCreate</a>
 

 

