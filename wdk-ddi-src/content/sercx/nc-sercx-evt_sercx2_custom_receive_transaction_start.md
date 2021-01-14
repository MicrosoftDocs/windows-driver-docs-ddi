---
UID: NC:sercx.EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_START
title: EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_START (sercx.h)
description: The EvtSerCx2CustomReceiveTransactionStart event callback function is called by version 2 of the serial framework extension (SerCx2) to start a custom-receive transaction.
old-location: serports\evtsercx2customreceivetransactionstart.htm
tech.root: serports
ms.date: 04/23/2018
keywords: ["EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_START callback function"]
ms.keywords: 2/EvtSerCx2CustomReceiveTransactionStart, EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_START, EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_START callback, EvtSerCx2CustomReceiveTransactionStart, EvtSerCx2CustomReceiveTransactionStart callback function [Serial Ports], serports.evtsercx2customreceivetransactionstart
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
 - EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_START
 - sercx/EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_START
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - 2.0\Sercx.h
api_name:
 - EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_START
---

# EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_START callback function


## -description

The <i>EvtSerCx2CustomReceiveTransactionStart</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to start a custom-receive transaction.

## -parameters

### -param CustomReceiveTransaction 

[in]
A <a href="/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2CUSTOMRECEIVETRANSACTION</a> handle to a custom-receive-transaction object. The serial controller driver previously called the <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2customreceivetransactioncreate">SerCx2CustomReceiveTransactionCreate</a> method to create this object.

### -param Request 

[in]
A handle to the framework request object associated with the custom-receive transaction. The driver is responsible for completing this request. This request might not be the <a href="/windows-hardware/drivers/ifs/irp-mj-read">IRP_MJ_READ</a> request sent by the client, and thus the serial controller driver should not try to use this request to access the read buffer. This request is primarily used for cancellation, completion, and queue forwarding (if needed). To access the read buffer for the client's read request, use the <i>Mdl</i>, <i>Offset</i>, and <i>Length</i> parameters.

### -param Mdl 

[in]
A pointer to an <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_mdl">MDL</a> that describes the memory pages that are spanned by the read buffer for the custom-receive transaction. The scatter/gather list for the data transfer will use the region of this memory that is specified by the <i>Offset</i> and <i>Length</i> parameters.

### -param Offset 

[in]
The starting offset for the data transfer. This parameter is a byte offset from the start of the buffer region described by the MDL. If the MDL specifies a total of N bytes of buffer space, possible values of <i>Offset</i> are in the range 0 to N–1.

### -param Length 

[in]
The size, in bytes, of the data transfer. If the MDL specifies a total of N bytes of buffer space, possible values of <i>Length</i> are in the range 1 to N–<i>Offset</i>.

## -remarks

Your serial controller driver must implement this function if it creates a custom-receive-transaction object. The driver registers the function in the <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2customreceivetransactioncreate">SerCx2CustomReceiveTransactionCreate</a> call that creates this object.

After SerCx2 calls the <i>EvtSerCx2CustomReceiveTransactionStart</i> function, the serial controller driver initiates the transaction by programming the custom data-transfer mechanism to move data from the receive FIFO in the serial controller hardware to the buffer in the read request. Unless the request can be completed immediately, before the <i>EvtSerCx2CustomReceiveTransactionStart</i> function returns, the driver must call a method such as <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestmarkcancelableex">WdfRequestMarkCancelableEx</a> to mark the request as cancelable.

After the <i>EvtSerCx2CustomReceiveTransactionStart</i> function starts the transaction, SerCx2 periodically calls the <a href="/previous-versions/windows/hardware/drivers/dn265203(v=vs.85)">EvtSerCx2CustomReceiveTransactionQueryProgress</a> event callback function to monitor progress made by the serial controller driver in performing this transaction. After the transaction finishes and the driver completes the pending read request, SerCx2 calls the <a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_custom_receive_transaction_cleanup">EvtSerCx2CustomReceiveTransactionCleanup</a> event callback function, if the driver implements this function.

If the serial controller driver implements an <a href="/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_custom_receive_transaction_initialize">EvtSerCx2CustomReceiveTransactionInitialize</a> event callback function, SerCx2 calls this function before calling the <i>EvtSerCx2CustomReceiveTransactionStart</i> function. Just before the <i>EvtSerCx2CustomReceiveTransactionStart</i> call, and after the <i>EvtSerCx2CustomReceiveTransactionInitialize</i> call returns, SerCx2 starts the timer that detects whether the read request times out. For more information, see the discussion of total time-outs in  <a href="/windows-hardware/drivers/ddi/ntddser/ns-ntddser-_serial_timeouts">SERIAL_TIMEOUTS</a>.

If the custom data-transfer mechanism is a bus-master DMA device, the <i>EvtSerCx2CustomReceiveTransactionStart</i> function can call a method such as <a href="/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioninitializeusingoffset">WdfDmaTransactionInitializeUsingOffset</a> to initiate a DMA transaction that uses the read buffer described by the <i>Mdl</i>, <i>Offset</i>, and <i>Length</i> parameters.

If the request object identified by the <i>Request</i> parameter contains storage for a private context, this storage might be uninitialized the first time the serial controller driver accesses the context. On first access, the driver typically should fill the context with zeros, and then, if needed, explicitly set any fields in the context that require nonzero initial values.

For more information, see <a href="/previous-versions/dn265314(v=vs.85)">SerCx2 Custom-Receive Transactions</a>.


#### Examples

To define an <i>EvtSerCx2CustomReceiveTransactionStart</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSerCx2CustomReceiveTransactionStart</i> callback function that is named <code>MyCustomReceiveTransactionStart</code>, use the <b>EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_START</b> function type, as shown in this code example:


```cpp
EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_START  MyCustomReceiveTransactionStart;
```

Then, implement your callback function as follows:


```cpp
_Use_decl_annotations_
VOID
  MyCustomReceiveTransactionStart(
    SERCX2CUSTOMRECEIVETRANSACTION  CustomReceiveTransaction,
    WDFREQUEST  Request,
    PMDL  Mdl,
    ULONG  Offset,
    ULONG  Length
    )
  {...}
```

The <b>EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_START</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_START</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ifs/irp-mj-read">IRP_MJ_READ</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_mdl">MDL</a>



<a href="/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2CUSTOMRECEIVETRANSACTION</a>



<a href="/windows-hardware/drivers/ddi/ntddser/ns-ntddser-_serial_timeouts">SERIAL_TIMEOUTS</a>



<a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2customreceivetransactioncreate">SerCx2CustomReceiveTransactionCreate</a>



<a href="/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioninitializeusingoffset">WdfDmaTransactionInitializeUsingOffset</a>



<a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestmarkcancelableex">WdfRequestMarkCancelableEx</a>

