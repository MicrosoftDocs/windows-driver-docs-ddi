---
UID: NF:wdfdmatransaction.WdfDmaTransactionStopSystemTransfer
title: WdfDmaTransactionStopSystemTransfer function
author: windows-driver-content
description: The WdfDmaTransactionStopSystemTransfer method attempts to stop a system-mode DMA transfer after the framework has called EvtProgramDma.
old-location: wdf\wdfdmatransactionstopsystemtransfer.htm
tech.root: wdf
ms.assetid: 55674946-A2DA-4695-8673-6BF3123FB5FC
ms.date: 2/26/2018
ms.keywords: WdfDmaTransactionStopSystemTransfer, WdfDmaTransactionStopSystemTransfer method, kmdf.wdfdmatransactionstopsystemtransfer, wdf.wdfdmatransactionstopsystemtransfer, wdfdmatransaction/WdfDmaTransactionStopSystemTransfer
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
-	WdfDmaTransactionStopSystemTransfer
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDmaTransactionStopSystemTransfer function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>


   The 
  <b>WdfDmaTransactionStopSystemTransfer</b> method attempts to stop a system-mode DMA transfer after the framework has called <a href="https://msdn.microsoft.com/c01b94b2-aabf-47dd-952a-06e481579614">EvtProgramDma</a>.


## -parameters




### -param DmaTransaction [in]

A handle to an initialized DMA transaction object.


## -returns



This method does not return a value.




## -remarks



Only a driver that uses system-mode DMA should call  <b>WdfDmaTransactionStopSystemTransfer</b>.

A driver using bus-mastering  DMA is responsible for programming its own dedicated DMA controller. In the event of a request cancellation, timeout, or device error, the driver can program the DMA controller to stop transferring data.

In contrast, a driver using system-mode DMA must rely on the hardware abstraction layer (HAL) to program the shared DMA controller.  When a driver calls <b>WdfDmaTransactionStopSystemTransfer</b>, the framework notifies the HAL that the transfer must be stopped and returns immediately.

The framework next calls the driver's <a href="https://msdn.microsoft.com/C638A505-AAE1-48FC-B06B-F2F161ADC948">EvtDmaTransactionDmaTransferComplete</a> callback function, if the driver has provided one.  If not, the framework returns FALSE when the driver next calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff547039">WdfDmaTransactionDmaCompleted</a>.

If your driver calls this method on an operating system earlier than Windows 8, <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-kmdf-verifier">the framework's verifier</a> reports an error.

 For more information about system-mode DMA, see <a href="https://msdn.microsoft.com/CCC77C15-69CA-44CB-8DEB-29F3EAEA44F6">Supporting System-Mode DMA</a>.

 For more information about canceling DMA transactions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/canceling-dma-transactions">Canceling DMA Transactions</a>.


#### Examples

The following code example shows how a driver might call <b>WdfDmaTransactionStopSystemTransfer</b> from an <a href="https://msdn.microsoft.com/abe15fd9-620e-4c24-9a82-32d20a7e49cc">EvtTimerFunc</a> event callback function that it registers to be called if an I/O request times out.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
MyTimerFunc(
    __in WDFTIMER Timer
    )
{
    WDFREQUEST request = (WDFREQUEST) WdfTimerGetParentObject(Timer);
    PREQUEST_CONTEXT requestContext = GetRequestContext(request);

    //
    // Begin the completion process.  If we're the first to get here 
    // then stop the DMA transfer.  The dma completion routine will
    // take care of running down cancellation.
    //
    if (BeginCompletion(requestContext, STATUS_IO_TIMEOUT, false)) {
        WdfDmaTransactionStopSystemTransfer(requestContext-&gt;DmaTransaction);
    }
    
    AttemptRequestCompletion(requestContext, false);
}

bool
BeginCompletion(
    __in PREQUEST_CONTEXT  RequestContext,
    __in NTSTATUS          CompletionStatus,
    __in bool              ForceStatusUpdate
    )
{
    bool completionStarted;

    //
    // Grab the object lock and mark the beginning of 
    // completion.
    //
    WdfSpinLockAcquire(RequestContext-&gt;Lock);

    completionStarted = RequestContext-&gt;CompletionStarted;
    RequestContext-&gt;CompletionStarted = true;

    if ((completionStarted == false) || 
        (ForceStatusUpdate == true)) {
        RequestContext-&gt;CompletionStatus = CompletionStatus;
    }

    WdfSpinLockRelease(RequestContext-&gt;Lock);

    return !completionStarted;
}

