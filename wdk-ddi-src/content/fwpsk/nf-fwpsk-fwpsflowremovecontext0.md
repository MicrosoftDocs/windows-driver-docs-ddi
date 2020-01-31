---
UID: NF:fwpsk.FwpsFlowRemoveContext0
title: FwpsFlowRemoveContext0 function (fwpsk.h)
description: The FwpsFlowRemoveContext0 function removes a previously associated context from a data flow.Note  FwpsFlowRemoveContext0 is a specific version of FwpsFlowRemoveContext.
old-location: netvista\fwpsflowremovecontext0.htm
tech.root: netvista
ms.assetid: edc257bc-2805-47d8-827a-536e5d74793b
ms.date: 05/02/2018
ms.keywords: FwpsFlowRemoveContext0, FwpsFlowRemoveContext0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsFlowRemoveContext0, netvista.fwpsflowremovecontext0, wfp_ref_2_funct_3_fwps_D-H_97a48a00-87f5-414f-9a6c-fb15873454e1.xml
f1_keywords:
 - "fwpsk/FwpsFlowRemoveContext0"
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
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
- FwpsFlowRemoveContext0
product:
- Windows
targetos: Windows
req.typenames: 
---

# FwpsFlowRemoveContext0 function


## -description


The 
  <b>FwpsFlowRemoveContext0</b> function removes a previously associated context from a data flow.
<div class="alert"><b>Note</b>  <b>FwpsFlowRemoveContext0</b> is a specific version of <b>FwpsFlowRemoveContext</b>. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters




### -param flowId [in]

A run-time identifier that specifies the data flow from which to remove the context. The run-time
     identifier for a data flow is provided to a callout driver through the FWPS_METADATA_FIELD_FLOW_HANDLE
     metadata value that was passed to the callout driver's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">classifyFn</a> callout function.


### -param layerId [in]

The run-time identifier for the filtering layer from which the context is being removed. For more
     information, see 
     <a href="https://docs.microsoft.com/windows/desktop/FWP/management-filtering-layer-identifiers-">Run-time Filtering Layer
     Identifiers</a>. A callout driver should specify the same identifier that it specified when it called
     the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsflowassociatecontext0">FwpsFlowAssociateContext0</a> function to associate the context with the data flow.


### -param calloutId [in]

The run-time identifier for the callout in the filter engine. This identifier was returned when
     the callout driver called either the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpscalloutregister0">FwpsCalloutRegister0</a> or 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpscalloutregister1">FwpsCalloutRegister1</a> functions to
     register the callout with the filter engine.


## -returns



The 
     <b>FwpsFlowRemoveContext0</b> function returns one of the following NTSTATUS codes.

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
The context was successfully removed from the data flow.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
There is no context currently associated with the data flow.

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



If the 
    <b>FwpsFlowRemoveContext0</b> function returns STATUS_SUCCESS, 
    <b>FwpsFlowRemoveContext0</b> calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_callout_flow_delete_notify_fn0">flowDeleteFn</a> callout function
    synchronously. If 
    <b>FwpsFlowRemoveContext0</b> returns STATUS_PENDING, 
    <b>FwpsFlowRemoveContext0</b> calls 
    <i>flowDeleteFn</i> asynchronously because an active callout classification is in progress.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpscalloutregister0">FwpsCalloutRegister0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpscalloutregister1">FwpsCalloutRegister1</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsflowassociatecontext0">FwpsFlowAssociateContext0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">classifyFn</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_callout_flow_delete_notify_fn0">flowDeleteFn</a>
 

 

