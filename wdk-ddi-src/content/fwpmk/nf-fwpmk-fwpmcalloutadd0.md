---
UID: NF:fwpmk.FwpmCalloutAdd0
title: FwpmCalloutAdd0 function (fwpmk.h)
description: The FwpmCalloutAdd0 function adds a callout to the filter engine.Note  FwpmCalloutAdd0 is a specific version of FwpmCalloutAdd.
old-location: netvista\fwpmcalloutadd0.htm
tech.root: netvista
ms.assetid: f88a31c4-f42c-487d-b6d8-f8f609f2faff
ms.date: 05/02/2018
ms.keywords: FwpmCalloutAdd0, FwpmCalloutAdd0 function [Network Drivers Starting with Windows Vista], fwpmk/FwpmCalloutAdd0, netvista.fwpmcalloutadd0, wfp_ref_2_funct_2_fwpm_b1548682-4f29-467f-916d-fa434260b0ae.xml
f1_keywords:
 - "fwpmk/FwpmCalloutAdd0"
req.header: fwpmk.h
req.include-header: Fwpmk.h
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- fwpkclnt.lib
- fwpkclnt.dll
api_name:
- FwpmCalloutAdd0
product:
- Windows
targetos: Windows
req.typenames: 
---

# FwpmCalloutAdd0 function


## -description


The 
  <b>FwpmCalloutAdd0</b> function adds a callout to the filter engine.
<div class="alert"><b>Note</b>  <b>FwpmCalloutAdd0</b> is a specific version of <b>FwpmCalloutAdd</b>. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters




### -param engineHandle [in]

A handle for an open session to the filter engine. A callout driver calls the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmengineopen0">FwpmEngineOpen0</a> function to open a
     session to the filter engine.


### -param callout [in]

A pointer to a constant 
     <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550076(v=vs.85)">FWPM_CALLOUT0</a> structure that contains the
     data that is required to add the callout to the filter engine.


### -param sd [in, optional]

A pointer to a constant <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_security_descriptor">SECURITY_DESCRIPTOR</a> structure that describes the security descriptor for
     the callout that is being added to the filter engine. This parameter is optional and can be <b>NULL</b>.


### -param id [out, optional]

A pointer to a UINT32-typed variable that receives a run-time identifier that identifies the
     callout in the filter engine. This is the same identifier that is returned when a callout driver
     registers the callout driver's callout functions with the filter engine. The callout driver passes this
     identifier to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmcalloutdeletebyid0">FwpmCalloutDeleteById0</a> function
     when removing the callout from the filter engine. This parameter is optional and can be <b>NULL</b>.


## -returns



The 
     <b>FwpmCalloutAdd0</b> function returns one of the following NTSTATUS codes:

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
The callout was successfully added to the filter engine.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FWP_ALREADY_EXISTS</b></dt>
</dl>
</td>
<td width="60%">
The callout could not be added to the filter engine. A callout already exists in the filter
       engine with an identifier identical to the GUID specified in the 
       <b>calloutKey</b> member of the 
       <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550076(v=vs.85)">FWPM_CALLOUT0</a> structure pointed to by the 
       <i>callout</i> parameter.

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



A callout driver calls the 
    <b>FwpmCalloutAdd0</b> function to add a callout to the filter engine.

Callout drivers do not typically add their callouts to the filter engine. In most situations this is
    handled by a user-mode Windows Filtering Platform management application.

A callout and filters that specify the callout for the filter's action can be added to the filter
    engine before a callout driver registers the callout with the filter engine. In this situation, filters
    with an action type of <b>FWP_ACTION_CALLOUT_TERMINATING</b> or <b>FWP_ACTION_CALLOUT_UNKNOWN</b> are treated as
    <b>FWP_ACTION_BLOCK</b> and filters with an action type of <b>FWP_ACTION_CALLOUT_INSPECTION</b> are ignored until the
    callout is registered with the filter engine.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550076(v=vs.85)">FWPM_CALLOUT0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmcalloutdeletebyid0">FwpmCalloutDeleteById0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmcalloutdeletebykey0">FwpmCalloutDeleteByKey0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmengineopen0">FwpmEngineOpen0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/types-of-callouts">Types of Callouts</a>
 

 

