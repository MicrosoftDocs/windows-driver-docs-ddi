---
UID: NF:sercx.SerCx2CustomReceiveTransactionInitializeComplete
title: SerCx2CustomReceiveTransactionInitializeComplete function
author: windows-driver-content
description: The SerCx2CustomReceiveTransactionInitializeComplete method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished initializing the serial controller and associated hardware in preparation for a new custom-receive transaction.
old-location: serports\sercx2customreceivetransactioninitializecomplete.htm
old-project: serports
ms.assetid: C2D7C955-B63E-4D99-BC20-F7684C8D61F8
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SerCx2CustomReceiveTransactionInitializeComplete method [Serial Ports], serports.sercx2customreceivetransactioninitializecomplete, SerCx2CustomReceiveTransactionInitializeComplete, 2/SerCx2CustomReceiveTransactionInitializeComplete
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	2.0\Sercx.h
apiname:
-	SerCx2CustomReceiveTransactionInitializeComplete
product: Windows
targetos: Windows
req.typenames: "*PSERCX_STATUS, SERCX_STATUS"
req.product: Windows 10 or later.
---

# SerCx2CustomReceiveTransactionInitializeComplete function


## -description


The <b>SerCx2CustomReceiveTransactionInitializeComplete</b> method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished initializing the serial controller and associated hardware in preparation for  a new custom-receive transaction.


## -syntax


````
VOID SerCx2CustomReceiveTransactionInitializeComplete(
  [in] SERCX2CUSTOMRECEIVETRANSACTION CustomReceiveTransaction,
  [in] BOOLEAN                        InitSuccess
);
````


## -parameters




#### - CustomReceiveTransaction [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/dn265249">SERCX2CUSTOMRECEIVETRANSACTION</a> handle to a custom-receive object. The serial controller driver previously called the <a href="..\sercx\nf-sercx-sercx2customreceivetransactioncreate.md">SerCx2CustomReceiveTransactionCreate</a> method to create this object.


#### - InitSuccess [in]

Whether the initialization was successful. If <b>TRUE</b>, the initialization succeeded. If <b>FALSE</b>, the initialization failed.


## -returns


None.



## -remarks


Before SerCx2 starts a custom-receive transaction, SerCx2 calls the <a href="..\sercx\nc-sercx-evt_sercx2_custom_receive_transaction_initialize.md">EvtSerCx2CustomReceiveTransactionInitialize</a> event callback function, if it is implemented, to initialize the serial controller to perform the transaction. In response to this call, the driver should first do any initialization that is needed; then the driver must call <b>SerCx2CustomReceiveTransactionInitializeComplete</b> to notify SerCx2. SerCx2 expects this notification and does not start the transaction until it is notified.

The serial controller driver must call <b>SerCx2CustomReceiveTransactionInitializeComplete</b> only in response to a call to the <i>EvtSerCx2CustomReceiveTransactionInitialize</i> function.

For more information, see <a href="https://msdn.microsoft.com/29849A8C-6656-444C-BE91-405A4BA2D5B0">SerCx2 Custom-Receive Transactions</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn265249">SERCX2CUSTOMRECEIVETRANSACTION</a>

<a href="..\sercx\nc-sercx-evt_sercx2_custom_receive_transaction_initialize.md">EvtSerCx2CustomReceiveTransactionInitialize</a>

<a href="..\sercx\nf-sercx-sercx2customreceivetransactioncreate.md">SerCx2CustomReceiveTransactionCreate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCx2CustomReceiveTransactionInitializeComplete method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

