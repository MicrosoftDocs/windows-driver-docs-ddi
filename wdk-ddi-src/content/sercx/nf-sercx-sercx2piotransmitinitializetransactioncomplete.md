---
UID: NF:sercx.SerCx2PioTransmitInitializeTransactionComplete
title: SerCx2PioTransmitInitializeTransactionComplete function
author: windows-driver-content
description: The SerCx2PioTransmitInitializeTransactionComplete method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished initializing the serial controller hardware in preparation for a new PIO-transmit transaction.
old-location: serports\sercx2piotransmitinitializetransactioncomplete.htm
old-project: serports
ms.assetid: 3A2CA5FB-0844-4992-9A05-DDF9D7F1BADC
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SerCx2PioTransmitInitializeTransactionComplete, 2/SerCx2PioTransmitInitializeTransactionComplete, serports.sercx2piotransmitinitializetransactioncomplete, SerCx2PioTransmitInitializeTransactionComplete method [Serial Ports]
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
-	SerCx2PioTransmitInitializeTransactionComplete
product: Windows
targetos: Windows
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---

# SerCx2PioTransmitInitializeTransactionComplete function


## -description


The <b>SerCx2PioTransmitInitializeTransactionComplete</b> method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished initializing the serial controller hardware in preparation for a new PIO-transmit transaction.


## -syntax


````
VOID SerCx2PioTransmitInitializeTransactionComplete(
  [in] SERCX2PIOTRANSMIT PioTransmit,
  [in] BOOLEAN           InitSuccess
);
````


## -parameters




### -param PioTransmit [in]

A <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a> handle to a PIO-transmit object. The serial controller driver previously called the <a href="..\sercx\nf-sercx-sercx2piotransmitcreate.md">SerCx2PioTransmitCreate</a> method to create this object.


### -param InitSuccess [in]

Whether the initialization was successful. If <b>TRUE</b>, the initialization succeeded. If <b>FALSE</b>, the initialization failed.


## -returns


None.



## -remarks


Before SerCx2 initiates a PIO-transmit transaction, SerCx2 calls the <a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_initialize_transaction.md">EvtSerCx2PioTransmitInitializeTransaction</a> event callback function, if it is implemented, to initialize the serial controller to perform the transaction. In response to this call, the driver should first do any initialization that is needed; then the driver must call <b>SerCx2PioTransmitInitializeTransactionComplete</b> to notify SerCx2. SerCx2 expects this notification and does not start the transaction until it is notified.

The serial controller driver must call <b>SerCx2PioTransmitInitializeTransactionComplete</b> only in response to a call to the <i>EvtSerCx2PioTransmitInitializeTransaction</i> function.

For more information, see <a href="https://msdn.microsoft.com/3BEF9A3D-1FEF-4626-B07F-1670359062AF">SerCx2 PIO-Transmit Transactions</a>.



## -see-also

<a href="..\sercx\nf-sercx-sercx2piotransmitcreate.md">SerCx2PioTransmitCreate</a>

<a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_initialize_transaction.md">EvtSerCx2PioTransmitInitializeTransaction</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCx2PioTransmitInitializeTransactionComplete method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

