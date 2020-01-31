---
UID: NF:fwpsk.FwpsAcquireWritableLayerDataPointer0
title: FwpsAcquireWritableLayerDataPointer0 function (fwpsk.h)
description: The FwpsAcquireWritableLayerDataPointer0 function returns layer-specific data that can be inspected and changed.Note  FwpsAcquireWritableLayerDataPointer0 is a specific version of FwpsAcquireWritableLayerDataPointer.
old-location: netvista\fwpsacquirewritablelayerdatapointer0.htm
tech.root: netvista
ms.assetid: 79816d01-bf27-49d0-b6f1-083b7e87cc4e
ms.date: 05/02/2018
ms.keywords: FwpsAcquireWritableLayerDataPointer0, FwpsAcquireWritableLayerDataPointer0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsAcquireWritableLayerDataPointer0, netvista.fwpsacquirewritablelayerdatapointer0, wfp_ref_2_funct_3_fwps_A-B_adf2c5a7-ebcb-4c05-aa5a-3b794b60dc74.xml
f1_keywords:
 - "fwpsk/FwpsAcquireWritableLayerDataPointer0"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- fwpkclnt.lib
- fwpkclnt.dll
api_name:
- FwpsAcquireWritableLayerDataPointer0
product:
- Windows
targetos: Windows
req.typenames: 
---

# FwpsAcquireWritableLayerDataPointer0 function


## -description


The 
  <b>FwpsAcquireWritableLayerDataPointer0</b> function returns layer-specific data that can be inspected and
  changed.
<div class="alert"><b>Note</b>  <b>FwpsAcquireWritableLayerDataPointer0</b> is a specific version of <b>FwpsAcquireWritableLayerDataPointer</b>. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters




### -param classifyHandle [in]

A handle for the classify request.
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


### -param writableLayerData [out]

A data buffer that contains the modifiable data for the layer. The supported data types, which are listed in the following Remarks section, are defined as
     structures. On return, the data can be accessed by casting the void pointer to the appropriate structure
     type.


### -param classifyOut [in, out]

Set to the 
     <i>classifyOut</i> parameter of the callout driver's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">classifyFn</a> function. The 
     <i>classifyOut</i> parameter of 
     classifyFn is listed as an output parameter in the header, but it contains enough information on
     input to be useful to the engine when passed to 
     <b>FwpsAcquireWritableLayerDataPointer0</b>.


## -returns



The 
     <b>FwpsAcquireWritableLayerDataPointer0</b> function returns one of the following NTSTATUS codes.

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
The callback function was successfully registered.

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



<b>FwpsAcquireWritableLayerDataPointer0</b> sets the following members of the <a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_classify_out0_">FWPS_CLASSIFY_OUT0</a> structure:<ul>
<li><i>classifyOut</i>-><b>actionType</b> = <b>FWP_ACTION_BLOCK</b></li>
<li><i>classifyOut</i>-><b>rights</b> = ~<b>FWPS_RIGHT_ACTION_WRITE</b></li>
</ul>


For every call to this function, you must make a matching call to 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsapplymodifiedlayerdata0">FwpsApplyModifiedLayerData0</a> to
    finalize the changes that were made, even if your callout driver didn't modify any data. If you do not make the call to <b>FwpsApplyModifiedLayerData0</b>, this could result in the classify not completing correctly.

The following structures are defined to contain modifiable layer data. The pointer set on output as
    the 
    <i>writableLayerData</i> parameter can be cast to one of these types:

<ul>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-_fwps_bind_request0">FWPS_BIND_REQUEST0</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-_fwps_connect_request0">FWPS_CONNECT_REQUEST0</a>


</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-_fwps_bind_request0">FWPS_BIND_REQUEST0</a>



<a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_classify_out0_">FWPS_CLASSIFY_OUT0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-_fwps_connect_request0">FWPS_CONNECT_REQUEST0</a>



<a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_filter1_">FWPS_FILTER1</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsacquireclassifyhandle0">FwpsAcquireClassifyHandle0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsapplymodifiedlayerdata0">FwpsApplyModifiedLayerData0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsreleaseclassifyhandle0">FwpsReleaseClassifyHandle0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">classifyFn</a>
 

 

