---
UID: NF:wdfrequest.WdfRequestComplete
title: WdfRequestComplete function (wdfrequest.h)
description: The WdfRequestComplete method completes a specified I/O request and supplies a completion status.
old-location: wdf\wdfrequestcomplete.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WdfRequestComplete function"]
ms.keywords: DFRequestObjectRef_e723fb4c-f8f2-4eb9-9152-7f7ac74329df.xml, WdfRequestComplete, WdfRequestComplete method, kmdf.wdfrequestcomplete, wdf.wdfrequestcomplete, wdfrequest/WdfRequestComplete
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: BufAfterReqCompletedIntIoctl, BufAfterReqCompletedIntIoctlA, BufAfterReqCompletedIoctl, BufAfterReqCompletedIoctlA, BufAfterReqCompletedRead, BufAfterReqCompletedReadA, BufAfterReqCompletedWrite, BufAfterReqCompletedWriteA, CompleteCanceledReq, DeferredRequestCompleted, DoubleCompletion, DoubleCompletionLocal, DriverCreate, EvtIoStopCancel, EvtIoStopCompleteOrStopAck, EvtSurpriseRemoveNoRequestComplete, InvalidReqAccess, KmdfIrql, KmdfIrql2, MarkCancOnCancReqLocal, MdlAfterReqCompletedIntIoctl, MdlAfterReqCompletedIntIoctlA, MdlAfterReqCompletedIoctl, MdlAfterReqCompletedIoctlA, MdlAfterReqCompletedRead, MdlAfterReqCompletedReadA, MdlAfterReqCompletedWrite, MdlAfterReqCompletedWriteA, MemAfterReqCompletedIntIoctl, MemAfterReqCompletedIntIoctlA, MemAfterReqCompletedIoctl, MemAfterReqCompletedIoctlA, MemAfterReqCompletedRead, MemAfterReqCompletedReadA, MemAfterReqCompletedWrite, MemAfterReqCompletedWriteA, NoCancelFromEvtSurpriseRemove, ReqDelete, ReqIsCancOnCancReq, ReqNotCanceledLocal, ReqSendFail, RequestCompleted, RequestCompletedLocal
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfRequestComplete
 - wdfrequest/WdfRequestComplete
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
 - WUDFx02000.dll
 - WUDFx02000.dll.dll
api_name:
 - WdfRequestComplete
---

# WdfRequestComplete function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfRequestComplete</b> method completes a specified I/O request and supplies a completion status.

## -parameters

### -param Request [in]


A handle to the framework request object that represents the I/O request that is being completed.

### -param Status [in]


An <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS value</a> that represents the completion status of the request. Valid status values include, but are not limited to, the following:





#### STATUS_SUCCESS

The driver is successfully completing the request.



#### STATUS_CANCELLED

The driver is canceling the request.



#### STATUS_UNSUCCESSFUL

The driver has encountered an error while processing the request.

## -remarks

A bug check occurs if the driver supplies an invalid object handle.



After a driver calls <b>WdfRequestComplete</b>, higher-level drivers on the driver stack can call <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestgetstatus">WdfRequestGetStatus</a> to obtain the completion status value that was specified for the <i>Status</i> parameter. Typically, drivers call <b>WdfRequestGetStatus</b> from within a <a href="/windows-hardware/drivers/ddi/wdfrequest/nc-wdfrequest-evt_wdf_request_completion_routine">CompletionRoutine</a> callback function.

After a call to <b>WdfRequestComplete</b> returns, the request handle is no longer valid unless the driver has called <a href="/windows-hardware/drivers/wdf/wdfobjectreference">WdfObjectReference</a> to add one or more additional reference counts to the request object.  Note that after <b>WdfRequestComplete</b> returns, the driver must not attempt to access the associated WDM IRP structure, even if it has called <b>WdfObjectReference</b>. This requirement extends to accessing the associated WDM IRP structure by calling methods on the WDFREQUEST, like <b>WdfRequestRetrieveOutputBuffer</b> or <b>WdfRequestRetrieveInputBuffer</b>.

After a driver calls <b>WdfRequestComplete</b>, the framework calls the driver's <a href="/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_cleanup">EvtCleanupCallback</a> function for the request, if the driver has supplied one.

Instead of calling <b>WdfRequestComplete</b>, the driver can call <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcompletewithinformation">WdfRequestCompleteWithInformation</a> or <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcompletewithpriorityboost">WdfRequestCompleteWithPriorityBoost</a>. See the Remarks of <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcompletewithinformation">WdfRequestCompleteWithInformation</a> for more information.

When your driver calls <b>WdfRequestComplete</b>, the framework supplies a default value that the system uses to boost the run-time priority of the thread that requested the I/O operation. For information about default priority boost values, see <a href="/windows-hardware/drivers/wdf/specifying-priority-boosts-when-completing-i-o-requests">Specifying Priority Boosts When Completing I/O Requests</a>. Your driver can call <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcompletewithpriorityboost">WdfRequestCompleteWithPriorityBoost</a> to override the default priority boost value.

For more information about calling <b>WdfRequestComplete</b>, see <a href="/windows-hardware/drivers/wdf/completing-i-o-requests">Completing I/O Requests</a>.


#### Examples

The following code example is a section of a request handler. The request handler accepts only read and write requests, and it completes a each request with an error status if the request type is not read or write.

```cpp
VOID
MyEvtIoDefault(
    IN WDFQUEUE  Queue,
    IN WDFREQUEST  Request
    )
{
    WDF_REQUEST_PARAMETERS  params;
    WDF_DMA_DIRECTION  direction;

...
    WDF_REQUEST_PARAMETERS_INIT(&params);

    WdfRequestGetParameters(
                            Request,
                            &params
                            );

    //
    // Validate and gather parameters.
    //
    switch (params.Type) {
        case WdfRequestTypeRead:
            length = params.Parameters.Read.Length;
            direction = WdfDmaDirectionReadFromDevice;
            break;
        case WdfRequestTypeWrite:
            length = params.Parameters.Write.Length;
            direction = WdfDmaDirectionWriteToDevice;
            break;
        default:
            WdfRequestComplete(
                               Request,
                               STATUS_INVALID_DEVICE_REQUEST
                               );
            return;
    }
...
}
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_parameters">WDF_REQUEST_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdf_request_parameters_init">WDF_REQUEST_PARAMETERS_INIT</a>



<a href="/windows-hardware/drivers/wdf/wdfobjectreference">WdfObjectReference</a>



<a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcompletewithinformation">WdfRequestCompleteWithInformation</a>



<a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcompletewithpriorityboost">WdfRequestCompleteWithPriorityBoost</a>



<a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestgetstatus">WdfRequestGetStatus</a>
