---
UID: NF:wdfdmatransaction.WdfDmaTransactionStopSystemTransfer
title: WdfDmaTransactionStopSystemTransfer function
author: windows-driver-content
description: The WdfDmaTransactionStopSystemTransfer method attempts to stop a system-mode DMA transfer after the framework has called EvtProgramDma.
old-location: wdf\wdfdmatransactionstopsystemtransfer.htm
old-project: wdf
ms.assetid: 55674946-A2DA-4695-8673-6BF3123FB5FC
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , D, S, T, W, WdfDmaTransactionStopSystemTransfer, WdfDmaTransactionStopSystemTransfer method, a, c, d, e, f, i, kmdf.wdfdmatransactionstopsystemtransfer, m, n, o, p, r, s, t, wdf.wdfdmatransactionstopsystemtransfer, wdfdmatransaction/WdfDmaTransactionStopSystemTransfer, y"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfDmaTransactionStopSystemTransfer
product: Windows
targetos: Windows
req.typenames: WDF_DMA_SYSTEM_PROFILE_CONFIG, *PWDF_DMA_SYSTEM_PROFILE_CONFIG
req.product: Windows 10 or later.
---

# WdfDmaTransactionStopSystemTransfer function


## -description


<p class="CCE_Message">[Applies to KMDF only]


   The 
  <b>WdfDmaTransactionStopSystemTransfer</b> method attempts to stop a system-mode DMA transfer after the framework has called <a href="https://msdn.microsoft.com/c01b94b2-aabf-47dd-952a-06e481579614">EvtProgramDma</a>.


## -syntax


````
void WdfDmaTransactionStopSystemTransfer(
  _In_ WDFDMATRANSACTION DmaTransaction
);
````


## -parameters




### -param DmaTransaction [in]

A handle to an initialized DMA transaction object.


## -returns



This method does not return a value.




## -remarks



Only a driver that uses system-mode DMA should call  <b>WdfDmaTransactionStopSystemTransfer</b>.

A driver using bus-mastering  DMA is responsible for programming its own dedicated DMA controller. In the event of a request cancellation, timeout, or device error, the driver can program the DMA controller to stop transferring data.

In contrast, a driver using system-mode DMA must rely on the hardware abstraction layer (HAL) to program the shared DMA controller.  When a driver calls <b>WdfDmaTransactionStopSystemTransfer</b>, the framework notifies the HAL that the transfer must be stopped and returns immediately.

The framework next calls the driver's <a href="..\wdfdmatransaction\nc-wdfdmatransaction-evt_wdf_dma_transaction_dma_transfer_complete.md">EvtDmaTransactionDmaTransferComplete</a> callback function, if the driver has provided one.  If not, the framework returns FALSE when the driver next calls <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactiondmacompleted.md">WdfDmaTransactionDmaCompleted</a>.

If your driver calls this method on an operating system earlier than Windows 8, <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-kmdf-verifier">the framework's verifier</a> reports an error.

 For more information about system-mode DMA, see <a href="https://msdn.microsoft.com/CCC77C15-69CA-44CB-8DEB-29F3EAEA44F6">Supporting System-Mode DMA</a>.

 For more information about canceling DMA transactions, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/canceling-dma-transactions">Canceling DMA Transactions</a>.


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
The following code example shows how a driver might call <b>WdfDmaTransactionStopSystemTransfer</b> from an <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_cancel.md">EvtRequestCancel</a> callback function. The driver previously called <a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelableex.md">WdfRequestMarkCancelableEx</a> from its I/O request handler to register the callback.

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

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioncreate.md">WdfDmaTransactionCreate</a>



<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioncancel.md">WdfDmaTransactionCancel</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDmaTransactionStopSystemTransfer method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

