---
UID: NC:sercx.EVT_SERCX2_PIO_TRANSMIT_CLEANUP_TRANSACTION
title: EVT_SERCX2_PIO_TRANSMIT_CLEANUP_TRANSACTION
author: windows-driver-content
description: The EvtSerCx2PioTransmitCleanupTransaction event callback function is called by version 2 of the serial framework extension (SerCx2) to clean up the serial controller state after a PIO-transmit transaction ends.
old-location: serports\evtsercx2piotransmitcleanuptransaction.htm
old-project: serports
ms.assetid: 48300C50-47B7-47DC-BDE5-3847E1EAE820
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: serports.evtsercx2piotransmitcleanuptransaction, EvtSerCx2PioTransmitCleanupTransaction callback function [Serial Ports], EvtSerCx2PioTransmitCleanupTransaction, EVT_SERCX2_PIO_TRANSMIT_CLEANUP_TRANSACTION, EVT_SERCX2_PIO_TRANSMIT_CLEANUP_TRANSACTION, 2/EvtSerCx2PioTransmitCleanupTransaction
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
-	EvtSerCx2PioTransmitCleanupTransaction
product: Windows
targetos: Windows
req.typenames: SENSOR_VALUE_PAIR, *PSENSOR_VALUE_PAIR
req.product: Windows 10 or later.
---

# EVT_SERCX2_PIO_TRANSMIT_CLEANUP_TRANSACTION callback


## -description


The <i>EvtSerCx2PioTransmitCleanupTransaction</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to clean up the serial controller state after a PIO-transmit transaction ends.


## -prototype


````
EVT_SERCX2_PIO_TRANSMIT_CLEANUP_TRANSACTION EvtSerCx2PioTransmitCleanupTransaction;

VOID EvtSerCx2PioTransmitCleanupTransaction(
  _In_ SERCX2PIOTRANSMIT PioTransmit
)
{ ... }
````


## -parameters




### -param PioTransmit [in]

A <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a> handle to a PIO-transmit object. The serial controller driver previously called the <a href="..\sercx\nf-sercx-sercx2piotransmitcreate.md">SerCx2PioTransmitCreate</a> method to create this object.


## -returns


None.



## -remarks


Your serial controller driver can, as an option, implement this function. If implemented, the driver registers the function in the <a href="..\sercx\nf-sercx-sercx2piotransmitcreate.md">SerCx2PioTransmitCreate</a> call that creates the PIO-transmit object.

Your serial controller driver should implement an <i>EvtSerCx2PioTransmitCleanupTransaction</i> function if it needs to clean up the serial controller state at the end of a PIO-transmit transaction. SerCx2 calls this function, if it is implemented, after a PIO-transmit transaction ends. In response to the <i>EvtSerCx2PioTransmitCleanupTransaction</i> call, the serial controller driver must call the <a href="..\sercx\nf-sercx-sercx2piotransmitcleanuptransactioncomplete.md">SerCx2PioTransmitCleanupTransactionComplete</a> method to notify SerCx2 after the clean-up work is done.

For more information, see <a href="https://msdn.microsoft.com/3BEF9A3D-1FEF-4626-B07F-1670359062AF">SerCx2 PIO-Transmit Transactions</a>.



## -see-also

<a href="..\sercx\nf-sercx-sercx2piotransmitcreate.md">SerCx2PioTransmitCreate</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a>

<a href="..\sercx\nf-sercx-sercx2piotransmitcleanuptransactioncomplete.md">SerCx2PioTransmitCleanupTransactionComplete</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX2_PIO_TRANSMIT_CLEANUP_TRANSACTION callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

