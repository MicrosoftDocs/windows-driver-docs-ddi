---
UID: NF:wdfrequest.WDF_REQUEST_SEND_OPTIONS_INIT
title: WDF_REQUEST_SEND_OPTIONS_INIT function
author: windows-driver-content
description: The WDF_REQUEST_SEND_OPTIONS_INIT function initializes a driver's WDF_REQUEST_SEND_OPTIONS structure.
old-location: wdf\wdf_request_send_options_init.htm
old-project: wdf
ms.assetid: 65e57147-f8a1-4b9b-b856-51f89bcba149
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WDF_REQUEST_SEND_OPTIONS_INIT, kmdf.wdf_request_send_options_init, wdf.wdf_request_send_options_init, DFRequestObjectRef_9a31e96a-4cb1-43ea-b429-591f820838d8.xml, WDF_REQUEST_SEND_OPTIONS_INIT function, wdfrequest/WDF_REQUEST_SEND_OPTIONS_INIT
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfrequest.h
apiname:
-	WDF_REQUEST_SEND_OPTIONS_INIT
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WDF_REQUEST_SEND_OPTIONS_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_REQUEST_SEND_OPTIONS_INIT</b> function initializes a driver's <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a> structure.


## -syntax


````
VOID WDF_REQUEST_SEND_OPTIONS_INIT(
  _Out_ PWDF_REQUEST_SEND_OPTIONS Options,
  _In_  ULONG                     Flags
);
````


## -parameters




### -param Options [out]

A pointer to a caller-supplied <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a> structure.


### -param Flags [in]

A bitwise OR of <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_request_send_options_flags.md">WDF_REQUEST_SEND_OPTIONS_FLAGS</a>-typed flags. 


## -returns


None



## -remarks


The <b>WDF_REQUEST_SEND_OPTIONS_INIT</b> function zeros the specified <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a> structure, sets the structure's <b>Size</b> member, and sets the <b>Flag</b> member to the specified <i>Flags</i> value.



## -see-also

<a href="..\wudfddi_types\ne-wudfddi_types-_wdf_request_send_options_flags.md">WDF_REQUEST_SEND_OPTIONS_FLAGS</a>

<a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a>

<a href="..\wdfrequest\nf-wdfrequest-wdf_request_send_options_set_timeout.md">WDF_REQUEST_SEND_OPTIONS_SET_TIMEOUT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_REQUEST_SEND_OPTIONS_INIT function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

