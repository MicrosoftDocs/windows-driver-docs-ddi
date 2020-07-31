---
UID: NF:fwpsk.FwpsPendClassify0
title: FwpsPendClassify0 function (fwpsk.h)
description: A callout's classifyFn function calls FwpsPendClassify0 to pend the current classify request.
old-location: netvista\fwpspendclassify0.htm
tech.root: netvista
ms.assetid: 8abf967f-776e-4438-b20a-d7c278793633
ms.date: 05/02/2018
keywords: ["FwpsPendClassify0 function"]
ms.keywords: FwpsPendClassify0, FwpsPendClassify0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsPendClassify0, netvista.fwpspendclassify0, wfp_ref_2_funct_3_fwps_J-Q_b0a2ba71-91f1-460c-9b67-d8ddbe25cb44.xml
f1_keywords:
 - "fwpsk/FwpsPendClassify0"
 - "FwpsPendClassify0"
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with  Windows 7.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- fwpkclnt.lib
- fwpkclnt.dll
api_name:
- FwpsPendClassify0
targetos: Windows
req.typenames: 
---

# FwpsPendClassify0 function


## -description


A callout's 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">classifyFn</a> function calls 
  <b>FwpsPendClassify0</b> to pend the current classify request. After the request is pended, the callout driver must complete
  the processing of the classify request asynchronously by calling 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpscompleteclassify0">FwpsCompleteClassify0</a>.
<div class="alert"><b>Note</b>  <b>FwpsPendClassify0</b> is a specific version of <b>FwpsPendClassify</b>. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters




### -param classifyHandle [in]

The classification handle that identifies the callout driver's processing at the current layer.
     This handle is obtained by calling 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsacquireclassifyhandle0">
     FwpsAcquireClassifyHandle0</a>.


### -param filterId [in]

The value of the 
     <b>FilterId</b> member of the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">classifyFn</a> function's 
     <i>filter</i> parameter. For more information about the 
     <b>FilterId</b> member, see 
     <a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_filter1_">FWPS_FILTER1</a>.


### -param flags [in]

Reserved for future use. Set to zero.


### -param classifyOut [in, out]

Set to the 
     <i>classifyOut</i> parameter of the callout driver's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">classifyFn</a> function. The 
     <i>classifyOut</i> parameter of 
     <i>classifyFn</i> is listed as an output parameter in the header, but it contains enough information on
     input to be useful to the engine when passed to 
     <b>FwpsPendClassify</b>.


## -returns



The 
     <b>FwpsPendClassify0</b> function returns one of the following NTSTATUS codes.

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
The classify request was successfully pended.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FWP_CANNOT_PEND</b></dt>
</dl>
</td>
<td width="60%">
The engine does not allow asynchronous classification at the layer from which the call was
       made.

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



<b>FwpsPendClassify0</b> puts the classification of the indicated event in a pended state. A callout
    driver typically pends classification so that more processing can be done outside the scope of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">classifyFn</a> callout function. The callout driver can
    then pass the classification handle and any other pertinent data about the indication to a function with
    less impact on performance than the driver callout functions. When processing is complete, the callout
    must call 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpscompleteclassify0">FwpsCompleteClassify0</a> to remove
    the pended state. At the time of the call to FwpsCompleteClassify, the callout driver must return a
    filled-out 
    <a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_classify_out0_">FWPS_CLASSIFY_OUT0</a> structure just as it
    would in an inline classification.

FwpsPendClassify0 increments the reference count for the classification handle passed in the 
    <i>classifyHandle</i> parameter. After the callout driver calls this function, it can call 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsreleaseclassifyhandle0">
    FwpsReleaseClassifyHandle0</a> to release the local instance. When <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpscompleteclassify0">FwpsCompleteClassify0</a> is called, the
    reference to the handle will be decremented automatically.




## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_classify_out0_">FWPS_CLASSIFY_OUT0</a>



<a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_filter1_">FWPS_FILTER1</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsacquireclassifyhandle0">FwpsAcquireClassifyHandle0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpscompleteclassify0">FwpsCompleteClassify0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsreleaseclassifyhandle0">FwpsReleaseClassifyHandle0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">classifyFn</a>
 

 

