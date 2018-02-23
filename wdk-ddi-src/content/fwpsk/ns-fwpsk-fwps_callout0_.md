---
UID: NS:fwpsk.FWPS_CALLOUT0_
title: FWPS_CALLOUT0_
author: windows-driver-content
description: The FWPS_CALLOUT0 structure defines the data that is required for a callout driver to register a callout with the filter engine.Note  FWPS_CALLOUT0 is the specific version of FWPS_CALLOUT used in Windows Vista and later.
old-location: netvista\fwps_callout0.htm
old-project: netvista
ms.assetid: df6e9980-6c9b-4d01-a1d5-e5242a3ebc66
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FWPS_CALLOUT0 structure [Network Drivers Starting with Windows Vista], FWPS_CALLOUT0_, wfp_ref_3_struct_3_fwps_A-E_5e9913c4-01d7-4b1c-b2d0-b4a7a28477e2.xml, netvista.fwps_callout0, FWPS_CALLOUT0, fwpsk/FWPS_CALLOUT0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	fwpsk.h
apiname:
-	FWPS_CALLOUT0
product: Windows
targetos: Windows
req.typenames: FWPS_CALLOUT0
---

# FWPS_CALLOUT0_ structure


## -description


The <b>FWPS_CALLOUT0</b> structure defines the data that is required for a callout driver to register a
  callout with the filter engine.
<div class="alert"><b>Note</b>  <b>FWPS_CALLOUT0</b> is the specific version of <b>FWPS_CALLOUT</b> used in Windows Vista and later. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information. For Windows 8, <a href="..\fwpsk\ns-fwpsk-fwps_callout2_.md">FWPS_CALLOUT2</a> is available. For Windows 7, <a href="..\fwpsk\ns-fwpsk-fwps_callout1_.md">FWPS_CALLOUT1</a> is available.</div><div> </div>

## -syntax


````
typedef struct FWPS_CALLOUT0_ {
  GUID                                calloutKey;
  UINT32                              flags;
  FWPS_CALLOUT_CLASSIFY_FN0           classifyFn;
  FWPS_CALLOUT_NOTIFY_FN0             notifyFn;
  FWPS_CALLOUT_FLOW_DELETE_NOTIFY_FN0 flowDeleteFn;
} FWPS_CALLOUT0;
````


## -struct-fields




### -field calloutKey

A callout driver-defined <b>GUID</b> that uniquely identifies the callout.


### -field flags

Flags that specify callout-specific parameters. Possible flags are:
     





#### FWP_CALLOUT_FLAG_CONDITIONAL_ON_FLOW

A callout driver can specify this flag when registering a callout that will be added at a layer
       that supports data flows. If this flag is specified, the filter engine calls the callout driver's 
       <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn0</a> callout function only if there
       is a context associated with the data flow. A callout driver associates a context with a data flow by
       calling the 
       <a href="..\fwpsk\nf-fwpsk-fwpsflowassociatecontext0.md">FwpsFlowAssociateContext0</a> function.



#### FWP_CALLOUT_FLAG_ALLOW_OFFLOAD

A callout driver specifies this flag to indicate that the callout driver's 
       <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn0</a> callout function is unaffected
       by offloading network data processing to offload-capable network interface cards (NICs). If this flag
       is not specified, then offloading of network data processing is disabled for all traffic that is
       processed by any filters that specify the callout for the filter's action.


### -field classifyFn

A pointer to the callout driver's 
     <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn0</a> callout function. The filter
     engine calls this function whenever there is network data to be processed by the callout.


### -field notifyFn

A pointer to the callout driver's 
     <a href="..\fwpsk\nc-fwpsk-fwps_callout_notify_fn0.md">notifyFn0</a> function. The filter engine calls
     this function to notify the callout driver about events that are associated with the callout.


### -field flowDeleteFn

A pointer to the callout driver's 
     <a href="..\fwpsk\nc-fwpsk-fwps_callout_flow_delete_notify_fn0.md">flowDeleteFn</a> callout function. The filter
     engine calls this function whenever a data flow that is being processed by the callout is terminated.
     

If a callout driver does not associate a context with the data flows that the callout processes, then
     this member should be set to <b>NULL</b>.


## -remarks



A callout driver passes a pointer to an initialized <b>FWPS_CALLOUT0</b> structure to the 
    <a href="..\fwpsk\nf-fwpsk-fwpscalloutregister0.md">FwpsCalloutRegister0</a> function when it
    registers a callout with the filter engine.

A callout can set the <b>FWP_CALLOUT_FLAG_CONDITIONAL_ON_FLOW</b> flag only for connections on which
    the driver is interested in performing stream inspections. This callout will be ignored on all other
    connections. Performance will be improved and the driver will not have to maintain unnecessary state
    data.




## -see-also

<a href="..\fwpsk\nf-fwpsk-fwpscalloutregister0.md">FwpsCalloutRegister0</a>



<a href="..\fwpsk\nc-fwpsk-fwps_callout_flow_delete_notify_fn0.md">flowDeleteFn</a>



<a href="..\fwpsk\nc-fwpsk-fwps_callout_notify_fn0.md">notifyFn0</a>



<a href="..\fwpsk\ns-fwpsk-fwps_callout2_.md">FWPS_CALLOUT2</a>



<a href="..\fwpsk\ns-fwpsk-fwps_callout1_.md">FWPS_CALLOUT1</a>



<a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn0</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_CALLOUT0 structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

