---
UID: NF:wdfrequest.WDF_REQUEST_SEND_OPTIONS_SET_TIMEOUT
title: WDF_REQUEST_SEND_OPTIONS_SET_TIMEOUT function
author: windows-driver-content
description: The WDF_REQUEST_SEND_OPTIONS_SET_TIMEOUT function sets a time-out value in a driver's WDF_REQUEST_SEND_OPTIONS structure.
old-location: wdf\wdf_request_send_options_set_timeout.htm
old-project: wdf
ms.assetid: 729bd44f-9ac7-4b3d-905d-a78b10fba2a7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFRequestObjectRef_bcbdd786-6d81-45f7-a70b-96e781da0d36.xml, WDF_REQUEST_SEND_OPTIONS_SET_TIMEOUT, WDF_REQUEST_SEND_OPTIONS_SET_TIMEOUT function, kmdf.wdf_request_send_options_set_timeout, wdf.wdf_request_send_options_set_timeout, wdfrequest/WDF_REQUEST_SEND_OPTIONS_SET_TIMEOUT
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfrequest.h
api_name:
-	WDF_REQUEST_SEND_OPTIONS_SET_TIMEOUT
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WDF_REQUEST_SEND_OPTIONS_SET_TIMEOUT function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_REQUEST_SEND_OPTIONS_SET_TIMEOUT</b> function sets a time-out value in a driver's <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a> structure.


## -syntax


````
VOID WDF_REQUEST_SEND_OPTIONS_SET_TIMEOUT(
  _Inout_ PWDF_REQUEST_SEND_OPTIONS Options,
  _In_    LONGLONG                  Timeout
);
````


## -parameters




### -param Options [in, out]

A pointer to the driver's <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a> structure.


### -param Timeout [in]

An absolute or relative time-out value. For more information, see the <b>Timeout</b> member of the <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a> structure.


## -returns



None




## -remarks



To set a time-out value, your driver must call <b>WDF_REQUEST_SEND_OPTIONS_SET_TIMEOUT</b> after it calls <a href="..\wdfrequest\nf-wdfrequest-wdf_request_send_options_init.md">WDF_REQUEST_SEND_OPTIONS_INIT</a>.

The <b>WDF_REQUEST_SEND_OPTIONS_SET_TIMEOUT</b> function stores the specified timeout value in the specified <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a> structure's <b>Timeout</b> member. It also sets the <b>WDF_REQUEST_SEND_OPTION_TIMEOUT</b> flag in the structure's <b>Flags</b> member.


#### Examples

The following code example initializes a <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a> structure and sets a time-out value for the structure. (The example calls <a href="..\wdfcore\nf-wdfcore-wdf_rel_timeout_in_sec.md">WDF_REL_TIMEOUT_IN_SEC</a> to specify a relative time-out value of 10 seconds.) The example then uses the <b>WDF_REQUEST_SEND_OPTIONS</b> structure as input to <a href="..\wdfusb\nf-wdfusb-wdfusbtargetpipewritesynchronously.md">WdfUsbTargetPipeWriteSynchronously</a>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_REQUEST_SEND_OPTIONS  syncReqOptions;

WDF_REQUEST_SEND_OPTIONS_INIT(
                              &amp;syncReqOptions,
                              0
                              );
WDF_REQUEST_SEND_OPTIONS_SET_TIMEOUT(
                                     &amp;syncReqOptions,
                                     WDF_REL_TIMEOUT_IN_SEC(10)
                                     );
status = WdfUsbTargetPipeWriteSynchronously(
                                            pipeHandle,
                                            NULL,
                                            &amp;syncReqOptions,
                                            &amp;writeBufDesc,
                                            NULL
                                            );</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfrequest\nf-wdfrequest-wdf_request_send_options_init.md">WDF_REQUEST_SEND_OPTIONS_INIT</a>



<a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_REQUEST_SEND_OPTIONS_SET_TIMEOUT function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

