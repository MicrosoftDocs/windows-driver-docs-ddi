---
UID: NF:wdfdmatransaction.WdfDmaTransactionCancel
title: WdfDmaTransactionCancel function
author: windows-driver-content
description: The WdfDmaTransactionCancel method attempts to cancel a DMA transaction that is waiting for the allocation of map registers.
old-location: wdf\wdfdmatransactioncancel.htm
old-project: wdf
ms.assetid: A0EB188E-D5C7-4C7B-A462-2C3792825FD8
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WdfDmaTransactionCancel, WdfDmaTransactionCancel method, kmdf.wdfdmatransactioncancel, wdf.wdfdmatransactioncancel, wdfdmatransaction/WdfDmaTransactionCancel
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdmatransaction.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfDmaTransactionCancel
product: Windows
targetos: Windows
req.typenames: WDF_DMA_SYSTEM_PROFILE_CONFIG, *PWDF_DMA_SYSTEM_PROFILE_CONFIG
req.product: Windows 10 or later.
---

# WdfDmaTransactionCancel function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDmaTransactionCancel</b> method attempts to cancel a DMA transaction that is waiting for the allocation of map registers.


## -syntax


````
BOOLEAN WdfDmaTransactionCancel(
  _In_ WDFDMATRANSACTION DmaTransaction
);
````


## -parameters




### -param DmaTransaction [in]

A handle to the DMA transaction object that represents the transaction that is being canceled. This transaction must have already been initialized by the driver. 


## -returns



<b>WdfDmaTransactionCancel</b> returns TRUE if the framework successfully cancels map register allocation.  In this case, no transfers are completed, and the framework makes no additional DMA callbacks on the transaction until it is reinitiated.

 The method returns FALSE if another thread is already processing this transaction, or if the driver has not yet called <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionexecute.md">WdfDmaTransactionExecute</a>.  In the first case, the framework is currently calling or will call <a href="https://msdn.microsoft.com/c01b94b2-aabf-47dd-952a-06e481579614">EvtProgramDma</a> or <a href="..\wdfdmatransaction\nc-wdfdmatransaction-evt_wdf_reserve_dma.md">EvtReserveDma</a>. At this point, a driver that specified a system-mode DMA profile might call <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionstopsystemtransfer.md">WdfDmaTransactionStopSystemTransfer</a>.

The method also returns FALSE if called with a transaction that was allocated from a DMA version 2 enabler.




## -remarks



The driver might call <b>WdfDmaTransactionCancel</b> from an <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_cancel.md">EvtRequestCancel</a> event callback function that it supplies in a call to <a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelableex.md">WdfRequestMarkCancelableEx</a>. For a code example that shows how to do this, see <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionstopsystemtransfer.md">WdfDmaTransactionStopSystemTransfer</a>.

The driver might also call <b>WdfDmaTransactionCancel</b> from an <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_canceled_on_queue.md">EvtIoCanceledOnQueue</a> event callback function.



Cancellation can only succeed if the call to <b>WdfDmaTransactionCancel</b> occurs after the call to <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionexecute.md">WdfDmaTransactionExecute</a>, but before the <b>WdfDmaTransactionExecute</b> method has started the DMA allocation.  For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/canceling-dma-transactions">Canceling DMA Transactions</a>.

The driver must call <b>WdfDmaTransactionCancel</b> after calling <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioninitialize.md">WdfDmaTransactionInitialize</a>, but before calling <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionrelease.md">WdfDmaTransactionRelease</a> or <a href="..\wdfobject\nf-wdfobject-wdfobjectdelete.md">WdfObjectDelete</a> to delete the transaction object.

 Do not call <b>WdfDmaTransactionCancel</b> after the framework has called <a href="https://msdn.microsoft.com/c01b94b2-aabf-47dd-952a-06e481579614">EvtProgramDma</a> or <a href="..\wdfdmatransaction\nc-wdfdmatransaction-evt_wdf_reserve_dma.md">EvtReserveDma</a>.

A driver must request use of DMA version 3 prior to calling  <b>WdfDmaTransactionCancel</b>. 
 To select DMA version 3, set the <b>WdmDmaVersionOverride</b> member of <a href="..\wdfdmaenabler\ns-wdfdmaenabler-_wdf_dma_enabler_config.md">WDF_DMA_ENABLER_CONFIG</a> to 3.

 If a driver calls <b>WdfDmaTransactionCancel</b> on a transaction that was allocated from a DMA version 2 enabler, the framework generates a verifier error and <b>WdfDmaTransactionCancel</b> returns FALSE. In this case, no attempt is made to cancel the transaction.




## -see-also

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionstopsystemtransfer.md">WdfDmaTransactionStopSystemTransfer</a>



<a href="https://msdn.microsoft.com/c01b94b2-aabf-47dd-952a-06e481579614">EvtProgramDma</a>



<a href="..\wdfdmatransaction\nc-wdfdmatransaction-evt_wdf_reserve_dma.md">EvtReserveDma</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDmaTransactionCancel method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