VOID
AttemptRequestCompletion(
    __in PREQUEST_CONTEXT RequestContext,
    __in bool TransferComplete
    )
{
    LONG refCount;

    NT_ASSERTMSG("No thread has begun completion", 
                 RequestContext-&gt;CompletionStarted == true);

    if (TransferComplete) {
        //
        // Unmark the request cancelable.  If that succeeds then drop the cancel reference
        //
        if (WdfRequestUnmarkCancelable(RequestContext-&gt;Request) == STATUS_SUCCESS) {
            refCount = InterlockedDecrement(&amp;(RequestContext-&gt;CompletionRefCount));
            NT_ASSERTMSGW(L"Reference count should not have gone to zero yet",
                          refCount != 0);
        }
                
        //
        // Stop the timer if it's been started.
        //
        if (RequestContext-&gt;TimerStarted == true) {
            if (WdfTimerStop(RequestContext-&gt;Timer, FALSE) == TRUE) {
                //
                // The timer was queued but won't ever run.  Drop its 
                // reference count.
                //
                refCount = InterlockedDecrement(&amp;RequestContext-&gt;CompletionRefCount);
                NT_ASSERTMSG("Completion reference count should not reach zero until "
                             L"this routine calls AttemptRequestCompletion",
                             refCount &gt; 0);
            }
        }
    }

    //
    // Drop this caller's reference.  If that was the last one then 
    // complete the request.
    //
    refCount = InterlockedDecrement(&amp;(RequestContext-&gt;CompletionRefCount));

    if (refCount == 0) {
        NT_ASSERTMSGW(L"Execution reference was released, but execution "
                      L"path did not set a completion status for the "
                      L"request",
                      RequestContext-&gt;CompletionStatus != STATUS_PENDING);
        
        
        //
        // Timers are disposed of at passive level.  If we leave it attached to 
        // the request then we can hit a verifier issue, since the request 
        // needs to be immediately disposable at dispatch-level.
        //
        // Delete the timer now so that we can complete the request safely.
        // At this point the timer has either expired or been successfully 
        // cancelled so there's no race with the timer routine.
        //
        if (RequestContext-&gt;Timer != NULL) {
            WdfObjectDelete(RequestContext-&gt;Timer);
            RequestContext-&gt;Timer = NULL;
        }

        WdfRequestComplete(RequestContext-&gt;Request, 
                           RequestContext-&gt;CompletionStatus);
    }
}
</pre>
</td>
</tr>
</table></span></div>
The following code example shows how a driver might call <b>WdfDmaTransactionStopSystemTransfer</b> from an <a href="https://msdn.microsoft.com/db54fa76-d3e0-4f8c-aa3f-bab268dd9b4d">EvtRequestCancel</a> callback function. The driver previously called <a href="https://msdn.microsoft.com/library/windows/hardware/ff549984">WdfRequestMarkCancelableEx</a> from its I/O request handler to register the callback.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
MyRequestCancel(
    __in WDFREQUEST Request
    )
{
    PREQUEST_CONTEXT requestContext = GetRequestContext(Request);
    LONG oldValue;

    //
    // Start completion
    //

    if (BeginCompletion(requestContext, STATUS_CANCELLED, false)) {
        
        //
        // Cancel the DMA transaction.
        //
        if (WdfDmaTransactionCancel(requestContext-&gt;DmaTransaction) == TRUE) {
            //
            // The transaction was stopped before EvtProgramDma could be 
            // called.  Drop the I/O reference.
            // 
            oldValue = InterlockedDecrement(&amp;requestContext-&gt;CompletionRefCount);
            NT_ASSERTMSG("Completion reference count should not reach zero until "
                         L"this routine calls AttemptRequestCompletion",
                         oldValue &gt; 0);
            NT_ASSERTMSG("Completion status should be cancelled", 
                         requestContext-&gt;CompletionStatus == STATUS_CANCELLED);
        }
        else {
            //
            // The transaction couldn't be stopped before EvtProgramDma.
            // Stop any running system DMA transfer.
            //
            WdfDmaTransactionStopSystemTransfer(requestContext-&gt;DmaTransaction);
        }
    }

    AttemptRequestCompletion(requestContext, false);
}
</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451127">WdfDmaTransactionCancel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547027">WdfDmaTransactionCreate</a>
 

 

