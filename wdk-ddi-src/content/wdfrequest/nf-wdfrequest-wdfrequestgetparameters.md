---
UID: NF:wdfrequest.WdfRequestGetParameters
title: WdfRequestGetParameters function
author: windows-driver-content
description: The WdfRequestGetParameters method retrieves the parameters that are associated with a specified framework request object.
old-location: wdf\wdfrequestgetparameters.htm
tech.root: wdf
ms.assetid: 7d9924a9-23b6-4bec-95f0-cebc3e99fda4
ms.date: 02/26/2018
ms.keywords: DFRequestObjectRef_f3d44f7e-60b9-4a64-b5b8-a68ab5240376.xml, WdfRequestGetParameters, WdfRequestGetParameters method, kmdf.wdfrequestgetparameters, wdf.wdfrequestgetparameters, wdfrequest/WdfRequestGetParameters
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfRequestGetParameters
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfRequestGetParameters function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfRequestGetParameters</b> method retrieves the parameters that are associated with a specified framework request object.


## -parameters




### -param Request [in]

A handle to a framework request object. 


### -param Parameters [out]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff552472">WDF_REQUEST_PARAMETERS</a> structure that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552476">WDF_REQUEST_PARAMETERS_INIT</a> routine initialized and filled in.


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



A driver cannot retrieve parameters from a driver-created request by calling <b>WdfRequestGetParameters</b>  because the framework does not allocate a stack location for the current driver.

For more information about <b>WdfRequestGetParameters</b>, see <a href="https://msdn.microsoft.com/a686ea00-6987-480a-a4ce-892e1efbed87">Obtaining Information About an I/O Request</a>.


#### Examples

For a code example that uses <b>WdfRequestGetParameters</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff549945">WdfRequestComplete</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552472">WDF_REQUEST_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552476">WDF_REQUEST_PARAMETERS_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550037">WdfRequestWdmGetIrp</a>
 

 

