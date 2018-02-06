---
UID: NF:fwpsk.FwpsClassifyOptionSet0
title: FwpsClassifyOptionSet0 function
author: windows-driver-content
description: The FwpsClassifyOptionSet0 function is called by a callout filter's classifyFn function to specify additional information that affects the characteristics of permitted filtering operations.Note  FwpsClassifyOptionSet0 is a specific version of FwpsClassifyOptionSet. See WFP Version-Independent Names and Targeting Specific Versions of Windows for more information.
old-location: netvista\fwpsclassifyoptionset0.htm
old-project: netvista
ms.assetid: 8653fac0-8b2f-4e77-9588-2854ae168c1a
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: FwpsClassifyOptionSet0 function [Network Drivers Starting with Windows Vista], FwpsClassifyOptionSet0, wfp_ref_2_funct_3_fwps_C_a482e4f1-dc60-450e-8e3f-6ba7da1a4528.xml, netvista.fwpsclassifyoptionset0, fwpsk/FwpsClassifyOptionSet0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Fwpkclnt.lib
-	Fwpkclnt.dll
apiname:
-	FwpsClassifyOptionSet0
product: Windows
targetos: Windows
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---

# FwpsClassifyOptionSet0 function


## -description


The 
  <b>FwpsClassifyOptionSet0</b> function is called by a callout filter's 
  <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> function to specify additional
  information that affects the characteristics of permitted filtering operations.
<div class="alert"><b>Note</b>  <b>FwpsClassifyOptionSet0</b> is a specific version of <b>FwpsClassifyOptionSet</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -syntax


````
NTSTATUS NTAPI FwpsClassifyOptionSet0(
  _In_ const FWPS_INCOMING_METADATA_VALUES0 *inMetadataValues,
  _In_ const FWP_CLASSIFY_OPTION_TYPE       option,
  _In_ const FWP_VALUE0                     *newValue
);
````


## -parameters




### -param inMetadataValues [in]

A pointer to an 
     <a href="..\fwpsk\ns-fwpsk-fwps_incoming_metadata_values0_.md">FWPS_INCOMING_METADATA_VALUES0</a> structure. This structure contains the values for each of the
     metadata fields at the layer that is being filtered.


### -param option [in]

An 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff552428">FWP_CLASSIFY_OPTION_TYPE</a> enumeration
     constant that indicates whether the 
     <i>newValue</i> parameter refers to unicast, multicast, or loose source mapping states, or to data
     time-out values. For more information, see Remarks.


### -param newValue [in]

A pointer to an array of 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff552450">FWP_VALUE0</a> structures. Each structure in the
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
       <a href="https://msdn.microsoft.com/4731b03d-4c51-414b-a07d-0957b9a04db2">
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
       <i>newValue</i> -&gt;
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
       <i>newValue</i> -&gt;
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
    <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> function.

The following are the allowed values of the 
    <i>option</i> parameter and members of the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff552450">FWP_VALUE0</a> structure pointed to by the 
    <i>newValue</i> parameter.
<table>
<tr>
<th><i>option</i> Parameter</th>
<th>
      newValue-&gt;type Value</th>
<th>
      newValue-&gt;uint32 Value</th>
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
FWP_UINT32 &gt; 0

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
FWP_UINT32 &gt; 0

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

<a href="..\fwpsk\ns-fwpsk-fwps_incoming_metadata_values0_.md">
   FWPS_INCOMING_METADATA_VALUES0</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550079">FWPM_CLASSIFY_OPTIONS0</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552428">FWP_CLASSIFY_OPTION_TYPE</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550078">FWPM_CLASSIFY_OPTION0</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552450">FWP_VALUE0</a>

<a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsClassifyOptionSet0 function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

