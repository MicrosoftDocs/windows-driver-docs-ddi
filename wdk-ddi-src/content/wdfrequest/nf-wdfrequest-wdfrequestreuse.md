---
UID: NF:wdfrequest.WdfRequestReuse
title: WdfRequestReuse function
author: windows-driver-content
description: The WdfRequestReuse method reinitializes a framework request object so that it can be reused.
old-location: wdf\wdfrequestreuse.htm
old-project: wdf
ms.assetid: 3d649cc5-6512-432c-9bd9-60e18507a873
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , DFRequestObjectRef_8815216b-4632-4cc8-8afd-c4b1412ddbad.xml, R, W, WdfRequestReuse, WdfRequestReuse method, d, e, f, kmdf.wdfrequestreuse, q, s, t, u, wdf.wdfrequestreuse, wdfrequest/WdfRequestReuse"
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
req.ddi-compliance: DriverCreate, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2, ReqSendFail
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
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
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfRequestReuse
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfRequestReuse function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRequestReuse</b> method reinitializes a framework request object so that it can be reused.


## -syntax


````
NTSTATUS WdfRequestReuse(
  _In_ WDFREQUEST                Request,
  _In_ PWDF_REQUEST_REUSE_PARAMS ReuseParams
);
````


## -parameters




### -param Request [in]

A handle to a framework request object.


### -param ReuseParams [in]

A pointer to a caller-allocated <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_reuse_params.md">WDF_REQUEST_REUSE_PARAMS</a> structure.


## -returns



<b>WdfRequestReuse</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An input parameter is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WDF_REQUEST_INVALID_STATE</b></dt>
</dl>
</td>
<td width="60%">
The driver supplied an IRP in the <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_reuse_params.md">WDF_REQUEST_REUSE_PARAMS</a> structure, but the specified request object was not obtained from <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcreatefromirp.md">WdfRequestCreateFromIrp</a>.

</td>
</tr>
</table>
 

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



A framework-based driver can reuse framework request objects that it created by previous calls to <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcreate.md">WdfRequestCreate</a> or <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcreatefromirp.md">WdfRequestCreateFromIrp</a>. Drivers can also reuse request objects that they have <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/receiving-i-o-requests">received from the framework</a>, but they cannot set the <a href="https://msdn.microsoft.com/3d1f8f38-b875-4661-9941-4dec28b7e8fb">WDF_REQUEST_REUSE_SET_NEW_IRP</a> flag for those request objects.

A driver can reuse a request object after the original request has been completed. After a driver has called <b>WdfRequestReuse</b>, the request's contents must be reinitialized. The driver can specify some request parameters in the <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_reuse_params.md">WDF_REQUEST_REUSE_PARAMS</a> structure. 

If you want the reused request to have a <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_completion_routine.md">CompletionRoutine</a> callback function, the driver must call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsetcompletionroutine.md">WdfRequestSetCompletionRoutine</a> after calling <b>WdfRequestReuse</b>.

For more information about <b>WdfRequestReuse</b>, see <a href="https://msdn.microsoft.com/9e3090a9-62d0-48b3-9f3b-7171dc6d2766">Reusing Framework Request Objects</a>.


#### Examples

The following code example is part of a <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_completion_routine.md">CompletionRoutine</a> callback function that calls <b>WdfRequestReuse</b> so that the driver can reuse a driver-allocated request.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
MyRequestCompletionRoutine(
    IN WDFREQUEST  Request,
    IN WDFIOTARGET  Target,
    PWDF_REQUEST_COMPLETION_PARAMS  CompletionParams,
    IN WDFCONTEXT  Context
    )
{
    WDF_REQUEST_REUSE_PARAMS  params;
    NTSTATUS  status;
...
    WDF_REQUEST_REUSE_PARAMS_INIT(
                                  &amp;params,
                                  WDF_REQUEST_REUSE_NO_FLAGS,
                                  STATUS_SUCCESS
                                  );

    status = WdfRequestReuse(
                             Request,
                             &amp;params
                             );
    ASSERT(NT_SUCCESS(status));
...
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfrequest\ns-wdfrequest-_wdf_request_reuse_params.md">WDF_REQUEST_REUSE_PARAMS</a>



<a href="..\wdfrequest\nf-wdfrequest-wdf_request_reuse_params_init.md">WDF_REQUEST_REUSE_PARAMS_INIT</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestsetcompletionroutine.md">WdfRequestSetCompletionRoutine</a>



<a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_completion_routine.md">CompletionRoutine</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestcreate.md">WdfRequestCreate</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestcreatefromirp.md">WdfRequestCreateFromIrp</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestReuse method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

