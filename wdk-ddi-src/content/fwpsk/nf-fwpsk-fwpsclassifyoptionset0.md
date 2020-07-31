---
UID: NF:fwpsk.FwpsClassifyOptionSet0
title: FwpsClassifyOptionSet0 function (fwpsk.h)
description: The FwpsClassifyOptionSet0 function is called by a callout filter's classifyFn function to specify additional information that affects the characteristics of permitted filtering operations.Note  FwpsClassifyOptionSet0 is a specific version of FwpsClassifyOptionSet. See WFP Version-Independent Names and Targeting Specific Versions of Windows for more information.
old-location: netvista\fwpsclassifyoptionset0.htm
tech.root: netvista
ms.assetid: 8653fac0-8b2f-4e77-9588-2854ae168c1a
ms.date: 05/02/2018
keywords: ["FwpsClassifyOptionSet0 function"]
ms.keywords: FwpsClassifyOptionSet0, FwpsClassifyOptionSet0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsClassifyOptionSet0, netvista.fwpsclassifyoptionset0, wfp_ref_2_funct_3_fwps_C_a482e4f1-dc60-450e-8e3f-6ba7da1a4528.xml
f1_keywords:
 - "fwpsk/FwpsClassifyOptionSet0"
 - "FwpsClassifyOptionSet0"
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
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
- Fwpkclnt.lib
- Fwpkclnt.dll
api_name:
- FwpsClassifyOptionSet0
targetos: Windows
req.typenames: 
---

# FwpsClassifyOptionSet0 function


## -description


The 
  <b>FwpsClassifyOptionSet0</b> function is called by a callout filter's 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">classifyFn</a> function to specify additional
  information that affects the characteristics of permitted filtering operations.
<div class="alert"><b>Note</b>  <b>FwpsClassifyOptionSet0</b> is a specific version of <b>FwpsClassifyOptionSet</b>. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters




### -param inMetadataValues [in]

A pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_incoming_metadata_values0_">FWPS_INCOMING_METADATA_VALUES0</a> structure. This structure contains the values for each of the
     metadata fields at the layer that is being filtered.


### -param option [in]

An 
     <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff552428(v=vs.85)">FWP_CLASSIFY_OPTION_TYPE</a> enumeration
     constant that indicates whether the 
     <i>newValue</i> parameter refers to unicast, multicast, or loose source mapping states, or to data
     time-out values. For more information, see Remarks.


### -param newValue [in]

A pointer to an array of 
     <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff552450(v=vs.85)">FWP_VALUE0</a> structures. Each structure in the
     array contains particular values for a particular FWP_OPTION_VALUE_XXX constant. For more information, see
     Remarks.


## -returns



The 
     <b>FwpsClassifyOptionSet0</b> function returns one of the following NTSTATUS codes.

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
The function completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FWP_INVALID_ENUMERATOR</b></dt>
</dl>
</td>
<td width="60%">
The 
       <i>option</i> parameter does not match any of the values in the 
       <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff552428(v=vs.85)">
       FWP_CLASSIFY_OPTION_TYPE</a> enumeration.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FWP_OUT_OF_BOUNDS</b></dt>
</dl>
</td>
<td width="60%">
The option value specified by 
       <i>newValue</i> ->
       <b>uint32</b> does not include one of the defined FWP_OPTION_VALUE_XXX constant values.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The data type specified by 
       <i>newValue</i> ->
       <b>Type</b> was not FWP_UINT32.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
A general error occurred.

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



This function should be called only by a callout filter's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">classifyFn</a> function.

The following are the allowed values of the 
    <i>option</i> parameter and members of the 
    <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff552450(v=vs.85)">FWP_VALUE0</a> structure pointed to by the 
    <i>newValue</i> parameter.

<table>
<tr>
<th><i>option</i> Parameter</th>
<th>
      newValue->type Value</th>
<th>
      newValue->uint32 Value</th>
</tr>
<tr>
<td>
FWP_CLASSIFY_OPTION_LOOSE_SOURCE_MAPPING

</td>
<td>
FWP_UINT32

</td>
<td>
FWP_OPTION_VALUE_ENABLE_LOOSE_SOURCE
       <dl>
<dd>Enable loose source mapping.</dd>
</dl>


FWP_OPTION_VALUE_DISABLE_LOOSE_SOURCE
       <dl>
<dd>Disable loose source mapping.</dd>
</dl>


</td>
</tr>
<tr>
<td>
FWP_CLASSIFY_OPTION_MULTICAST_STATE

</td>
<td>
FWP_UINT32

</td>
<td>
FWP_OPTION_VALUE_ALLOW_MULTICAST_STATE
       <dl>
<dd>Allow link-local multicast state creation on outbound traffic.</dd>
</dl>


FWP_OPTION_VALUE_DENY_MULTICAST_STATE
       <dl>
<dd>Do not allow link-local multicast state creation on outbound traffic.</dd>
</dl>


FWP_OPTION_VALUE_ALLOW_NON_LINK_LOCAL_RESPONSE
       <dl>
<dd>Allow multicast state creation for outbound traffic (permitting non–link-local
        responses).</dd>
</dl>


</td>
</tr>
<tr>
<td>
FWP_CLASSIFY_OPTION_MCAST_BCAST_LIFETIME

</td>
<td>
FWP_UINT32 > 0

</td>
<td>
Specifies the multicast/broadcast state lifetime, in seconds.

</td>
</tr>
<tr>
<td>
FWP_CLASSIFY_OPTION_UNICAST_LIFETIME

</td>
<td>
FWP_UINT32 > 0

</td>
<td>
Specifies the unicast state lifetime, in seconds.

</td>
</tr>
</table>
 

The first (highest weight) caller to set a particular option will be granted that option. For example,
    if callout A sets the multicast state option, callout B will not be able to do so, but callout B can set
    other options.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550078(v=vs.85)">FWPM_CLASSIFY_OPTION0</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550079(v=vs.85)">FWPM_CLASSIFY_OPTIONS0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_incoming_metadata_values0_">
   FWPS_INCOMING_METADATA_VALUES0</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff552428(v=vs.85)">FWP_CLASSIFY_OPTION_TYPE</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff552450(v=vs.85)">FWP_VALUE0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">classifyFn</a>
 

 

