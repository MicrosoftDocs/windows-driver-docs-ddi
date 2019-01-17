---
UID: NF:wdfdmatransaction.WdfDmaTransactionCancel
title: WdfDmaTransactionCancel function
description: The WdfDmaTransactionCancel method attempts to cancel a DMA transaction that is waiting for the allocation of map registers.
old-location: wdf\wdfdmatransactioncancel.htm
tech.root: wdf
ms.assetid: A0EB188E-D5C7-4C7B-A462-2C3792825FD8
ms.date: 02/26/2018
ms.keywords: WdfDmaTransactionCancel, WdfDmaTransactionCancel method, kmdf.wdfdmatransactioncancel, wdf.wdfdmatransactioncancel, wdfdmatransaction/WdfDmaTransactionCancel
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDmaTransactionCancel function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDmaTransactionCancel</b> method attempts to cancel a DMA transaction that is waiting for the allocation of map registers.


## -parameters




### -param DmaTransaction [in]

A handle to the DMA transaction object that represents the transaction that is being canceled. This transaction must have already been initialized by the driver. 


## -returns



<b>WdfDmaTransactionCancel</b> returns TRUE if the framework successfully cancels map register allocation.  In this case, no transfers are completed, and the framework makes no additional DMA callbacks on the transaction until it is reinitiated.

 The method returns FALSE if another thread is already processing this transaction, or if the driver has not yet called <a href="https://msdn.microsoft.com/library/windows/hardware/ff547062">WdfDmaTransactionExecute</a>.  In the first case, the framework is currently calling or will call <a href="https://msdn.microsoft.com/c01b94b2-aabf-47dd-952a-06e481579614">EvtProgramDma</a> or <a href="https://msdn.microsoft.com/3663EF19-5F16-43D1-BFBC-28280E28D4DE">EvtReserveDma</a>. At this point, a driver that specified a system-mode DMA profile might call <a href="https://msdn.microsoft.com/library/windows/hardware/hh439264">WdfDmaTransactionStopSystemTransfer</a>.

The method also returns FALSE if called with a transaction that was allocated from a DMA version 2 enabler.




## -remarks



The driver might call <b>WdfDmaTransactionCancel</b> from an <a href="https://msdn.microsoft.com/db54fa76-d3e0-4f8c-aa3f-bab268dd9b4d">EvtRequestCancel</a> event callback function that it supplies in a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff549984">WdfRequestMarkCancelableEx</a>. For a code example that shows how to do this, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh439264">WdfDmaTransactionStopSystemTransfer</a>.

The driver might also call <b>WdfDmaTransactionCancel</b> from an <a href="https://msdn.microsoft.com/1b938ee8-a5f3-4a1e-9beb-231d88aa5848">EvtIoCanceledOnQueue</a> event callback function.



Cancellation can only succeed if the call to <b>WdfDmaTransactionCancel</b> occurs after the call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff547062">WdfDmaTransactionExecute</a>, but before the <b>WdfDmaTransactionExecute</b> method has started the DMA allocation.  For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/canceling-dma-transactions">Canceling DMA Transactions</a>.

The driver must call <b>WdfDmaTransactionCancel</b> after calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff547099">WdfDmaTransactionInitialize</a>, but before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff547114">WdfDmaTransactionRelease</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548734">WdfObjectDelete</a> to delete the transaction object.

 Do not call <b>WdfDmaTransactionCancel</b> after the framework has called <a href="https://msdn.microsoft.com/c01b94b2-aabf-47dd-952a-06e481579614">EvtProgramDma</a> or <a href="https://msdn.microsoft.com/3663EF19-5F16-43D1-BFBC-28280E28D4DE">EvtReserveDma</a>.

A driver must request use of DMA version 3 prior to calling  <b>WdfDmaTransactionCancel</b>. 
 To select DMA version 3, set the <b>WdmDmaVersionOverride</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff551290">WDF_DMA_ENABLER_CONFIG</a> to 3.

 If a driver calls <b>WdfDmaTransactionCancel</b> on a transaction that was allocated from a DMA version 2 enabler, the framework generates a verifier error and <b>WdfDmaTransactionCancel</b> returns FALSE. In this case, no attempt is made to cancel the transaction.




## -see-also




<a href="https://msdn.microsoft.com/c01b94b2-aabf-47dd-952a-06e481579614">EvtProgramDma</a>



<a href="https://msdn.microsoft.com/3663EF19-5F16-43D1-BFBC-28280E28D4DE">EvtReserveDma</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439264">WdfDmaTransactionStopSystemTransfer</a>
 

 

