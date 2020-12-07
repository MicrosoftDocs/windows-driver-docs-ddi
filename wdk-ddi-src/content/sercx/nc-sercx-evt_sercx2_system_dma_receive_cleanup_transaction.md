---
UID: NC:sercx.EVT_SERCX2_SYSTEM_DMA_RECEIVE_CLEANUP_TRANSACTION
title: EVT_SERCX2_SYSTEM_DMA_RECEIVE_CLEANUP_TRANSACTION (sercx.h)
description: The EvtSerCx2SystemDmaReceiveCleanupTransaction event callback function is called by version 2 of the serial framework extension (SerCx2) to clean up the serial controller state after a system-DMA-receive transaction ends.
old-location: serports\evtsercx2systemdmareceivecleanuptransaction.htm
tech.root: serports
ms.date: 04/23/2018
keywords: ["EVT_SERCX2_SYSTEM_DMA_RECEIVE_CLEANUP_TRANSACTION callback function"]
ms.keywords: 2/EvtSerCx2SystemDmaReceiveCleanupTransaction, EVT_SERCX2_SYSTEM_DMA_RECEIVE_CLEANUP_TRANSACTION, EVT_SERCX2_SYSTEM_DMA_RECEIVE_CLEANUP_TRANSACTION callback, EvtSerCx2SystemDmaReceiveCleanupTransaction, EvtSerCx2SystemDmaReceiveCleanupTransaction callback function [Serial Ports], serports.evtsercx2systemdmareceivecleanuptransaction
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
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_SERCX2_SYSTEM_DMA_RECEIVE_CLEANUP_TRANSACTION
 - sercx/EVT_SERCX2_SYSTEM_DMA_RECEIVE_CLEANUP_TRANSACTION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - 2.0\Sercx.h
api_name:
 - EvtSerCx2SystemDmaReceiveCleanupTransaction
---

# EVT_SERCX2_SYSTEM_DMA_RECEIVE_CLEANUP_TRANSACTION callback function


## -description

The <i>EvtSerCx2SystemDmaReceiveCleanupTransaction</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to clean up the serial controller state after a system-DMA-receive transaction ends.

## -parameters

### -param SystemDmaReceive 

[in]
A <a href="/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMARECEIVE</a> handle to a system-DMA-receive object. The serial controller driver previously called the <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmareceivecreate">SerCx2SystemDmaReceiveCreate</a> method to create this object.

## -remarks

Your serial controller driver can, as an option, implement this function. If implemented, the driver registers the function in the <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmareceivecreate">SerCx2SystemDmaReceiveCreate</a> call that creates the system-DMA-receive object.

Your serial controller driver should implement an <i>EvtSerCx2SystemDmaReceiveCleanupTransaction</i> function if it needs to clean up the serial controller state at the end of a system-DMA-receive transaction. SerCx2 calls this function, if it is implemented, after a system-DMA-receive transaction ends. In response to the <i>EvtSerCx2SystemDmaReceiveCleanupTransaction</i> call, the serial controller driver must call the <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmareceivecleanuptransactioncomplete">SerCx2SystemDmaReceiveCleanupTransactionComplete</a> method to notify SerCx2 after the clean-up work is done.

For more information, see <a href="/previous-versions/dn265343(v=vs.85)">SerCx2 System-DMA-Receive Transactions</a>.


#### Examples

To define an <i>EvtSerCx2SystemDmaReceiveCleanupTransaction</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSerCx2SystemDmaReceiveCleanupTransaction</i> callback function that is named <code>MySystemDmaReceiveCleanupTransaction</code>, use the <b>EVT_SERCX2_SYSTEM_DMA_RECEIVE_CLEANUP_TRANSACTION</b> function type, as shown in this code example:


```cpp
EVT_SERCX2_SYSTEM_DMA_RECEIVE_CLEANUP_TRANSACTION  MySystemDmaReceiveCleanupTransaction;
```

Then, implement your callback function as follows:


```cpp
_Use_decl_annotations_
VOID
  MySystemDmaReceiveCleanupTransaction(
    SERCX2SYSTEMDMARECEIVE  SystemDmaReceive
    )
  {...}
```

The <b>EVT_SERCX2_SYSTEM_DMA_RECEIVE_CLEANUP_TRANSACTION</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_SYSTEM_DMA_RECEIVE_CLEANUP_TRANSACTION</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMARECEIVE</a>



<a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmareceivecleanuptransactioncomplete">SerCx2SystemDmaReceiveCleanupTransactionComplete</a>



<a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmareceivecreate">SerCx2SystemDmaReceiveCreate</a>
