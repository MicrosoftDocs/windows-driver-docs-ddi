---
UID: NC:sercx.EVT_SERCX2_CUSTOM_TRANSMIT_TRANSACTION_INITIALIZE
title: EVT_SERCX2_CUSTOM_TRANSMIT_TRANSACTION_INITIALIZE
author: windows-driver-content
description: The EvtSerCx2CustomTransmitTransactionInitialize event callback function is called by version 2 of the serial framework extension (SerCx2) to prepare the serial controller driver to perform a custom-transmit transaction.
old-location: serports\evtsercx2customtransmittransactioninitialize.htm
old-project: serports
ms.assetid: CFC577D6-747F-4752-8CB6-7410C21487B6
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: serports.evtsercx2customtransmittransactioninitialize, EvtSerCx2CustomTransmitTransactionInitialize callback function [Serial Ports], EvtSerCx2CustomTransmitTransactionInitialize, EVT_SERCX2_CUSTOM_TRANSMIT_TRANSACTION_INITIALIZE, EVT_SERCX2_CUSTOM_TRANSMIT_TRANSACTION_INITIALIZE, 2/EvtSerCx2CustomTransmitTransactionInitialize
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
-	EvtSerCx2CustomTransmitTransactionInitialize
product: Windows
targetos: Windows
req.typenames: SENSOR_VALUE_PAIR, *PSENSOR_VALUE_PAIR
req.product: Windows 10 or later.
---

# EVT_SERCX2_CUSTOM_TRANSMIT_TRANSACTION_INITIALIZE callback


## -description


The <i>EvtSerCx2CustomTransmitTransactionInitialize</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to prepare the serial controller driver to perform a custom-transmit transaction.


## -prototype


````
EVT_SERCX2_CUSTOM_TRANSMIT_TRANSACTION_INITIALIZE EvtSerCx2CustomTransmitTransactionInitialize;

VOID EvtSerCx2CustomTransmitTransactionInitialize(
  _In_ SERCX2CUSTOMTRANSMITTRANSACTION CustomTransmitTransaction,
  _In_ PMDL                            Mdl,
  _In_ ULONG                           Offset,
  _In_ ULONG                           Length
)
{ ... }
````


## -parameters




### -param CustomTransmitTransaction [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/dn265257">SERCX2CUSTOMTRANSMITTRANSACTION</a> handle to a custom-transmit object. The serial controller driver previously called the <a href="..\sercx\nf-sercx-sercx2customtransmittransactioncreate.md">SerCx2CustomTransmitTransactionCreate</a> method to create this object.


### -param Mdl [in]

A pointer to an <a href="..\wdm\ns-wdm-_mdl.md">MDL</a> that describes the memory pages that are spanned by the write buffer for the custom-transmit transaction. The scatter/gather list for the DMA transfer will use the region of this memory that is specified by the <i>Offset</i> and <i>Length</i> parameters.


### -param Offset [in]

The starting offset for the data transfer. This parameter is a byte offset from the start of the buffer region described by the MDL. If the MDL specifies a total of N bytes of buffer space, possible values of <i>Offset</i> are in the range 0 to N–1.


### -param Length [in]

The size, in bytes, of the data transfer. If the MDL specifies a total of N bytes of buffer space, possible values of <i>Length</i> are in the range 1 to N–<i>Offset</i>.


## -returns


None.



## -remarks


Your serial controller driver can, as an option, implement this function. If implemented, the driver registers the function in the <a href="..\sercx\nf-sercx-sercx2customtransmittransactioncreate.md">SerCx2CustomTransmitTransactionCreate</a> call that creates the custom-transmit object.

Your driver should implement an <i>EvtSerCx2CustomTransmitTransactionInitialize</i> function if it needs to initialize the serial controller and associated hardware in preparation for a new custom-transmit transaction. SerCx2 calls this function, if it is implemented, before starting the custom-transmit transaction. In response to this call, the serial controller driver must call the <a href="..\sercx\nf-sercx-sercx2customtransmittransactioninitializecomplete.md">SerCx2CustomTransmitTransactionInitializeComplete</a> method to notify SerCx2 after the initialization is finished.

For more information, see <a href="https://msdn.microsoft.com/E72E68BC-A60A-41BE-8606-92A608648042">SerCx2 Custom-Transmit Transactions</a>.



## -see-also

<a href="..\wdm\ns-wdm-_mdl.md">MDL</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>

<a href="..\sercx\nf-sercx-sercx2customtransmittransactioncreate.md">SerCx2CustomTransmitTransactionCreate</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/dn265257">SERCX2CUSTOMTRANSMITTRANSACTION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX2_CUSTOM_TRANSMIT_TRANSACTION_INITIALIZE callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

