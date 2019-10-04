---
UID: NF:wdfrequest.WdfRequestGetStatus
title: WdfRequestGetStatus function (wdfrequest.h)
description: The WdfRequestGetStatus method returns the status of an I/O request.
old-location: wdf\wdfrequestgetstatus.htm
tech.root: wdf
ms.assetid: 82f922a1-34c1-475b-b12a-210ae602a4bd
ms.date: 02/26/2018
ms.keywords: DFRequestObjectRef_60149f5d-5523-4b88-9bba-464be280b2b7.xml, WdfRequestGetStatus, WdfRequestGetStatus method, kmdf.wdfrequestgetstatus, wdf.wdfrequestgetstatus, wdfrequest/WdfRequestGetStatus
ms.topic: function
f1_keywords:
 - "wdfrequest/WdfRequestGetStatus"
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, RequestGetStatusValid
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
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
- WdfRequestGetStatus
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfRequestGetStatus function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfRequestGetStatus</b> method returns the status of an I/O request.


## -parameters




### -param Request [in]

A handle to a framework request object.


## -returns



<b>WdfRequestGetStatus</b>  returns an NTSTATUS value. For more information about what value can be returned, see the following Remarks section.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



The <b>WdfRequestGetStatus</b> method returns one of the following:

<ul>
<li>
If a driver's call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestsend">WdfRequestSend</a> succeeds, <b>WdfRequestGetStatus</b> returns the status value that is set by the driver that calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestcomplete">WdfRequestComplete</a> to complete the specified request. The driver typically calls <b>WdfRequestGetStatus</b> from within a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nc-wdfrequest-evt_wdf_request_completion_routine">CompletionRoutine</a> callback function.

</li>
<li>
If a driver's call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestsend">WdfRequestSend</a> fails, <b>WdfRequestGetStatus</b> returns a status value that the framework has set to describe the failure. The driver can call <b>WdfRequestGetStatus</b> immediately after calling <b>WdfRequestSend</b>.

</li>
</ul>
If the driver sets the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/ne-wdfrequest-_wdf_request_send_options_flags">WDF_REQUEST_SEND_OPTION_SYNCHRONOUS</a> flag for a request when calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestsend">WdfRequestSend</a>, the driver can call <b>WdfRequestGetStatus</b> immediately after calling <b>WdfRequestSend</b>, whether the call to <b>WdfRequestSend</b> succeeds or fails.

For more information about request completion, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/completing-i-o-requests">Completing I/O Requests</a>.


#### Examples

The following code example is from the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/sample-kmdf-drivers">KbFiltr</a> sample driver. This example sends an I/O request to an I/O target. If <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestsend">WdfRequestSend</a> fails, the example uses the <b>WdfRequestGetStatus</b> return value as input to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestcomplete">WdfRequestComplete</a>. 

```cpp
VOID
KbFilter_ForwardRequest(
    IN WDFREQUEST Request,
    IN WDFIOTARGET Target
    )
{
    WDF_REQUEST_SEND_OPTIONS options;
    BOOLEAN ret;
    NTSTATUS status;

    WDF_REQUEST_SEND_OPTIONS_INIT(
                                  &options,
                                  WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET
                                  );

    ret = WdfRequestSend(
                         Request,
                         Target,
                         &options
                         );

    if (ret == FALSE) {
        status = WdfRequestGetStatus (Request);
        DebugPrint(("WdfRequestSend failed: 0x%x\n", status));
        WdfRequestComplete(
                           Request,
                           status
                           );
    }
    return;
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nc-wdfrequest-evt_wdf_request_completion_routine">CompletionRoutine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestcomplete">WdfRequestComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestsend">WdfRequestSend</a>
 

 

