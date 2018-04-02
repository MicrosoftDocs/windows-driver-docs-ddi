---
UID: NF:sercx.SerCx2CustomReceiveTransactionInitializeComplete
title: SerCx2CustomReceiveTransactionInitializeComplete function
author: windows-driver-content
description: The SerCx2CustomReceiveTransactionInitializeComplete method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished initializing the serial controller and associated hardware in preparation for a new custom-receive transaction.
old-location: serports\sercx2customreceivetransactioninitializecomplete.htm
old-project: serports
ms.assetid: C2D7C955-B63E-4D99-BC20-F7684C8D61F8
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: 2/SerCx2CustomReceiveTransactionInitializeComplete, SerCx2CustomReceiveTransactionInitializeComplete, SerCx2CustomReceiveTransactionInitializeComplete method [Serial Ports], serports.sercx2customreceivetransactioninitializecomplete
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	2.0\Sercx.h
api_name:
-	SerCx2CustomReceiveTransactionInitializeComplete
product: Windows
targetos: Windows
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---

# SerCx2CustomReceiveTransactionInitializeComplete function


## -description


The <b>SerCx2CustomReceiveTransactionInitializeComplete</b> method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished initializing the serial controller and associated hardware in preparation for  a new custom-receive transaction.


## -parameters




### -param CustomReceiveTransaction [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/dn265249">SERCX2CUSTOMRECEIVETRANSACTION</a> handle to a custom-receive object. The serial controller driver previously called the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265251">SerCx2CustomReceiveTransactionCreate</a> method to create this object.


### -param InitSuccess [in]

Whether the initialization was successful. If <b>TRUE</b>, the initialization succeeded. If <b>FALSE</b>, the initialization failed.


## -returns



None.




## -remarks



Before SerCx2 starts a custom-receive transaction, SerCx2 calls the <a href="https://msdn.microsoft.com/B3C23236-2A35-456A-B461-AEC688ACA5B7">EvtSerCx2CustomReceiveTransactionInitialize</a> event callback function, if it is implemented, to initialize the serial controller to perform the transaction. In response to this call, the driver should first do any initialization that is needed; then the driver must call <b>SerCx2CustomReceiveTransactionInitializeComplete</b> to notify SerCx2. SerCx2 expects this notification and does not start the transaction until it is notified.

The serial controller driver must call <b>SerCx2CustomReceiveTransactionInitializeComplete</b> only in response to a call to the <i>EvtSerCx2CustomReceiveTransactionInitialize</i> function.

For more information, see <a href="https://msdn.microsoft.com/29849A8C-6656-444C-BE91-405A4BA2D5B0">SerCx2 Custom-Receive Transactions</a>.




## -see-also




<a href="https://msdn.microsoft.com/B3C23236-2A35-456A-B461-AEC688ACA5B7">EvtSerCx2CustomReceiveTransactionInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265249">SERCX2CUSTOMRECEIVETRANSACTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265251">SerCx2CustomReceiveTransactionCreate</a>
 

 

