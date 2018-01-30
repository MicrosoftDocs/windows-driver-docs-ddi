---
UID: NC:sercx.EVT_SERCX2_PIO_RECEIVE_INITIALIZE_TRANSACTION
title: EVT_SERCX2_PIO_RECEIVE_INITIALIZE_TRANSACTION
author: windows-driver-content
description: The EvtSerCx2PioReceiveInitializeTransaction event callback function is called by version 2 of the serial framework extension (SerCx2) to prepare the serial controller to perform a PIO-receive transaction.
old-location: serports\evtsercx2pioreceiveinitializetransaction.htm
old-project: serports
ms.assetid: E03B5319-BBBE-4396-8D03-8BC82FB97D15
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: serports.evtsercx2pioreceiveinitializetransaction, EvtSerCx2PioReceiveInitializeTransaction callback function [Serial Ports], EvtSerCx2PioReceiveInitializeTransaction, EVT_SERCX2_PIO_RECEIVE_INITIALIZE_TRANSACTION, EVT_SERCX2_PIO_RECEIVE_INITIALIZE_TRANSACTION, 2/EvtSerCx2PioReceiveInitializeTransaction
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
-	EvtSerCx2PioReceiveInitializeTransaction
product: Windows
targetos: Windows
req.typenames: SENSOR_VALUE_PAIR, *PSENSOR_VALUE_PAIR
req.product: Windows 10 or later.
---

# EVT_SERCX2_PIO_RECEIVE_INITIALIZE_TRANSACTION callback


## -description


The <i>EvtSerCx2PioReceiveInitializeTransaction</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to prepare the serial controller to perform a PIO-receive transaction.


## -prototype


````
EVT_SERCX2_PIO_RECEIVE_INITIALIZE_TRANSACTION EvtSerCx2PioReceiveInitializeTransaction;

VOID EvtSerCx2PioReceiveInitializeTransaction(
  _In_ SERCX2PIORECEIVE PioReceive,
  _In_ ULONG            Length
)
{ ... }
````


## -parameters




### -param PioReceive [in]

A <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIORECEIVE</a> handle to a PIO-receive object. The serial controller driver previously called the <a href="..\sercx\nf-sercx-sercx2pioreceivecreate.md">SerCx2PioReceiveCreate</a> method to create this object.


### -param Length [in]

The number of bytes to be transferred in the PIO-receive transaction.


## -returns


None.



## -remarks


Your serial controller driver can, as an option, implement this function. If implemented, the driver registers the function in the call to the <a href="..\sercx\nf-sercx-sercx2pioreceivecreate.md">SerCx2PioReceiveCreate</a> method that creates the PIO-receive object.

Your driver should implement an <i>EvtSerCx2PioReceiveInitializeTransaction</i> function if it needs to initialize the serial controller and associated hardware in preparation for a new PIO-receive transaction. SerCx2 calls this function, if it is implemented, before a PIO-receive transaction starts. In response to this call, the serial controller driver must call the <a href="..\sercx\nf-sercx-sercx2pioreceiveinitializetransactioncomplete.md">SerCx2PioReceiveInitializeTransactionComplete</a> method to notify SerCx2 after the initialization is finished.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265332">SerCx2 PIO-Receive Transactions</a>.



## -see-also

<a href="..\sercx\nf-sercx-sercx2pioreceivecreate.md">SerCx2PioReceiveCreate</a>

<a href="..\sercx\nf-sercx-sercx2pioreceiveinitializetransactioncomplete.md">SerCx2PioReceiveInitializeTransactionComplete</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIORECEIVE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX2_PIO_RECEIVE_INITIALIZE_TRANSACTION callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

