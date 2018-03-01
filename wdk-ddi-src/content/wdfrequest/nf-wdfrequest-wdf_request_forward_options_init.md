---
UID: NF:wdfrequest.WDF_REQUEST_FORWARD_OPTIONS_INIT
title: WDF_REQUEST_FORWARD_OPTIONS_INIT function
author: windows-driver-content
description: The WDF_REQUEST_FORWARD_OPTIONS_INIT function initializes a WDF_REQUEST_FORWARD_OPTIONS structure.
old-location: wdf\wdf_request_forward_options_init.htm
old-project: wdf
ms.assetid: 301b4b63-0337-4f78-a4f8-6b2d2b168663
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFRequestObjectRef_ade75e55-accb-4fe0-a1be-b5acd9e4c34b.xml, WDF_REQUEST_FORWARD_OPTIONS_INIT, WDF_REQUEST_FORWARD_OPTIONS_INIT function, kmdf.wdf_request_forward_options_init, wdf.wdf_request_forward_options_init, wdfrequest/WDF_REQUEST_FORWARD_OPTIONS_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.9
req.umdf-ver: 
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
-	WDF_REQUEST_FORWARD_OPTIONS_INIT
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WDF_REQUEST_FORWARD_OPTIONS_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_REQUEST_FORWARD_OPTIONS_INIT</b> function initializes a <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_forward_options.md">WDF_REQUEST_FORWARD_OPTIONS</a> structure.


## -syntax


````
VOID WDF_REQUEST_FORWARD_OPTIONS_INIT(
  _Out_ PWDF_REQUEST_FORWARD_OPTIONS ForwardOptions
);
````


## -parameters




### -param ForwardOptions [out]

A pointer to a <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_forward_options.md">WDF_REQUEST_FORWARD_OPTIONS</a> structure.


## -returns



None.




## -remarks



Before a driver calls <a href="..\wdfrequest\nf-wdfrequest-wdfrequestforwardtoparentdeviceioqueue.md">WdfRequestForwardToParentDeviceIoQueue</a>, it must call <b>WDF_REQUEST_FORWARD_OPTIONS_INIT</b> to initialize a <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_forward_options.md">WDF_REQUEST_FORWARD_OPTIONS</a> structure.

The <b>WDF_REQUEST_FORWARD_OPTIONS_INIT</b> function zeros the specified <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_forward_options.md">WDF_REQUEST_FORWARD_OPTIONS</a> structure and sets the structure's <b>Size</b> member. Then the function sets the <a href="..\wdfrequest\ne-wdfrequest-_wdf_request_forward_options_flags.md">WDF_REQUEST_FORWARD_OPTION_SEND_AND_FORGET</a> flag.

For a code example that uses <b>WDF_REQUEST_FORWARD_OPTIONS_INIT</b>, see <a href="..\wdfrequest\nf-wdfrequest-wdfrequestforwardtoparentdeviceioqueue.md">WdfRequestForwardToParentDeviceIoQueue</a>.




## -see-also

<a href="..\wdfrequest\ns-wdfrequest-_wdf_request_forward_options.md">WDF_REQUEST_FORWARD_OPTIONS</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestforwardtoparentdeviceioqueue.md">WdfRequestForwardToParentDeviceIoQueue</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_REQUEST_FORWARD_OPTIONS_INIT function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

