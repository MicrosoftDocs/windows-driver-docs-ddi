---
UID: NC:sercx.EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_START
title: EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_START
author: windows-driver-content
description: The EvtSerCx2CustomReceiveTransactionStart event callback function is called by version 2 of the serial framework extension (SerCx2) to start a custom-receive transaction.
old-location: serports\evtsercx2customreceivetransactionstart.htm
old-project: serports
ms.assetid: F90250CC-EDBF-4DB7-B889-4BF6325FB0CD
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: serports.evtsercx2customreceivetransactionstart, EvtSerCx2CustomReceiveTransactionStart callback function [Serial Ports], EvtSerCx2CustomReceiveTransactionStart, EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_START, EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_START, 2/EvtSerCx2CustomReceiveTransactionStart
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
-	EvtSerCx2CustomReceiveTransactionStart
product: Windows
targetos: Windows
req.typenames: SENSOR_VALUE_PAIR, *PSENSOR_VALUE_PAIR
req.product: Windows 10 or later.
---

# EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_START callback


## -description


The <i>EvtSerCx2CustomReceiveTransactionStart</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to start a custom-receive transaction.


## -prototype


````
EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_START EvtSerCx2CustomReceiveTransactionStart;

VOID EvtSerCx2CustomReceiveTransactionStart(
  _In_ SERCX2CUSTOMRECEIVETRANSACTION CustomReceiveTransaction,
  _In_ WDFREQUEST                     Request,
  _In_ PMDL                           Mdl,
  _In_ ULONG                          Offset,
  _In_ ULONG                          Length
)
{ ... }
````


## -parameters




### -param CustomReceiveTransaction [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/dn265249">SERCX2CUSTOMRECEIVETRANSACTION</a> handle to a custom-receive-transaction object. The serial controller driver previously called the <a href="..\sercx\nf-sercx-sercx2customreceivetransactioncreate.md">SerCx2CustomReceiveTransactionCreate</a> method to create this object.


### -param Request [in]

A handle to the framework request object associated with the custom-receive transaction. The driver is responsible for completing this request. This request might not be the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a> request sent by the client, and thus the serial controller driver should not try to use this request to access the read buffer. This request is primarily used for cancellation, completion, and queue forwarding (if needed). To access the read buffer for the client's read request, use the <i>Mdl</i>, <i>Offset</i>, and <i>Length</i> parameters.


### -param Mdl [in]

A pointer to an <a href="..\wdm\ns-wdm-_mdl.md">MDL</a> that describes the memory pages that are spanned by the read buffer for the custom-receive transaction. The scatter/gather list for the data transfer will use the region of this memory that is specified by the <i>Offset</i> and <i>Length</i> parameters.


### -param Offset [in]

The starting offset for the data transfer. This parameter is a byte offset from the start of the buffer region described by the MDL. If the MDL specifies a total of N bytes of buffer space, possible values of <i>Offset</i> are in the range 0 to N–1.


### -param Length [in]

The size, in bytes, of the data transfer. If the MDL specifies a total of N bytes of buffer space, possible values of <i>Length</i> are in the range 1 to N–<i>Offset</i>.


## -returns


None.



## -remarks


Your serial controller driver must implement this function if it creates a custom-receive-transaction object. The driver registers the function in the <a href="..\sercx\nf-sercx-sercx2customreceivetransactioncreate.md">SerCx2CustomReceiveTransactionCreate</a> call that creates this object.

After SerCx2 calls the <i>EvtSerCx2CustomReceiveTransactionStart</i> function, the serial controller driver initiates the transaction by programming the custom data-transfer mechanism to move data from the receive FIFO in the serial controller hardware to the buffer in the read request. Unless the request can be completed immediately, before the <i>EvtSerCx2CustomReceiveTransactionStart</i> function returns, the driver must call a method such as <a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelableex.md">WdfRequestMarkCancelableEx</a> to mark the request as cancelable.

After the <i>EvtSerCx2CustomReceiveTransactionStart</i> function starts the transaction, SerCx2 periodically calls the <a href="https://msdn.microsoft.com/B0B08257-E867-4E22-949E-555AD44C2DDE">EvtSerCx2CustomReceiveTransactionQueryProgress</a> event callback function to monitor progress made by the serial controller driver in performing this transaction. After the transaction finishes and the driver completes the pending read request, SerCx2 calls the <a href="..\sercx\nc-sercx-evt_sercx2_custom_receive_transaction_cleanup.md">EvtSerCx2CustomReceiveTransactionCleanup</a> event callback function, if the driver implements this function.

If the serial controller driver implements an <a href="..\sercx\nc-sercx-evt_sercx2_custom_receive_transaction_initialize.md">EvtSerCx2CustomReceiveTransactionInitialize</a> event callback function, SerCx2 calls this function before calling the <i>EvtSerCx2CustomReceiveTransactionStart</i> function. Just before the <i>EvtSerCx2CustomReceiveTransactionStart</i> call, and after the <i>EvtSerCx2CustomReceiveTransactionInitialize</i> call returns, SerCx2 starts the timer that detects whether the read request times out. For more information, see the discussion of total time-outs in  <a href="..\ntddser\ns-ntddser-_serial_timeouts.md">SERIAL_TIMEOUTS</a>.

If the custom data-transfer mechanism is a bus-master DMA device, the <i>EvtSerCx2CustomReceiveTransactionStart</i> function can call a method such as <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioninitializeusingoffset.md">WdfDmaTransactionInitializeUsingOffset</a> to initiate a DMA transaction that uses the read buffer described by the <i>Mdl</i>, <i>Offset</i>, and <i>Length</i> parameters.

If the request object identified by the <i>Request</i> parameter contains storage for a private context, this storage might be uninitialized the first time the serial controller driver accesses the context. On first access, the driver typically should fill the context with zeros, and then, if needed, explicitly set any fields in the context that require nonzero initial values.

For more information, see <a href="https://msdn.microsoft.com/29849A8C-6656-444C-BE91-405A4BA2D5B0">SerCx2 Custom-Receive Transactions</a>.



## -see-also

<a href="..\ntddser\ns-ntddser-_serial_timeouts.md">SERIAL_TIMEOUTS</a>

<a href="..\wdm\ns-wdm-_mdl.md">MDL</a>

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioninitializeusingoffset.md">WdfDmaTransactionInitializeUsingOffset</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/dn265249">SERCX2CUSTOMRECEIVETRANSACTION</a>

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelableex.md">WdfRequestMarkCancelableEx</a>

<a href="..\sercx\nf-sercx-sercx2customreceivetransactioncreate.md">SerCx2CustomReceiveTransactionCreate</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX2_CUSTOM_RECEIVE_TRANSACTION_START callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

