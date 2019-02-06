---
UID: NF:wdfrequest.WdfRequestCompleteWithPriorityBoost
title: WdfRequestCompleteWithPriorityBoost function (wdfrequest.h)
description: The WdfRequestCompleteWithPriorityBoost method completes a specified I/O request and supplies a completion status. It also specifies a value that the system can use to boost the run-time priority of the thread that requested the I/O operation.
old-location: wdf\wdfrequestcompletewithpriorityboost.htm
tech.root: wdf
ms.assetid: c09ea33d-a20e-4535-8b5c-4645a30841a7
ms.date: 02/26/2018
ms.keywords: DFRequestObjectRef_a396672f-9267-489a-af15-44b4b01831b2.xml, WdfRequestCompleteWithPriorityBoost, WdfRequestCompleteWithPriorityBoost method, kmdf.wdfrequestcompletewithpriorityboost, wdf.wdfrequestcompletewithpriorityboost, wdfrequest/WdfRequestCompleteWithPriorityBoost
ms.topic: function
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: BufAfterReqCompletedIntIoctl, BufAfterReqCompletedIntIoctlA, BufAfterReqCompletedIoctl, BufAfterReqCompletedIoctlA, BufAfterReqCompletedRead, BufAfterReqCompletedReadA, BufAfterReqCompletedWrite, BufAfterReqCompletedWriteA, CompleteCanceledReq, DeferredRequestCompleted, DoubleCompletion, DoubleCompletionLocal, DriverCreate, EvtIoStopCancel, EvtIoStopCompleteOrStopAck, EvtSurpriseRemoveNoRequestComplete, InvalidReqAccess, KmdfIrql, KmdfIrql2, MarkCancOnCancReqLocal, MdlAfterReqCompletedIntIoctl, MdlAfterReqCompletedIntIoctlA, MdlAfterReqCompletedIoctl, MdlAfterReqCompletedIoctlA, MdlAfterReqCompletedRead, MdlAfterReqCompletedReadA, MdlAfterReqCompletedWrite, MdlAfterReqCompletedWriteA, MemAfterReqCompletedIntIoctl, MemAfterReqCompletedIntIoctlA, MemAfterReqCompletedIoctl, MemAfterReqCompletedIoctlA, MemAfterReqCompletedRead, MemAfterReqCompletedReadA, MemAfterReqCompletedWrite, MemAfterReqCompletedWriteA, NoCancelFromEvtSurpriseRemove, ReqDelete, ReqIsCancOnCancReq, ReqNotCanceledLocal, ReqSendFail, RequestCompleted, RequestCompletedLocal
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
-	WdfRequestCompleteWithPriorityBoost
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfRequestCompleteWithPriorityBoost function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfRequestCompleteWithPriorityBoost</b> method completes a specified I/O request and supplies a completion status. It also specifies a value that the system can use to boost the run-time priority of the thread that requested the I/O operation.


## -parameters




### -param Request [in]

A handle to the framework request object that represents the I/O request that is being completed.


### -param Status [in]

An <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS value</a> that represents the completion status of the request. Valid status values include, but are not limited to, the following:





#### STATUS_SUCCESS

The driver successfully completed the request.



#### STATUS_CANCELLED

The driver canceled the request.



#### STATUS_UNSUCCESSFUL

The driver encountered an error while processing the request.


### -param PriorityBoost [in]

A system-defined constant value by which to increment the run-time priority of the original thread that requested the operation. Constant values are device-type-specific and are defined in <i>Wdm.h</i>. The format for the constant names is <i>XXX</i>_INCREMENT. For more information about priority boost values, see <a href="https://msdn.microsoft.com/9a501ca1-58c9-4458-b202-9581f8ce5e5f">Specifying Priority Boosts When Completing I/O Requests</a>.


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Your driver should call <b>WdfRequestCompleteWithPriorityBoost</b> if you want to override the default priority boost that the framework provides. For example, the driver might set the priority boost to IO_NO_INCREMENT if it was able to complete the request quickly, perhaps because it detected an error. 

After a call to <b>WdfRequestCompleteWithPriorityBoost</b> returns, the request handle is no longer valid unless the driver has called <a href="https://msdn.microsoft.com/library/windows/hardware/ff548758">WdfObjectReference</a> to add one or more additional reference counts to the request object. Note that after <b>WdfRequestCompleteWithPriorityBoost</b> returns, the driver must not attempt to access the associated WDM IRP structure, even if it has called <b>WdfObjectReference</b>.

For more information about calling <b>WdfRequestCompleteWithPriorityBoost</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/completing-i-o-requests">Completing I/O Requests</a>.


#### Examples

The following code example shows how the example at <a href="https://msdn.microsoft.com/library/windows/hardware/ff549945">WdfRequestComplete</a> can use <b>WdfRequestCompleteWithPriorityBoost</b> instead of <b>WdfRequestComplete</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>switch (params.Type) {
    case WdfRequestTypeRead:
        length = params.Parameters.Read.Length;
        direction = WdfDmaDirectionReadFromDevice;
        break;
    case WdfRequestTypeWrite:
        length = params.Parameters.Write.Length;
        direction = WdfDmaDirectionWriteToDevice;
        break;
    default:
        WdfRequestCompleteWithPriorityBoost(
                                            Request,
                                            STATUS_INVALID_PARAMETER,
                                            IO_NO_INCREMENT
                                            );
        return;
    }</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548758">WdfObjectReference</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549945">WdfRequestComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549948">WdfRequestCompleteWithInformation</a>
 

 

