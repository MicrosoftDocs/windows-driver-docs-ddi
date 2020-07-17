---
UID: NC:sercx.EVT_SERCX2_PIO_TRANSMIT_INITIALIZE_TRANSACTION
title: EVT_SERCX2_PIO_TRANSMIT_INITIALIZE_TRANSACTION (sercx.h)
description: The EvtSerCx2PioTransmitInitializeTransaction event callback function is called by version 2 of the serial framework extension (SerCx2) to prepare the serial controller driver to perform a PIO-transmit transaction.
old-location: serports\evtsercx2piotransmitinitializetransaction.htm
tech.root: serports
ms.assetid: 2E3652CB-24F1-4467-AF1D-CFD52392B2DB
ms.date: 04/23/2018
keywords: ["EVT_SERCX2_PIO_TRANSMIT_INITIALIZE_TRANSACTION callback function"]
ms.keywords: 2/EvtSerCx2PioTransmitInitializeTransaction, EVT_SERCX2_PIO_TRANSMIT_INITIALIZE_TRANSACTION, EVT_SERCX2_PIO_TRANSMIT_INITIALIZE_TRANSACTION callback, EvtSerCx2PioTransmitInitializeTransaction, EvtSerCx2PioTransmitInitializeTransaction callback function [Serial Ports], serports.evtsercx2piotransmitinitializetransaction
f1_keywords:
 - "sercx/EvtSerCx2PioTransmitInitializeTransaction"
 - "EvtSerCx2PioTransmitInitializeTransaction"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- 2.0\Sercx.h
api_name:
- EvtSerCx2PioTransmitInitializeTransaction
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_SERCX2_PIO_TRANSMIT_INITIALIZE_TRANSACTION callback function


## -description


The <i>EvtSerCx2PioTransmitInitializeTransaction</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to prepare the serial controller driver to perform a PIO-transmit transaction.


## -parameters




### -param PioTransmit [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a> handle to a PIO-transmit object. The serial controller driver previously called the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2piotransmitcreate">SerCx2PioTransmitCreate</a> method to create this object.


### -param Length [in]

The number of bytes to be transferred in the PIO-transmit transaction.


## -remarks



Your serial controller driver can, as an option, implement this function. If implemented, the driver registers the function in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2piotransmitcreate">SerCx2PioTransmitCreate</a> call that creates the PIO-transmit object.

Your driver should implement an <i>EvtSerCx2PioTransmitInitializeTransaction</i> function if it needs to initialize the serial controller and associated hardware in preparation for a new PIO-transmit transaction. SerCx2 calls this function, if it is implemented, before a PIO-transmit transaction starts. In response to this call, the serial controller driver must call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2piotransmitinitializetransactioncomplete">SerCx2PioTransmitInitializeTransactionComplete</a> method to notify SerCx2 after the initialization is finished.

For more information, see <a href="https://docs.microsoft.com/previous-versions/dn265336(v=vs.85)">SerCx2 PIO-Transmit Transactions</a>.


#### Examples

To define an <i>EvtSerCx2PioTransmitInitializeTransaction</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSerCx2PioTransmitInitializeTransaction</i> callback function that is named <code>MyPioTransmitInitializeTransaction</code>, use the <b>EVT_SERCX2_PIO_TRANSMIT_INITIALIZE_TRANSACTION</b> function type, as shown in this code example:

<div class="code"><span codelanguage="cpp"><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SERCX2_PIO_TRANSMIT_INITIALIZE_TRANSACTION  MyPioTransmitInitializeTransaction;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage="cpp"><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
  MyPioTransmitInitializeTransaction(
    SERCX2PIOTRANSMIT  PioTransmit,
    ULONG  Length
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_SERCX2_PIO_TRANSMIT_INITIALIZE_TRANSACTION</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_PIO_TRANSMIT_INITIALIZE_TRANSACTION</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2piotransmitcreate">SerCx2PioTransmitCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2piotransmitinitializetransactioncomplete">SerCx2PioTransmitInitializeTransactionComplete</a>
 

 

