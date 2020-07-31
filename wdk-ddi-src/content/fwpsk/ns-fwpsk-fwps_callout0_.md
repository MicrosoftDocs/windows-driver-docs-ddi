---
UID: NS:fwpsk.FWPS_CALLOUT0_
title: FWPS_CALLOUT0_ (fwpsk.h)
description: The FWPS_CALLOUT0 structure defines the data that is required for a callout driver to register a callout with the filter engine.Note  FWPS_CALLOUT0 is the specific version of FWPS_CALLOUT used in Windows Vista and later.
old-location: netvista\fwps_callout0.htm
tech.root: netvista
ms.assetid: df6e9980-6c9b-4d01-a1d5-e5242a3ebc66
ms.date: 05/02/2018
keywords: ["FWPS_CALLOUT0_ structure"]
ms.keywords: FWPS_CALLOUT0, FWPS_CALLOUT0 structure [Network Drivers Starting with Windows Vista], FWPS_CALLOUT0_, fwpsk/FWPS_CALLOUT0, netvista.fwps_callout0, wfp_ref_3_struct_3_fwps_A-E_5e9913c4-01d7-4b1c-b2d0-b4a7a28477e2.xml
f1_keywords:
 - "fwpsk/FWPS_CALLOUT0"
 - "FWPS_CALLOUT0"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- fwpsk.h
api_name:
- FWPS_CALLOUT0
targetos: Windows
req.typenames: FWPS_CALLOUT0
---

# FWPS_CALLOUT0_ structure


## -description


The <b>FWPS_CALLOUT0</b> structure defines the data that is required for a callout driver to register a
  callout with the filter engine.
<div class="alert"><b>Note</b>  <b>FWPS_CALLOUT0</b> is the specific version of <b>FWPS_CALLOUT</b> used in Windows Vista and later. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information. For Windows 8, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_callout2_">FWPS_CALLOUT2</a> is available. For Windows 7, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_callout1_">FWPS_CALLOUT1</a> is available.</div><div> </div>

## -struct-fields




### -field calloutKey

A callout driver-defined <b>GUID</b> that uniquely identifies the callout.


### -field flags

Flags that specify callout-specific parameters. Possible flags are:
     





#### FWP_CALLOUT_FLAG_CONDITIONAL_ON_FLOW

A callout driver can specify this flag when registering a callout that will be added at a layer
       that supports data flows. If this flag is specified, the filter engine calls the callout driver's 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_callout_classify_fn0">classifyFn0</a> callout function only if there
       is a context associated with the data flow. A callout driver associates a context with a data flow by
       calling the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsflowassociatecontext0">FwpsFlowAssociateContext0</a> function.



#### FWP_CALLOUT_FLAG_ALLOW_OFFLOAD

A callout driver specifies this flag to indicate that the callout driver's 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_callout_classify_fn0">classifyFn0</a> callout function is unaffected
       by offloading network data processing to offload-capable network interface cards (NICs). If this flag
       is not specified, then offloading of network data processing is disabled for all traffic that is
       processed by any filters that specify the callout for the filter's action.


### -field classifyFn

A pointer to the callout driver's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_callout_classify_fn0">classifyFn0</a> callout function. The filter
     engine calls this function whenever there is network data to be processed by the callout.


### -field notifyFn

A pointer to the callout driver's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_callout_notify_fn0">notifyFn0</a> function. The filter engine calls
     this function to notify the callout driver about events that are associated with the callout.


### -field flowDeleteFn

A pointer to the callout driver's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_callout_flow_delete_notify_fn0">flowDeleteFn</a> callout function. The filter
     engine calls this function whenever a data flow that is being processed by the callout is terminated.
     

If a callout driver does not associate a context with the data flows that the callout processes, then
     this member should be set to <b>NULL</b>.


## -remarks



A callout driver passes a pointer to an initialized <b>FWPS_CALLOUT0</b> structure to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpscalloutregister0">FwpsCalloutRegister0</a> function when it
    registers a callout with the filter engine.

A callout can set the <b>FWP_CALLOUT_FLAG_CONDITIONAL_ON_FLOW</b> flag only for connections on which
    the driver is interested in performing stream inspections. This callout will be ignored on all other
    connections. Performance will be improved and the driver will not have to maintain unnecessary state
    data.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_callout1_">FWPS_CALLOUT1</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_callout2_">FWPS_CALLOUT2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpscalloutregister0">FwpsCalloutRegister0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_callout_classify_fn0">classifyFn0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_callout_flow_delete_notify_fn0">flowDeleteFn</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_callout_notify_fn0">notifyFn0</a>
 

 

