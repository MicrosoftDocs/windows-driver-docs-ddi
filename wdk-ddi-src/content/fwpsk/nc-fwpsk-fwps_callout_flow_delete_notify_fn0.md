---
UID: NC:fwpsk.FWPS_CALLOUT_FLOW_DELETE_NOTIFY_FN0
title: FWPS_CALLOUT_FLOW_DELETE_NOTIFY_FN0
author: windows-driver-content
description: The filter engine calls a callout's flowDeleteFn callout function to notify the callout that a data flow that is being processed by the callout is being terminated.
old-location: netvista\flowdeletefn.htm
old-project: netvista
ms.assetid: 65449a23-da5d-4884-b98e-030461eb019a
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: FWPS_CALLOUT_FLOW_DELETE_NOTIFY_FN0, FWPS_CALLOUT_FLOW_DELETE_NOTIFY_FN0 callback, flowDeleteFn, flowDeleteFn callback function [Network Drivers Starting with Windows Vista], fwpsk/flowDeleteFn, netvista.flowdeletefn, wfp_ref_2_funct_4_callout_b89bd091-32f2-4d86-a394-84aa027219f7.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Fwpsk.h
api_name:
-	flowDeleteFn
product: Windows
targetos: Windows
req.typenames: 
---

# FWPS_CALLOUT_FLOW_DELETE_NOTIFY_FN0 callback function


## -description


The filter engine calls a callout's 
  <i>flowDeleteFn</i> callout function to notify the callout that a data flow that is being processed by the
  callout is being terminated.


## -parameters




### -param layerId [in]

The run-time identifier for the filtering layer at which the data flow is being terminated. For
     more information, see 
     <a href="https://msdn.microsoft.com/en-us/library/windows/desktop/aa366492">Run-time Filtering Layer
     Identifiers</a>.


### -param calloutId [in]

The run-time identifier for the callout in the filter engine. This is the same identifier that was
     returned when the callout driver called either the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff551140">FwpsCalloutRegister0</a> or 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff551143">FwpsCalloutRegister1</a> functions to
     register the callout with the filter engine.


### -param flowContext [in]

The most recent context that has been associated with the data flow by a call to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff551165">FwpsFlowAssociateContext0</a> function.


## -returns



None.




## -remarks



A callout driver registers a callout's callout functions with the filter engine by calling either the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff551140">FwpsCalloutRegister0</a> or 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff551143">FwpsCalloutRegister1</a> functions.

The filter engine calls a callout's 
    <i>flowDeleteFn</i> callout function when it terminates a data flow so that the callout can clean up the
    context associated with the data flow. For example, this callout function will be called after an abrupt
    halt from RST, without 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a> being called first. The filter
    engine calls this callout function only if the callout driver associated a context with the data flow.
    The context will be automatically removed from the data flow by the filter engine when the data flow
    terminates.

The filter engine calls a callout's 
    <i>flowDeleteFn</i> callout function only if the callout has been previously added to the filter engine at
    a filtering layer that supports data flows and the callout driver associates a context with the data
    flows that it processes. If a callout driver does not associate a context with the data flows that the
    callout processes, it should not implement a 
    <i>flowDeleteFn</i> callout function for the callout. In this situation, the callout driver should set the
    
    <i>flowDeleteFn</i> member of the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff551224">FWPS_CALLOUT0</a> structure to <b>NULL</b> when it
    registers the callout with the filter engine.

The FWPS_CALLOUT_FLOW_DELETE_NOTIFY_FN0 type is defined as a pointer to the 
    <i>flowDeleteFn</i> function as follows.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef void (NTAPI *FWPS_CALLOUT_FLOW_DELETE_NOTIFY_FN0) flowDeleteFn</pre>
</td>
</tr>
</table></span></div>
The filter engine calls a callout's 
    <i>flowDeleteFn</i> callout function at IRQL &lt;= DISPATCH_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543875">Callout Driver Callout Functions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551224">FWPS_CALLOUT0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551140">FwpsCalloutRegister0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551143">FwpsCalloutRegister1</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551165">FwpsFlowAssociateContext0</a>
 

 

