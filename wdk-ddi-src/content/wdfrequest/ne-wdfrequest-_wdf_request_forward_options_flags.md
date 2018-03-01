---
UID: NE:wdfrequest._WDF_REQUEST_FORWARD_OPTIONS_FLAGS
title: "_WDF_REQUEST_FORWARD_OPTIONS_FLAGS"
author: windows-driver-content
description: The WDF_REQUEST_FORWARD_OPTIONS_FLAGS enumeration type defines flags that are used in a driver's WDF_REQUEST_FORWARD_OPTIONS structure.
old-location: wdf\wdf_request_forward_options_flags.htm
old-project: wdf
ms.assetid: 6161bfd3-482c-4571-bd88-2e25d32b34a0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFRequestObjectRef_cad8f6c6-9c76-4dc3-ac3f-3938e5174563.xml, WDF_REQUEST_FORWARD_OPTIONS_FLAGS, WDF_REQUEST_FORWARD_OPTIONS_FLAGS enumeration, WDF_REQUEST_FORWARD_OPTION_SEND_AND_FORGET, _WDF_REQUEST_FORWARD_OPTIONS_FLAGS, kmdf.wdf_request_forward_options_flags, wdf.wdf_request_forward_options_flags, wdfrequest/WDF_REQUEST_FORWARD_OPTIONS_FLAGS, wdfrequest/WDF_REQUEST_FORWARD_OPTION_SEND_AND_FORGET
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Windows
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
-	WDF_REQUEST_FORWARD_OPTIONS_FLAGS
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_FORWARD_OPTIONS_FLAGS
req.product: Windows 10 or later.
---

# _WDF_REQUEST_FORWARD_OPTIONS_FLAGS enumeration


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_REQUEST_FORWARD_OPTIONS_FLAGS</b> enumeration type defines flags that are used in a driver's <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_forward_options.md">WDF_REQUEST_FORWARD_OPTIONS</a> structure.


## -syntax


````
typedef enum _WDF_REQUEST_FORWARD_OPTIONS_FLAGS { 
  WDF_REQUEST_FORWARD_OPTION_SEND_AND_FORGET  = 0x0000001
} WDF_REQUEST_FORWARD_OPTIONS_FLAGS;
````


## -enum-fields




### -field WDF_REQUEST_FORWARD_OPTION_SEND_AND_FORGET

If set, the driver does not need to be notified when the request is completed or canceled. The driver does not set a <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_completion_routine.md">CompletionRoutine</a> callback function or call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcomplete.md">WdfRequestComplete</a> for the request. 


## -remarks



Currently, drivers must set the WDF_REQUEST_FORWARD_OPTION_SEND_AND_FORGET flag.




## -see-also

<a href="..\wdfrequest\ns-wdfrequest-_wdf_request_forward_options.md">WDF_REQUEST_FORWARD_OPTIONS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_REQUEST_FORWARD_OPTIONS_FLAGS enumeration%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

