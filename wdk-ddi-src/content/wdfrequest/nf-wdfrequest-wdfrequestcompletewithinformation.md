---
UID: NF:wdfrequest.WdfRequestCompleteWithInformation
title: WdfRequestCompleteWithInformation function
author: windows-driver-content
description: The WdfRequestCompleteWithInformation method stores completion information and then completes a specified I/O request with a supplied completion status.
old-location: wdf\wdfrequestcompletewithinformation.htm
old-project: wdf
ms.assetid: dc8f5570-5bdd-492a-a830-e166f146879a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFRequestObjectRef_29eec73c-aa09-4814-85f9-61979df03412.xml, WdfRequestCompleteWithInformation, WdfRequestCompleteWithInformation method, kmdf.wdfrequestcompletewithinformation, wdf.wdfrequestcompletewithinformation, wdfrequest/WdfRequestCompleteWithInformation
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfRequestCompleteWithInformation
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfRequestCompleteWithInformation function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRequestCompleteWithInformation</b> method stores completion information and then completes a specified I/O request with a supplied completion status.


## -syntax


````
VOID WdfRequestCompleteWithInformation(
  _In_ WDFREQUEST Request,
  _In_ NTSTATUS   Status,
  _In_ ULONG_PTR  Information
);
````


## -parameters




### -param Request [in]

A handle to the request object.


### -param Status [in]

An <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS value</a> that represents the completion status of the request. Valid status values include, but are not limited to, the following:





#### STATUS_SUCCESS

The driver successfully completed the request.



#### STATUS_CANCELLED

The driver canceled the request.



#### STATUS_UNSUCCESSFUL

The driver encountered an error while processing the request.


### -param Information [in]

Driver-defined completion status information for the request, such as the number of bytes that were transferred.


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Calling <b>WdfRequestCompleteWithInformation</b> is equivalent to calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsetinformation.md">WdfRequestSetInformation</a> and then calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcomplete.md">WdfRequestComplete</a>.

After a call to <b>WdfRequestCompleteWithInformation</b> returns, the request handle is no longer valid unless the driver has called <a href="https://msdn.microsoft.com/library/windows/hardware/ff548758">WdfObjectReference</a> to add one or more additional reference counts to the request object. Note that after <b>WdfRequestCompleteWithInformation</b> returns, the driver must not attempt to access the associated WDM IRP structure, even if it has called <b>WdfObjectReference</b>.

When your driver calls <b>WdfRequestCompleteWithInformation</b>, the framework supplies a default value that the system uses to boost the run-time priority of the thread that requested the I/O operation. For information about default priority boost values, see <a href="https://msdn.microsoft.com/9a501ca1-58c9-4458-b202-9581f8ce5e5f">Specifying Priority Boosts When Completing I/O Requests</a>. Your driver can call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcompletewithpriorityboost.md">WdfRequestCompleteWithPriorityBoost</a> to override the default priority boost value.

For more information about calling <b>WdfRequestCompleteWithInformation</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">Completing I/O Requests</a>.


#### Examples

The following code example shows how a driver for a USB device might call <b>WdfRequestCompleteWithInformation</b> in a <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_completion_routine.md">CompletionRoutine</a> callback function .

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
EvtRequestReadCompletionRoutine(
    IN WDFREQUEST  Request,
    IN WDFIOTARGET  Target,
    PWDF_REQUEST_COMPLETION_PARAMS  CompletionParams,
    IN WDFCONTEXT  Context
    )
{    
    NTSTATUS  status;
    size_t  bytesRead = 0;
    PWDF_USB_REQUEST_COMPLETION_PARAMS  usbCompletionParams;

    UNREFERENCED_PARAMETER(Target);
    UNREFERENCED_PARAMETER(Context);

    status = CompletionParams-&gt;IoStatus.Status;
    usbCompletionParams = CompletionParams-&gt;Parameters.Usb.Completion;
    bytesRead =  usbCompletionParams-&gt;Parameters.PipeRead.Length;
 
    if (NT_SUCCESS(status)){
        TraceEvents(
                    TRACE_LEVEL_INFORMATION,
                    DBG_READ,
                    "Number of bytes read: %I64d\n",
                    (INT64)bytesRead
                    );
    } else {
        TraceEvents(
                    TRACE_LEVEL_ERROR,
                    DBG_READ,
                    "Read failed - request status 0x%x UsbdStatus 0x%x\n",
                    status,
                    usbCompletionParams-&gt;UsbdStatus
                    );
    }
    WdfRequestCompleteWithInformation(
                                      Request,
                                      status,
                                      bytesRead
                                      );
    return;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestsetinformation.md">WdfRequestSetInformation</a>



<a href="..\wdfusb\ns-wdfusb-_wdf_usb_request_completion_params.md">WDF_USB_REQUEST_COMPLETION_PARAMS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548758">WdfObjectReference</a>



<a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_completion_routine.md">CompletionRoutine</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestcomplete.md">WdfRequestComplete</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestcompletewithpriorityboost.md">WdfRequestCompleteWithPriorityBoost</a>



<a href="..\wdfrequest\ns-wdfrequest-_wdf_request_completion_params.md">WDF_REQUEST_COMPLETION_PARAMS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestCompleteWithInformation method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

