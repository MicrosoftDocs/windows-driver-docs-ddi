---
UID: NC:sercx.EVT_SERCX2_PIO_TRANSMIT_INITIALIZE_TRANSACTION
title: EVT_SERCX2_PIO_TRANSMIT_INITIALIZE_TRANSACTION
author: windows-driver-content
description: The EvtSerCx2PioTransmitInitializeTransaction event callback function is called by version 2 of the serial framework extension (SerCx2) to prepare the serial controller driver to perform a PIO-transmit transaction.
old-location: serports\evtsercx2piotransmitinitializetransaction.htm
old-project: serports
ms.assetid: 2E3652CB-24F1-4467-AF1D-CFD52392B2DB
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: serports.evtsercx2piotransmitinitializetransaction, EvtSerCx2PioTransmitInitializeTransaction callback function [Serial Ports], EvtSerCx2PioTransmitInitializeTransaction, EVT_SERCX2_PIO_TRANSMIT_INITIALIZE_TRANSACTION, EVT_SERCX2_PIO_TRANSMIT_INITIALIZE_TRANSACTION, 2/EvtSerCx2PioTransmitInitializeTransaction
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
-	EvtSerCx2PioTransmitInitializeTransaction
product: Windows
targetos: Windows
req.typenames: *PSENSOR_VALUE_PAIR, SENSOR_VALUE_PAIR
req.product: Windows 10 or later.
---

# EVT_SERCX2_PIO_TRANSMIT_INITIALIZE_TRANSACTION callback


## -description


The <i>EvtSerCx2PioTransmitInitializeTransaction</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to prepare the serial controller driver to perform a PIO-transmit transaction.


## -prototype


````
EVT_SERCX2_PIO_TRANSMIT_INITIALIZE_TRANSACTION EvtSerCx2PioTransmitInitializeTransaction;

VOID EvtSerCx2PioTransmitInitializeTransaction(
  _In_ SERCX2PIOTRANSMIT PioTransmit,
  _In_ ULONG             Length
)
{ ... }
````


## -parameters




### -param PioTransmit [in]

A <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a> handle to a PIO-transmit object. The serial controller driver previously called the <a href="..\sercx\nf-sercx-sercx2piotransmitcreate.md">SerCx2PioTransmitCreate</a> method to create this object.


### -param Length [in]

The number of bytes to be transferred in the PIO-transmit transaction.


## -returns


None.



## -remarks


Your serial controller driver can, as an option, implement this function. If implemented, the driver registers the function in the <a href="..\sercx\nf-sercx-sercx2piotransmitcreate.md">SerCx2PioTransmitCreate</a> call that creates the PIO-transmit object.

Your driver should implement an <i>EvtSerCx2PioTransmitInitializeTransaction</i> function if it needs to initialize the serial controller and associated hardware in preparation for a new PIO-transmit transaction. SerCx2 calls this function, if it is implemented, before a PIO-transmit transaction starts. In response to this call, the serial controller driver must call the <a href="..\sercx\nf-sercx-sercx2piotransmitinitializetransactioncomplete.md">SerCx2PioTransmitInitializeTransactionComplete</a> method to notify SerCx2 after the initialization is finished.

For more information, see <a href="https://msdn.microsoft.com/3BEF9A3D-1FEF-4626-B07F-1670359062AF">SerCx2 PIO-Transmit Transactions</a>.



## -see-also

<a href="..\sercx\nf-sercx-sercx2piotransmitcreate.md">SerCx2PioTransmitCreate</a>

<a href="..\sercx\nf-sercx-sercx2piotransmitinitializetransactioncomplete.md">SerCx2PioTransmitInitializeTransactionComplete</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX2_PIO_TRANSMIT_INITIALIZE_TRANSACTION callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

