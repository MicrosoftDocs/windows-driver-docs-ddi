---
UID: NF:sercx.SerCx2CustomReceiveTransactionCleanupComplete
title: SerCx2CustomReceiveTransactionCleanupComplete function (sercx.h)
description: The SerCx2CustomReceiveTransactionCleanupComplete method informs version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished cleaning up the serial controller's hardware state after a custom-receive transaction.
old-location: serports\sercx2customreceivetransactioncleanupcomplete.htm
tech.root: serports
ms.assetid: 45CCCD97-94FD-457B-8315-06DC701B22A2
ms.date: 04/23/2018
ms.keywords: 2/SerCx2CustomReceiveTransactionCleanupComplete, SerCx2CustomReceiveTransactionCleanupComplete, SerCx2CustomReceiveTransactionCleanupComplete method [Serial Ports], serports.sercx2customreceivetransactioncleanupcomplete
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- 2.0\Sercx.h
api_name:
- SerCx2CustomReceiveTransactionCleanupComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# SerCx2CustomReceiveTransactionCleanupComplete function


## -description


The <b>SerCx2CustomReceiveTransactionCleanupComplete</b> method informs version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished cleaning up the serial controller's hardware state after a custom-receive transaction.


## -parameters




### -param CustomReceiveTransaction [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/dn265249">SERCX2CUSTOMRECEIVETRANSACTION</a> handle to a custom-receive object. The serial controller driver previously called the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265251">SerCx2CustomReceiveTransactionCreate</a> method to create this object.


## -returns



None.




## -remarks



After a custom-receive transaction ends, SerCx2 calls the <a href="https://msdn.microsoft.com/72AF3D52-D109-42A7-9F25-14A3F5EDC94A">EvtSerCx2CustomReceiveTransactionCleanup</a> event callback function, if it is implemented, to clean up the serial controller state. In response to this call, the driver should first do any clean-up work that is needed; then the driver must call <b>SerCx2CustomReceiveTransactionCleanupComplete</b> to notify SerCx2. SerCx2 expects this notification and does not start the next transaction until it is notified.

The serial controller driver must call <b>SerCx2CustomReceiveTransactionCleanupComplete</b> only in response to a call to the <i>EvtSerCx2CustomReceiveTransactionCleanup</i> function.

For more information, see <a href="https://msdn.microsoft.com/29849A8C-6656-444C-BE91-405A4BA2D5B0">SerCx2 Custom-Receive Transactions</a>.




## -see-also




<a href="https://msdn.microsoft.com/72AF3D52-D109-42A7-9F25-14A3F5EDC94A">EvtSerCx2CustomReceiveTransactionCleanup</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265249">SERCX2CUSTOMRECEIVETRANSACTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265251">SerCx2CustomReceiveTransactionCreate</a>
 

 

