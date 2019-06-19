---
UID: NF:wdfrequest.WdfRequestComplete
title: WdfRequestComplete function (wdfrequest.h)
description: The WdfRequestComplete method completes a specified I/O request and supplies a completion status.
old-location: wdf\wdfrequestcomplete.htm
tech.root: wdf
ms.assetid: cb5bfd4f-e45a-4894-acb4-0ece2de91510
ms.date: 02/26/2018
ms.keywords: DFRequestObjectRef_e723fb4c-f8f2-4eb9-9152-7f7ac74329df.xml, WdfRequestComplete, WdfRequestComplete method, kmdf.wdfrequestcomplete, wdf.wdfrequestcomplete, wdfrequest/WdfRequestComplete
ms.topic: function
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
req.irql: "<=DISPATCH_LEVEL"
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfRequestComplete function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfRequestComplete</b> method completes a specified I/O request and supplies a completion status.


## -parameters




### -param Request [in]

A handle to the framework request object that represents the I/O request that is being completed.


### -param Status [in]

An <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS value</a> that represents the completion status of the request. Valid status values include, but are not limited to, the following:





#### STATUS_SUCCESS

The driver is successfully completing the request.



#### STATUS_CANCELLED

The driver is canceling the request.



#### STATUS_UNSUCCESSFUL

The driver has encountered an error while processing the request.


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



After a driver calls <b>WdfRequestComplete</b>, higher-level drivers on the driver stack can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549974">WdfRequestGetStatus</a> to obtain the completion status value that was specified for the <i>Status</i> parameter. Typically, drivers call <b>WdfRequestGetStatus</b> from within a <a href="https://msdn.microsoft.com/7d3eb4d6-9fc7-4924-9b95-f5824713049b">CompletionRoutine</a> callback function.

After a call to <b>WdfRequestComplete</b> returns, the request handle is no longer valid unless the driver has called <a href="https://msdn.microsoft.com/library/windows/hardware/ff548758">WdfObjectReference</a> to add one or more additional reference counts to the request object.  Note that after <b>WdfRequestComplete</b> returns, the driver must not attempt to access the associated WDM IRP structure, even if it has called <b>WdfObjectReference</b>.



After a driver calls <b>WdfRequestComplete</b>, the framework calls the driver's <a href="https://msdn.microsoft.com/aba2efca-7d1f-4594-af65-13356f0e3f8b">EvtCleanupCallback</a> function for the request, if the driver has supplied one.

Instead of calling <b>WdfRequestComplete</b>, the driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549948">WdfRequestCompleteWithInformation</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff549949">WdfRequestCompleteWithPriorityBoost</a>.

When your driver calls <b>WdfRequestComplete</b>, the framework supplies a default value that the system uses to boost the run-time priority of the thread that requested the I/O operation. For information about default priority boost values, see <a href="https://msdn.microsoft.com/9a501ca1-58c9-4458-b202-9581f8ce5e5f">Specifying Priority Boosts When Completing I/O Requests</a>. Your driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549949">WdfRequestCompleteWithPriorityBoost</a> to override the default priority boost value.

For more information about calling <b>WdfRequestComplete</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/completing-i-o-requests">Completing I/O Requests</a>.


#### Examples

The following code example is a section of a request handler. The request handler accepts only read and write requests, and it completes a each request with an error status if the request type is not read or write.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
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
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552472">WDF_REQUEST_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552476">WDF_REQUEST_PARAMETERS_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548758">WdfObjectReference</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549948">WdfRequestCompleteWithInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549949">WdfRequestCompleteWithPriorityBoost</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549974">WdfRequestGetStatus</a>
 

 

