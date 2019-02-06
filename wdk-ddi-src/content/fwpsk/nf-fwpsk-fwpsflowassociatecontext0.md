---
UID: NF:fwpsk.FwpsFlowAssociateContext0
title: FwpsFlowAssociateContext0 function (fwpsk.h)
description: The FwpsFlowAssociateContext0 function associates a callout driver-defined context with a data flow.Note  FwpsFlowAssociateContext0 is a specific version of FwpsFlowAssociateContext.
old-location: netvista\fwpsflowassociatecontext0.htm
tech.root: netvista
ms.assetid: 0a339457-77df-480b-adb8-9406507ec8d8
ms.date: 05/02/2018
ms.keywords: FwpsFlowAssociateContext0, FwpsFlowAssociateContext0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsFlowAssociateContext0, netvista.fwpsflowassociatecontext0, wfp_ref_2_funct_3_fwps_D-H_a700b313-fb1e-4b66-a3be-837b1a2d89b3.xml
ms.topic: function
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	fwpkclnt.lib
-	fwpkclnt.dll
api_name:
-	FwpsFlowAssociateContext0
product:
- Windows
targetos: Windows
req.typenames: 
---

# FwpsFlowAssociateContext0 function


## -description


The 
  <b>FwpsFlowAssociateContext0</b> function associates a callout driver-defined context with a data
  flow.
<div class="alert"><b>Note</b>  <b>FwpsFlowAssociateContext0</b> is a specific version of <b>FwpsFlowAssociateContext</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters




### -param flowId [in]

A run-time identifier that specifies the data flow with which to associate the context. The
     run-time identifier for a data flow is provided to a callout driver through the
     FWPS_METADATA_FIELD_FLOW_HANDLE metadata value that was passed to the callout driver's 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a> callout function.


### -param layerId [in]

The run-time identifier for the filtering layer with which the context is being associated. The context will be associated only with the specified filtering layer. For
     more information, see 
     <a href="https://msdn.microsoft.com/library/windows/desktop/aa366492">Run-time Filtering Layer
     Identifiers</a>.


### -param calloutId [in]

The run-time identifier for the callout in the filter engine. This identifier was returned when
     the callout driver called the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff551140">FwpsCalloutRegister0</a>, 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff551143">FwpsCalloutRegister1</a>, or  <a href="https://msdn.microsoft.com/library/windows/hardware/hh439576">FwpsCalloutRegister2</a> function to
     register the callout with the filter engine.


### -param flowContext [in]

The callout driver-defined context to be associated with the data flow. This parameter must not be
     zero. This context is opaque to the filter engine.


## -returns



The 
     <b>FwpsFlowAssociateContext0</b> function returns one of the following NTSTATUS codes.

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
The context was successfully associated with the data flow.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Either the <i>flowContext</i> parameter is <b>NULL</b> or the callout specified by the <i>calloutID</i> parameter does not have a <a href="https://msdn.microsoft.com/65449a23-da5d-4884-b98e-030461eb019a">flowDeleteFn</a> registered.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_EXISTS</b></dt>
</dl>
</td>
<td width="60%">
A context is already associated with the data flow. In this case, a callout driver should first
       call the 
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff551169">FwpsFlowRemoveContext0</a> function
       to remove the existing context and then call the 
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff551165">FwpsFlowAssociateContext0</a> function again to associate the new context with the data flow.

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



When filtering a data flow, a callout driver can call the 
    <b>FwpsFlowAssociateContext0</b> function to associate a context with the data flow. It can then use this
    context to preserve any driver-specific data or state information between calls by the filter engine to a
    callout's 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a> callout function for that data
    flow.

There must be a callout in the filter engine at the layer identified by the 
    <i>layerId</i> parameter that has registered a 
    <a href="https://msdn.microsoft.com/65449a23-da5d-4884-b98e-030461eb019a">flowDeleteFn</a> callout function. Otherwise,
    the call to the 
    <b>FwpsFlowAssociateContext0</b> function will return STATUS_INVALID_PARAMETER. The filter engine calls that 
    <i>flowDeleteFn</i> callout function when the flow is terminated so that the callout driver can clean up
    the context associated with the flow.

You can call <b>FwpsFlowAssociateContext0</b> multiple times for the same flow. In each call, you must specify a different callout and a different context—one context per added callout.

The <b>FwpsFlowAssociateContext0</b> function associates a single context with a single added callout.

You can associate multiple contexts with a flow. However, each context must be associated with a different callout. The new callout can be at the same layer as the previous one or at a different layer.

For more information and sample code, see <a href="https://msdn.microsoft.com/75f5838e-626d-4a59-810e-fec9a40640ed">Associating Context with a Data Flow</a>
and the <a href="https://go.microsoft.com/fwlink/p/?LinkId=618934">Windows Filtering Platform Sample</a>.




## -see-also




<a href="https://msdn.microsoft.com/75f5838e-626d-4a59-810e-fec9a40640ed">Associating Context with a Data Flow</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551140">FwpsCalloutRegister0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551143">FwpsCalloutRegister1</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439576">FwpsCalloutRegister2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551169">FwpsFlowRemoveContext0</a>



<a href="https://go.microsoft.com/fwlink/p/?LinkId=618934">Windows Filtering Platform Sample</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a>



<a href="https://msdn.microsoft.com/65449a23-da5d-4884-b98e-030461eb019a">flowDeleteFn</a>
 

 

