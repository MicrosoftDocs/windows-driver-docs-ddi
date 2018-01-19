---
UID: NF:wdfrequest.WDF_REQUEST_PARAMETERS_INIT
title: WDF_REQUEST_PARAMETERS_INIT function
author: windows-driver-content
description: The WDF_REQUEST_PARAMETERS_INIT function initializes a WDF_REQUEST_PARAMETERS structure.
old-location: wdf\wdf_request_parameters_init.htm
old-project: wdf
ms.assetid: c4e83638-4931-460f-848b-ceb0f7a00afb
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WDF_REQUEST_PARAMETERS_INIT
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
req.alt-api: WDF_REQUEST_PARAMETERS_INIT
req.alt-loc: wdfrequest.h
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
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WDF_REQUEST_PARAMETERS_INIT function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_REQUEST_PARAMETERS_INIT</b> function initializes a <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_parameters.md">WDF_REQUEST_PARAMETERS</a> structure.



## -syntax

````
VOID WDF_REQUEST_PARAMETERS_INIT(
  _Out_ PWDF_REQUEST_PARAMETERS Parameters
);
````


## -parameters

### -param Parameters [out]

A pointer to a caller-supplied <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_parameters.md">WDF_REQUEST_PARAMETERS</a> structure.


## -returns
None


## -remarks
Drivers must call <b>WDF_REQUEST_PARAMETERS_INIT</b> to initialize a <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_parameters.md">WDF_REQUEST_PARAMETERS</a> structure before calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetparameters.md">WdfRequestGetParameters</a>.

The <b>WDF_REQUEST_PARAMETERS_INIT</b> function zeros the specified <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_parameters.md">WDF_REQUEST_PARAMETERS</a> structure and sets the structure's <b>Size</b> member.

The following code example initializes a <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_parameters.md">WDF_REQUEST_PARAMETERS</a> structure and then calls <a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetparameters.md">WdfRequestGetParameters</a>.


## -see-also
<dl>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetparameters.md">WdfRequestGetParameters</a>
</dt>
<dt>
<a href="..\wdfrequest\ns-wdfrequest-_wdf_request_parameters.md">WDF_REQUEST_PARAMETERS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_REQUEST_PARAMETERS_INIT function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

