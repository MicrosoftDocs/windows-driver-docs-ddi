---
UID: NF:wdfrequest.WdfRequestGetParameters
title: WdfRequestGetParameters function (wdfrequest.h)
description: The WdfRequestGetParameters method retrieves the parameters that are associated with a specified framework request object.
old-location: wdf\wdfrequestgetparameters.htm
tech.root: wdf
ms.date: 01/26/2022
keywords: ["WdfRequestGetParameters function"]
ms.keywords: DFRequestObjectRef_f3d44f7e-60b9-4a64-b5b8-a68ab5240376.xml, WdfRequestGetParameters, WdfRequestGetParameters method, kmdf.wdfrequestgetparameters, wdf.wdfrequestgetparameters, wdfrequest/WdfRequestGetParameters
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfRequestGetParameters
 - wdfrequest/WdfRequestGetParameters
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
 - WUDFx02000.dll
 - WUDFx02000.dll.dll
api_name:
 - WdfRequestGetParameters
---

# WdfRequestGetParameters function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfRequestGetParameters</b> method retrieves the parameters that are associated with a specified framework request object.

## -parameters

### -param Request [in]


A handle to a framework request object.

### -param Parameters [in, out]


A pointer to a caller-allocated <a href="/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_parameters">WDF_REQUEST_PARAMETERS</a> structure that the <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdf_request_parameters_init">WDF_REQUEST_PARAMETERS_INIT</a> routine initialized and filled in.

## -remarks

A bug check occurs if the driver supplies an invalid object handle.



A driver cannot retrieve parameters from a driver-created request by calling <b>WdfRequestGetParameters</b>  because the framework does not allocate a stack location for the current driver.

For more information about <b>WdfRequestGetParameters</b>, see <a href="/windows-hardware/drivers/wdf/obtaining-information-about-an-i-o-request">Obtaining Information About an I/O Request</a>.


#### Examples

For a code example that uses <b>WdfRequestGetParameters</b>, see <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcomplete">WdfRequestComplete</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_parameters">WDF_REQUEST_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdf_request_parameters_init">WDF_REQUEST_PARAMETERS_INIT</a>



<a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestwdmgetirp">WdfRequestWdmGetIrp</a>
