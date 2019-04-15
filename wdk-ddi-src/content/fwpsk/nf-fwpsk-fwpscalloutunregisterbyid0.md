---
UID: NF:fwpsk.FwpsCalloutUnregisterById0
title: FwpsCalloutUnregisterById0 function (fwpsk.h)
description: The FwpsCalloutUnregisterById0 function unregisters a callout from the filter engine.Note  FwpsCalloutUnregisterById0 is a specific version of FwpsCalloutUnregisterById.
old-location: netvista\fwpscalloutunregisterbyid0.htm
tech.root: netvista
ms.assetid: 81e7e704-c387-48a0-a222-cae751bba1d3
ms.date: 05/02/2018
ms.keywords: FwpsCalloutUnregisterById0, FwpsCalloutUnregisterById0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsCalloutUnregisterById0, netvista.fwpscalloutunregisterbyid0, wfp_ref_2_funct_3_fwps_C_7bfae7f1-e5f2-4361-bbc0-6c5fef63a267.xml
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
- FwpsCalloutUnregisterById0
product:
- Windows
targetos: Windows
req.typenames: 
---

# FwpsCalloutUnregisterById0 function


## -description


The 
  <b>FwpsCalloutUnregisterById0</b> function unregisters a callout from the filter engine.
<div class="alert"><b>Note</b>  <b>FwpsCalloutUnregisterById0</b> is a specific version of <b>FwpsCalloutUnregisterById</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters




### -param calloutId [in]

The run-time identifier for the callout that is being unregistered from the filter engine. This
     must be the run-time identifier that was returned when the callout driver called either the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff551140">FwpsCalloutRegister0</a> or 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff551143">FwpsCalloutRegister1</a> function to
     register the callout with the filter engine.


## -returns



The 
     <b>FwpsCalloutUnregisterById0</b> function returns one of the following NTSTATUS codes.

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
The callout was successfully unregistered from the filter engine.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_BUSY</b></dt>
</dl>
</td>
<td width="60%">
There are one or more data flows being processed by the callout that have an outstanding context
       associated with the data flow. A callout driver must call the 
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff551169">FwpsFlowRemoveContext0</a> function
       for each of these data flows to remove the associated context. After the context has been successfully
       removed from each of these data flows, the callout driver must call the 
       <b>FwpsCalloutUnregisterById0</b> function again to finish unregistering the callout from the filter
       engine.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FWP_CALLOUT_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
There is not a callout registered with the filter engine that matches the run-time identifier
       specified in the 
       <i>calloutId</i> parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FWP_IN_USE</b></dt>
</dl>
</td>
<td width="60%">
The callout is already in the process of being registered or unregistered in another
       thread.

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
    <b>FwpsCalloutUnregisterById0</b> function to unregister a callout from the filter engine, using the
    run-time identifier to identify the callout to be unregistered. This function succeeds even if there
    are filters in the filter engine that specify the callout for the filter's action. In this situation,
    filters with an action type of <b>FWP_ACTION_CALLOUT_TERMINATING</b> or <b>FWP_ACTION_CALLOUT_UNKNOWN</b> are treated
    as <b>FWP_ACTION_BLOCK</b>, and filters with an action type of <b>FWP_ACTION_CALLOUT_INSPECTION</b> are ignored after
    the callout has been deregistered from the filter engine.

A callout driver cannot be unloaded until all of the callouts that were previously registered with the
    filter engine have been successfully unregistered.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551140">FwpsCalloutRegister0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551143">FwpsCalloutRegister1</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551145">FwpsCalloutUnregisterByKey0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551169">FwpsFlowRemoveContext0</a>



<a href="https://msdn.microsoft.com/d9539403-7657-4e95-8791-309673d1207d">Types of Callouts</a>
 

 

