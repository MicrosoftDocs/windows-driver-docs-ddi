---
UID: NC:sercx.EVT_SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CLEANUP
title: EVT_SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CLEANUP
author: windows-driver-content
description: The EvtSerCx2CustomTransmitTransactionCleanup event callback function is called by version 2 of the serial framework extension (SerCx2) to clean up the serial controller's hardware state after a custom-transmit transaction ends.
old-location: serports\evtsercx2customtransmittransactioncleanup.htm
old-project: serports
ms.assetid: CEADF06B-FD60-4B4C-AB59-1ED6B1226204
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: serports.evtsercx2customtransmittransactioncleanup, EvtSerCx2CustomTransmitTransactionCleanup callback function [Serial Ports], EvtSerCx2CustomTransmitTransactionCleanup, EVT_SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CLEANUP, EVT_SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CLEANUP, 2/EvtSerCx2CustomTransmitTransactionCleanup
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: sercx.h
req.include-header: 
req.target-type: Desktop
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
req.irql: Called at IRQL <= DISPATCH_LEVEL.
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	2.0\Sercx.h
apiname: 
-	EvtSerCx2CustomTransmitTransactionCleanup
product: Windows
targetos: Windows
req.typenames: *PSENSOR_VALUE_PAIR, SENSOR_VALUE_PAIR
req.product: Windows 10 or later.
---

# EVT_SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CLEANUP callback


## -description


The <i>EvtSerCx2CustomTransmitTransactionCleanup</i> event callback function  is called by version 2 of the serial framework extension (SerCx2) to clean up the serial controller's hardware state after a custom-transmit transaction ends.


## -prototype


````
EVT_SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CLEANUP EvtSerCx2CustomTransmitTransactionCleanup;

VOID EvtSerCx2CustomTransmitTransactionCleanup(
  _In_ SERCX2CUSTOMTRANSMITTRANSACTION CustomTransmitTransaction
)
{ ... }
````


## -parameters




### -param CustomTransmitTransaction [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/dn265257">SERCX2CUSTOMTRANSMITTRANSACTION</a> handle to a custom-transmit object. The serial controller driver previously called the <a href="..\sercx\nf-sercx-sercx2customtransmittransactioncreate.md">SerCx2CustomTransmitTransactionCreate</a> method to create this object.


## -returns


None.



## -remarks


Your serial controller driver can, as an option, implement this function. If implemented, the driver registers the function in the <a href="..\sercx\nf-sercx-sercx2customtransmittransactioncreate.md">SerCx2CustomTransmitTransactionCreate</a> call that creates the custom-transmit object.

Your serial controller driver should implement an <i>EvtSerCx2CustomTransmitTransactionCleanup</i> function if it needs to clean up the serial controller state at the end of a custom-transmit transaction. SerCx2 calls this function, if it is implemented, after a custom-transmit transaction ends. In response to the <i>EvtSerCx2CustomTransmitTransactionCleanup</i> call, the serial controller driver must call the <a href="..\sercx\nf-sercx-sercx2customtransmittransactioncleanupcomplete.md">SerCx2CustomTransmitTransactionCleanupComplete</a> method to notify SerCx2 after the clean-up work is done.

For more information, see <a href="https://msdn.microsoft.com/E72E68BC-A60A-41BE-8606-92A608648042">SerCx2 Custom-Transmit Transactions</a>.



## -see-also

<a href="..\sercx\nf-sercx-sercx2customtransmittransactioncreate.md">SerCx2CustomTransmitTransactionCreate</a>

<a href="..\sercx\nf-sercx-sercx2customtransmittransactioncleanupcomplete.md">SerCx2CustomTransmitTransactionCleanupComplete</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/dn265257">SERCX2CUSTOMTRANSMITTRANSACTION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX2_CUSTOM_TRANSMIT_TRANSACTION_CLEANUP callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

