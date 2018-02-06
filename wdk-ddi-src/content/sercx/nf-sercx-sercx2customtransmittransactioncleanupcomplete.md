---
UID: NF:sercx.SerCx2CustomTransmitTransactionCleanupComplete
title: SerCx2CustomTransmitTransactionCleanupComplete function
author: windows-driver-content
description: The SerCx2CustomTransmitTransactionCleanupComplete method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished cleaning up the serial controller's hardware state after a custom-transmit transaction.
old-location: serports\sercx2customtransmittransactioncleanupcomplete.htm
old-project: serports
ms.assetid: 5B9EBE82-A49A-4AD9-B07B-C0D17C5F3732
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: serports.sercx2customtransmittransactioncleanupcomplete, SerCx2CustomTransmitTransactionCleanupComplete method [Serial Ports], SerCx2CustomTransmitTransactionCleanupComplete, 2/SerCx2CustomTransmitTransactionCleanupComplete
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
-	SerCx2CustomTransmitTransactionCleanupComplete
product: Windows
targetos: Windows
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---

# SerCx2CustomTransmitTransactionCleanupComplete function


## -description


The <b>SerCx2CustomTransmitTransactionCleanupComplete</b> method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished cleaning up the serial controller's hardware state after a custom-transmit transaction.


## -syntax


````
VOID SerCx2CustomTransmitTransactionCleanupComplete(
  [in] SERCX2CUSTOMTRANSMITTRANSACTION CustomTransmitTransaction
);
````


## -parameters




### -param CustomTransmitTransaction [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/dn265257">SERCX2CUSTOMTRANSMITTRANSACTION</a> handle to a custom-transmit object. The serial controller driver previously called the <a href="..\sercx\nf-sercx-sercx2customtransmittransactioncreate.md">SerCx2CustomTransmitTransactionCreate</a> method to create this object.


## -returns


None.



## -remarks


After a custom-transmit transaction ends, SerCx2 calls the <a href="..\sercx\nc-sercx-evt_sercx2_custom_transmit_transaction_cleanup.md">EvtSerCx2CustomTransmitTransactionCleanup</a> event callback function, if it is implemented, to clean up the serial controller state. In response to this call, the driver should first do any clean-up work that is needed; then the driver must call <b>SerCx2CustomTransmitTransactionCleanupComplete</b> to notify SerCx2. SerCx2 expects this notification and does not start the next transaction until it is notified.

A serial controller driver must call <b>SerCx2CustomTransmitTransactionCleanupComplete</b> only in response to a call to the <i>EvtSerCx2CustomTransmitTransactionCleanup</i> function.

For more information, see <a href="https://msdn.microsoft.com/E72E68BC-A60A-41BE-8606-92A608648042">SerCx2 Custom-Transmit Transactions</a>.



## -see-also

<a href="..\sercx\nc-sercx-evt_sercx2_custom_transmit_transaction_cleanup.md">EvtSerCx2CustomTransmitTransactionCleanup</a>

<a href="..\sercx\nf-sercx-sercx2customtransmittransactioncreate.md">SerCx2CustomTransmitTransactionCreate</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/dn265257">SERCX2CUSTOMTRANSMITTRANSACTION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCx2CustomTransmitTransactionCleanupComplete method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

