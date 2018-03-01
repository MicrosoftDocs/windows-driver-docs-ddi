---
UID: NF:wdfrequest.WDF_REQUEST_COMPLETION_PARAMS_INIT
title: WDF_REQUEST_COMPLETION_PARAMS_INIT function
author: windows-driver-content
description: The WDF_REQUEST_COMPLETION_PARAMS_INIT function initializes a WDF_REQUEST_COMPLETION_PARAMS structure.
old-location: wdf\wdf_request_completion_params_init.htm
old-project: wdf
ms.assetid: f13e9474-7805-4c58-983d-4cfea4f005cc
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DFRequestObjectRef_f92844e3-5003-45db-9684-608301b1ec32.xml, WDF_REQUEST_COMPLETION_PARAMS_INIT, WDF_REQUEST_COMPLETION_PARAMS_INIT function, kmdf.wdf_request_completion_params_init, wdf.wdf_request_completion_params_init, wdfrequest/WDF_REQUEST_COMPLETION_PARAMS_INIT
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
req.lib: NtosKrnl.exe
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
-	WDF_REQUEST_COMPLETION_PARAMS_INIT
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WDF_REQUEST_COMPLETION_PARAMS_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_REQUEST_COMPLETION_PARAMS_INIT</b> function initializes a <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_completion_params.md">WDF_REQUEST_COMPLETION_PARAMS</a> structure.


## -syntax


````
VOID WDF_REQUEST_COMPLETION_PARAMS_INIT(
  _Out_ PWDF_REQUEST_COMPLETION_PARAMS Params
);
````


## -parameters




### -param Params [out]

A pointer to a caller-supplied <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_completion_params.md">WDF_REQUEST_COMPLETION_PARAMS</a> structure.


## -returns



None




## -remarks



Drivers must call <b>WDF_REQUEST_COMPLETION_PARAMS_INIT</b> to initialize a <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_completion_params.md">WDF_REQUEST_COMPLETION_PARAMS</a> structure before calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetcompletionparams.md">WdfRequestGetCompletionParams</a>.

The <b>WDF_REQUEST_COMPLETION_PARAMS_INIT</b> function zeros the specified <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_completion_params.md">WDF_REQUEST_COMPLETION_PARAMS</a> structure and sets the structure's <b>Size</b> member. It also sets the structure's <b>Type</b> member to <b>WdfRequestTypeNoFormat</b>.


#### Examples

For a code example that uses <b>WDF_REQUEST_COMPLETION_PARAMS_INIT</b>, see <a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetcompletionparams.md">WdfRequestGetCompletionParams</a>.

<div class="code"></div>



## -see-also

<a href="..\wdfrequest\ns-wdfrequest-_wdf_request_completion_params.md">WDF_REQUEST_COMPLETION_PARAMS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_REQUEST_COMPLETION_PARAMS_INIT function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

