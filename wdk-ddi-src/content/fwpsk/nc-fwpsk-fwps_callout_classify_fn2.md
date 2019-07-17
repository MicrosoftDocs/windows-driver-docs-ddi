---
UID: NC:fwpsk.FWPS_CALLOUT_CLASSIFY_FN2
title: FWPS_CALLOUT_CLASSIFY_FN2 (fwpsk.h)
description: The filter engine calls a callout's classifyFn2 callout function whenever there is data to be processed by the callout.Note  classifyFn2 is the specific version of classifyFn used in Windows 8 and later.
old-location: netvista\classifyfn2.htm
tech.root: netvista
ms.assetid: de8220de-cf71-4718-876e-ef02c15fc948
ms.date: 05/02/2018
ms.keywords: FWPS_CALLOUT_CLASSIFY_FN2, FWPS_CALLOUT_CLASSIFY_FN2 callback, classifyFn2, classifyFn2 callback function [Network Drivers Starting with Windows Vista], fwpsk/classifyFn2, netvista.classifyfn2
ms.topic: callback
f1_keywords:
 - "fwpsk/classifyFn2"
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Fwpsk.h
api_name:
- classifyFn2
product:
- Windows
targetos: Windows
req.typenames: 
---

# FWPS_CALLOUT_CLASSIFY_FN2 callback function


## -description


The filter engine calls a callout's 
  <i>classifyFn2</i> callout function whenever there is data to be processed by the callout.<div class="alert"><b>Note</b>  <i>classifyFn2</i> is the specific version of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_netvista/">classifyFn</a> used in Windows 8 and later. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information. For Windows 7, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nc-fwpsk-fwps_callout_classify_fn1">classifyFn1</a> is available. For Windows Vista, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nc-fwpsk-fwps_callout_classify_fn0">classifyFn0</a> is available.</div>
<div> </div>



## -parameters




### -param *inFixedValues [in]

A pointer to an 
     <a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_incoming_values0_">FWPS_INCOMING_VALUES0</a> structure. This
     structure contains the values for each of the data fields in the layer being filtered.


### -param *inMetaValues [in]

A pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/ns-fwpsk-fwps_incoming_metadata_values0_">
     FWPS_INCOMING_METADATA_VALUES0</a> structure. This structure contains the values for each of the
     metadata fields in the layer being filtered.


### -param *layerData [in, out, optional]

A pointer to a structure that describes the raw data in the layer being filtered. This parameter
     might be NULL, depending on the layer being filtered and the conditions under which the 
     <i>classifyFn2</i> callout function is called. For the stream layer, this parameter points to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/ns-fwpsk-fwps_stream_callout_io_packet0_">
     FWPS_STREAM_CALLOUT_IO_PACKET0</a> structure. For all of the other layers, this parameter points to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure if it is not
     NULL.


### -param *classifyContext [in, optional]

A pointer to context data associated with the callout driver by the filter engine.


### -param *filter [in]

A pointer to an 
     <a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_filter2_">FWPS_FILTER2</a> structure. This structure
     describes the filter that specifies the callout for the filter's action.


### -param flowContext [in]

A UINT64-typed variable that contains the context associated with the data flow. If no context is
     associated with the data flow, then this parameter is zero. If the callout is added to the filter engine
     at a filtering layer that does not support data flows, the 
     <i>classifyFn2</i> callout function should ignore this parameter.


### -param *classifyOut [in, out]

A pointer to an 
     <a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_classify_out0_">FWPS_CLASSIFY_OUT0</a> structure that
     receives any data that the 
     <i>classifyFn2</i> callout function returns to the caller.


## -returns



None




## -remarks



A callout driver registers a callout's callout functions with the filter engine by calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpscalloutregister2">FwpsCalloutRegister2</a> function.

The filter engine calls a callout's 
    <i>classifyFn2</i> callout function with data to be processed whenever all of the test conditions are true
    for a filter in the filter engine that specifies the callout for the filter's action.

A callout's 
    <i>classifyFn2</i> callout function should clear the FWPS_RIGHT_ACTION_WRITE flag in the 
    <b>rights</b> member of the 
    <a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_classify_out0_">FWPS_CLASSIFY_OUT0</a> structure in any of
    the following situations:

<ul>
<li>
When the 
      <i>classifyFn2</i> callout function sets the 
      <b>actionType</b> member of the 
      <a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_classify_out0_">FWPS_CLASSIFY_OUT0</a> structure to
      FWP_ACTION_BLOCK.

</li>
<li>
When the 
      <i>classifyFn2</i> callout function sets the 
      <b>actionType</b> member of the 
      <a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_classify_out0_">FWPS_CLASSIFY_OUT0</a> structure to
      FWP_ACTION_PERMIT and the FWPS_FILTER_FLAG_CLEAR_ACTION_RIGHT flag is set in the 
      <b>Flags</b> member of the 
      <a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_filter2_">FWPS_FILTER2</a> structure.

</li>
<li>
When a callout has indicated that it intends to modify the clone net buffer list by setting the 
      <i>intendToModify</i> parameter to TRUE in a call to the 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsreferencenetbufferlist0">
      FwpsReferenceNetBufferList0</a> function.

This function is essentially identical to the previous version, 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nc-fwpsk-fwps_callout_classify_fn1">classifyFn1</a>. However, the updated <a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_filter2_">FWPS_FILTER2</a> structure is pointed to by the 
       <i>filter</i> parameter and the <i>layerData</i> parameter is optional.

</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/associating-context-with-a-data-flow">Associating Context with a Data Flow</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_netvista/">Callout Driver Callout Functions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/data-logging">Data Logging</a>



<a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_classify_out0_">FWPS_CLASSIFY_OUT0</a>



<a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_filter2_">FWPS_FILTER2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/ns-fwpsk-fwps_incoming_metadata_values0_">
   FWPS_INCOMING_METADATA_VALUES0</a>



<a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_incoming_values0_">FWPS_INCOMING_VALUES0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpscalloutregister2">FwpsCalloutRegister2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsreferencenetbufferlist0">FwpsReferenceNetBufferList0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/packet-modification-examples">Packet Modification Examples</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/registering-callouts-with-the-filter-engine">Registering Callouts with the Filter Engine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/using-a-callout-for-deep-inspection-of-stream-data">Using a Callout
    for Deep Inspection of Stream Data</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/using-a-callout-for-deep-inspection">Using a Callout for Deep Inspection</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_netvista/">classifyFn</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nc-fwpsk-fwps_callout_classify_fn0">classifyFn0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nc-fwpsk-fwps_callout_classify_fn1">classifyFn1</a>
 

 

