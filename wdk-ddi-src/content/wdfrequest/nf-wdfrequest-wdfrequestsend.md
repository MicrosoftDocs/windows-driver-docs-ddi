---
UID: NF:wdfrequest.WdfRequestSend
title: WdfRequestSend function
author: windows-driver-content
description: The WdfRequestSend method sends a specified I/O request to a specified I/O target.
old-location: wdf\wdfrequestsend.htm
old-project: wdf
ms.assetid: a0f4d4a4-f636-44df-911f-e3a615144fa9
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: DFRequestObjectRef_3104cf0d-01d0-4299-a123-ba7a8cc0ada9.xml, wdfrequest/WdfRequestSend, WdfRequestSend, WdfRequestSend method, kmdf.wdfrequestsend, wdf.wdfrequestsend, PFN_WDFREQUESTSEND
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
req.ddi-compliance: DeferredRequestCompleted, DriverCreate, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, ReqCompletionRoutine, ReqMarkCancelableSend, ReqSendFail, ReqSendWhileSpinlock, RequestCompleted, RequestCompletedLocal, RequestFormattedValid, RequestGetStatusValid, RequestSendAndForgetNoFormatting, RequestSendAndForgetNoFormatting2, SyncReqSend2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: See Remarks section.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfRequestSend
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfRequestSend function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRequestSend</b> method sends a specified I/O request to a specified I/O target.


## -syntax


````
BOOLEAN WdfRequestSend(
  _In_     WDFREQUEST                Request,
  _In_     WDFIOTARGET               Target,
  _In_opt_ PWDF_REQUEST_SEND_OPTIONS RequestOptions
);
````


## -parameters




### -param Request [in]

A handle to a framework request object.


### -param Target [in]

A handle to a framework I/O target object. For more information about how to obtain this handle, see the following Remarks section. 


### -param Options

TBD



#### - RequestOptions [in, optional]

A pointer to a <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a> structure that contains caller-supplied request options. This parameter is optional and can be <b>NULL</b> if you do not want to enable any request options.


## -returns


<b>WdfRequestSend</b> returns <b>TRUE</b> if the request was sent to the target. Otherwise, this method returns <b>FALSE</b>.

A bug check occurs if the driver supplies an invalid object handle.



## -remarks


The request object that the driver specifies for the <i>Request</i> parameter can be one that it <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/receiving-i-o-requests">received</a> or one that it created by calling the <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcreate.md">WdfRequestCreate</a> method.

To obtain a handle to an I/O target object, the driver can do one of the following:
<ul>
<li>
If the driver is using general I/O targets, it calls <a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetiotarget.md">WdfDeviceGetIoTarget</a>. For more information, see <a href="https://msdn.microsoft.com/c5d5b589-09a3-4f58-83bf-2876b37b0937">Initializing a General I/O Target</a>.

</li>
<li>
If the driver is using a specialized I/O target, it calls one or more methods that the specialized target object defines. For example, a driver for a USB device can call <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicegetiotarget.md">WdfUsbTargetDeviceGetIoTarget</a> or <a href="..\wdfusb\nf-wdfusb-wdfusbtargetpipegetiotarget.md">WdfUsbTargetPipeGetIoTarget</a>.

</li>
</ul>By default, <b>WdfRequestSend</b> delivers the request to the target asynchronously, which means it returns immediately without waiting for the request to be completed. Optionally, the request can be delivered synchronously, which means <b>WdfRequestSend</b> does not return until a driver completes the request. To send the request synchronously, the driver must set the <b>WDF_REQUEST_SEND_OPTION_SYNCHRONOUS</b> flag in the <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a> structure.

If <b>WdfRequestSend</b> fails, or if your driver sets the WDF_REQUEST_SEND_OPTION_SYNCHRONOUS flag, the driver can call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetstatus.md">WdfRequestGetStatus</a> immediately after calling <b>WdfRequestSend</b>.

If <b>WdfRequestSend</b> succeeds and your driver does not set the WDF_REQUEST_SEND_OPTION_SYNCHRONOUS flag, the driver typically calls <a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetstatus.md">WdfRequestGetStatus</a> from within a <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_completion_routine.md">CompletionRoutine</a> callback function.

If the driver sends the request synchronously, we recommend that the driver set a time-out value in the <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a> structure and the time-out flag in the <b>Flags</b> member of this structure.

If the driver supplies a time-out value, it should call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestallocatetimer.md">WdfRequestAllocateTimer</a> before calling <b>WdfRequestSend</b>. This ensures that <b>WdfRequestSend</b> will not fail if there are insufficient system resources to allocate a timer.

 If the driver sets the <b>WDF_REQUEST_SEND_OPTION_SYNCHRONOUS</b> flag, it must call <b>WdfRequestSend</b> at IRQL = PASSIVE_LEVEL. If this flag is not set, the driver must call this method  at IRQL &lt;= DISPATCH_LEVEL.
          <b>WdfRequestSend</b> sends the request at the caller's IRQL.

A driver cannot call <b>WdfRequestSend</b> to send an I/O request to a USB pipe, if the driver has configured a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/working-with-usb-pipes">continuous reader</a> for the pipe.

For more information about <b>WdfRequestSend</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/forwarding-i-o-requests">Forwarding I/O Requests</a>.



## -see-also

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestallocatetimer.md">WdfRequestAllocateTimer</a>

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetiotarget.md">WdfDeviceGetIoTarget</a>

<a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_completion_routine.md">CompletionRoutine</a>

<a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a>

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetstatus.md">WdfRequestGetStatus</a>

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestcreate.md">WdfRequestCreate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestSend method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

