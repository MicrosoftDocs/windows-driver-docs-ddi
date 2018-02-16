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
ms.keywords: WDF_REQUEST_PARAMETERS_INIT, wdf.wdf_request_parameters_init, WDF_REQUEST_PARAMETERS_INIT function, wdfrequest/WDF_REQUEST_PARAMETERS_INIT, DFRequestObjectRef_1c1e97cb-9ca1-473a-aa30-d39fdadbc726.xml, kmdf.wdf_request_parameters_init
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
-	WDF_REQUEST_PARAMETERS_INIT
product: Windows
targetos: Windows
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


#### Examples

The following code example initializes a <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_parameters.md">WDF_REQUEST_PARAMETERS</a> structure and then calls <a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetparameters.md">WdfRequestGetParameters</a>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
MyEvtIoDefault(
    IN WDFQUEUE  Queue,
    IN WDFREQUEST  Request
    )
{
    WDF_REQUEST_PARAMETERS  params;

    WDF_REQUEST_PARAMETERS_INIT(&amp;params);

    WdfRequestGetParameters(
                            Request,
                            &amp;params
                            );
...
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfrequest\ns-wdfrequest-_wdf_request_parameters.md">WDF_REQUEST_PARAMETERS</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetparameters.md">WdfRequestGetParameters</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_REQUEST_PARAMETERS_INIT function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

