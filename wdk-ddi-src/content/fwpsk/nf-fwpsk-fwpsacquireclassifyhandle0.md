---
UID: NF:fwpsk.FwpsAcquireClassifyHandle0
title: FwpsAcquireClassifyHandle0 function (fwpsk.h)
description: The FwpsAcquireClassifyHandle0 function generates a classification handle that is used to identify asynchronous classification operations and requests for writable layer data.Note  FwpsAcquireClassifyHandle0 is a specific version of FwpsAcquireClassifyHandle. See WFP Version-Independent Names and Targeting Specific Versions of Windows for more information.
old-location: netvista\fwpsacquireclassifyhandle0.htm
tech.root: netvista
ms.assetid: 7348d937-6541-47a7-ae70-7d851d41bc1a
ms.date: 05/02/2018
keywords: ["FwpsAcquireClassifyHandle0 function"]
ms.keywords: FwpsAcquireClassifyHandle0, FwpsAcquireClassifyHandle0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsAcquireClassifyHandle0, netvista.fwpsacquireclassifyhandle0, wfp_ref_2_funct_3_fwps_A-B_c0b568dd-f546-4bab-a012-14f4d2a8d846.xml
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 7.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FwpsAcquireClassifyHandle0
 - fwpsk/FwpsAcquireClassifyHandle0
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - fwpkclnt.lib
 - fwpkclnt.dll
api_name:
 - FwpsAcquireClassifyHandle0
---

# FwpsAcquireClassifyHandle0 function


## -description

The 
  <b>FwpsAcquireClassifyHandle0</b> function generates a classification handle that is used to identify
  asynchronous classification operations and requests for writable layer data.
<div class="alert"><b>Note</b>  <b>FwpsAcquireClassifyHandle0</b> is a specific version of <b>FwpsAcquireClassifyHandle</b>. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters

### -param classifyContext 

[in]
The 
     <i>classifyContext</i> parameter from 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_callout_classify_fn1">classifyFn1</a>. The WFP engine passes this
     value to the callout driver's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">classifyFn</a>.

### -param flags 

[in]
Reserved for future use. Set to 0.

### -param classifyHandle 

[out]
A pointer to a variable that receives a classification handle. This handle is needed by subsequent
     function calls as noted in Remarks.

## -returns

The 
     <b>FwpsAcquireClassifyHandle0</b> function returns one of the following NTSTATUS codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
A handle to the classify request was successfully returned. The variable that the 
       <i>classifyHandle</i> parameter points to contains the handle for the classify request.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred.

</td>
</tr>
</table>

## -remarks

<b>FwpsAcquireClassifyHandle0</b> is a support function for asynchronous classification and data
    modification. The handle returned by this function is required as a parameter for the following
    functions:

<ul>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpspendclassify0">FwpsPendClassify0</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsacquirewritablelayerdatapointer0">
       FwpsAcquireWritableLayerDataPointer0</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsapplymodifiedlayerdata0">
       FwpsApplyModifiedLayerData0</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpscompleteclassify0">FwpsCompleteClassify0</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsreleaseclassifyhandle0">FwpsReleaseClassifyHandle0</a>


</li>
</ul>
For each call to this function, the callout driver must call 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsreleaseclassifyhandle0">FwpsReleaseClassifyHandle0</a> to
    free the system resources associated with the handle.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpscompleteclassify0">FwpsCompleteClassify0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpspendclassify0">FwpsPendClassify0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsreleaseclassifyhandle0">FwpsReleaseClassifyHandle0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">classifyFn</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_callout_classify_fn1">classifyFn1</a>

