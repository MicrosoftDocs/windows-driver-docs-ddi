---
UID: NF:sercx.SerCx2CustomTransmitTransactionInitializeComplete
title: SerCx2CustomTransmitTransactionInitializeComplete function
author: windows-driver-content
description: The SerCx2CustomTransmitTransactionInitializeComplete method informs version 2 of the serial framework extension (SerCx2) that the serial driver has finished initializing the serial controller and associated hardware in preparation for a new custom-transmit transaction.
old-location: serports\sercx2customtransmittransactioninitializecomplete.htm
old-project: serports
ms.assetid: 5C2BF433-11C0-425A-B14A-7A0275F7DF51
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: 2/SerCx2CustomTransmitTransactionInitializeComplete, SerCx2CustomTransmitTransactionInitializeComplete, serports.sercx2customtransmittransactioninitializecomplete, SerCx2CustomTransmitTransactionInitializeComplete method [Serial Ports]
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
req.irql: <= DISPATCH_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	COM
apilocation: 
-	2.0\Sercx.h
apiname: 
-	SerCx2CustomTransmitTransactionInitializeComplete
product: Windows
targetos: Windows
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---

# SerCx2CustomTransmitTransactionInitializeComplete function


## -description


The <b>SerCx2CustomTransmitTransactionInitializeComplete</b> method informs version 2 of the serial framework extension (SerCx2) that the serial driver has finished initializing the serial controller and associated hardware in preparation for a new custom-transmit transaction.


## -syntax


````
VOID SerCx2CustomTransmitTransactionInitializeComplete(
  [in] SERCX2CUSTOMTRANSMITTRANSACTION CustomTransmitTransaction,
  [in] BOOLEAN                         InitSuccess
);
````


## -parameters




### -param CustomTransmitTransaction [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/dn265257">SERCX2CUSTOMTRANSMITTRANSACTION</a> handle to a custom-transmit object. The serial controller driver previously called the <a href="..\sercx\nf-sercx-sercx2customtransmittransactioncreate.md">SerCx2CustomTransmitTransactionCreate</a> method to create this object.


### -param InitSuccess [in]

Whether the initialization was successful. If <b>TRUE</b>, the initialization succeeded. If <b>FALSE</b>, the initialization failed.


## -returns


None.



## -remarks


Before SerCx2 starts a custom-transmit transaction, SerCx2 calls the <a href="..\sercx\nc-sercx-evt_sercx2_custom_transmit_transaction_initialize.md">EvtSerCx2CustomTransmitTransactionInitialize</a> event callback function, if it is implemented, to initialize the serial controller to perform the transaction. In response to this call, the driver should first do any initialization that is needed; then the driver must call <b>SerCx2CustomTransmitTransactionInitializeComplete</b> to notify SerCx2. SerCx2 expects this notification and does not start the transaction until it is notified.

The serial controller driver must call <b>SerCx2CustomTransmitTransactionInitializeComplete</b> only in response to a call to the <i>EvtSerCx2CustomTransmitTransactionInitialize</i> function.

For more information, see <a href="https://msdn.microsoft.com/E72E68BC-A60A-41BE-8606-92A608648042">SerCx2 Custom-Transmit Transactions</a>.



## -see-also

<a href="..\sercx\nf-sercx-sercx2customtransmittransactioncreate.md">SerCx2CustomTransmitTransactionCreate</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/dn265257">SERCX2CUSTOMTRANSMITTRANSACTION</a>

<a href="..\sercx\nc-sercx-evt_sercx2_custom_transmit_transaction_initialize.md">EvtSerCx2CustomTransmitTransactionInitialize</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCx2CustomTransmitTransactionInitializeComplete method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

