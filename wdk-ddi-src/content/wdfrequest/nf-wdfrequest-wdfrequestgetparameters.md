---
UID: NF:wdfrequest.WdfRequestGetParameters
title: WdfRequestGetParameters function
author: windows-driver-content
description: The WdfRequestGetParameters method retrieves the parameters that are associated with a specified framework request object.
old-location: wdf\wdfrequestgetparameters.htm
old-project: wdf
ms.assetid: 7d9924a9-23b6-4bec-95f0-cebc3e99fda4
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfRequestGetParameters, wdfrequest/WdfRequestGetParameters, wdf.wdfrequestgetparameters, PFN_WDFREQUESTGETPARAMETERS, DFRequestObjectRef_f3d44f7e-60b9-4a64-b5b8-a68ab5240376.xml, kmdf.wdfrequestgetparameters, WdfRequestGetParameters method
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
req.ddi-compliance: DriverCreate, evtioresumegetparam, evtiostopgetparam, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2
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
-	WdfRequestGetParameters
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfRequestGetParameters function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRequestGetParameters</b> method retrieves the parameters that are associated with a specified framework request object.


## -syntax


````
VOID WdfRequestGetParameters(
  _In_  WDFREQUEST              Request,
  _Out_ PWDF_REQUEST_PARAMETERS Parameters
);
````


## -parameters




### -param Request [in]

A handle to a framework request object. 


### -param Parameters [out]

A pointer to a caller-allocated <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_parameters.md">WDF_REQUEST_PARAMETERS</a> structure that the <a href="..\wdfrequest\nf-wdfrequest-wdf_request_parameters_init.md">WDF_REQUEST_PARAMETERS_INIT</a> routine initialized and filled in.


## -returns


None.

A bug check occurs if the driver supplies an invalid object handle.





## -remarks


A driver cannot retrieve parameters from a driver-created request by calling <b>WdfRequestGetParameters</b>  because the framework does not allocate a stack location for the current driver.

For more information about <b>WdfRequestGetParameters</b>, see <a href="https://msdn.microsoft.com/a686ea00-6987-480a-a4ce-892e1efbed87">Obtaining Information About an I/O Request</a>.



## -see-also

<a href="..\wdfrequest\ns-wdfrequest-_wdf_request_parameters.md">WDF_REQUEST_PARAMETERS</a>

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestwdmgetirp.md">WdfRequestWdmGetIrp</a>

<a href="..\wdfrequest\nf-wdfrequest-wdf_request_parameters_init.md">WDF_REQUEST_PARAMETERS_INIT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestGetParameters method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

