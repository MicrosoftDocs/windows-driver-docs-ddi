---
UID: NC:fwpsk.FWPS_CALLOUT_CLASSIFY_FN1
title: FWPS_CALLOUT_CLASSIFY_FN1 (fwpsk.h)
description: The filter engine calls a callout's classifyFn1 callout function whenever there is data to be processed by the callout.Note  classifyFn1 is the specific version of classifyFn used in Windows 7 and later.
old-location: netvista\classifyfn1.htm
tech.root: netvista
ms.assetid: 128fd929-6e83-46a0-9475-e459ede58f30
ms.date: 05/02/2018
ms.keywords: FWPS_CALLOUT_CLASSIFY_FN1, FWPS_CALLOUT_CLASSIFY_FN1 callback, classifyFn1, classifyFn1 callback function [Network Drivers Starting with Windows Vista], fwpsk/classifyFn1, netvista.classifyfn1, wfp_ref_2_funct_4_callout_db29c2d0-9b7c-4737-b66f-472c78fff234.xml
ms.topic: callback
f1_keywords:
 - "fwpsk/classifyFn1"
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 7.
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Fwpsk.h
api_name:
- classifyFn1
product:
- Windows
targetos: Windows
req.typenames: 
---

# FWPS_CALLOUT_CLASSIFY_FN1 callback function


## -description


The filter engine calls a callout's 
  <i>classifyFn1</i> callout function whenever there is data to be processed by the callout.
<div class="alert"><b>Note</b>  <i>classifyFn1</i> is the specific version of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_netvista/">classifyFn</a> used in Windows 7 and later. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information. For Windows 8, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nc-fwpsk-fwps_callout_classify_fn2">classifyFn2</a> is available. For Windows Vista, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nc-fwpsk-fwps_callout_classify_fn0">classifyFn0</a> is available.</div><div> </div>

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


### -param *layerData [in, out]

A pointer to a structure that describes the raw data in the layer being filtered. This parameter
     might be <b>NULL</b>, depending on the layer being filtered and the conditions under which the 
     <i>classifyFn1</i> callout function is called. For the stream layer, this parameter points to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/ns-fwpsk-fwps_stream_callout_io_packet0_">
     FWPS_STREAM_CALLOUT_IO_PACKET0</a> structure. For all of the other layers, this parameter points to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure if it is not
     <b>NULL</b>.


### -param *classifyContext [in, optional]

A pointer to context data associated with the callout driver by the filter engine.


### -param *filter [in]

A pointer to an 
     <a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_filter1_">FWPS_FILTER1</a> structure. This structure
     describes the filter that specifies the callout for the filter's action.


### -param flowContext [in]

A UINT64-typed variable that contains the context associated with the data flow. If no context is
     associated with the data flow, then this parameter is zero. If the callout is added to the filter engine
     at a filtering layer that does not support data flows, the 
     <i>classifyFn1</i> callout function should ignore this parameter.


### -param *classifyOut [in, out]

A pointer to an 
     <a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_classify_out0_">FWPS_CLASSIFY_OUT0</a> structure that
     receives any data that the 
     <i>classifyFn1</i> callout function returns to the caller.


## -returns



None.




## -remarks



A callout driver registers a callout's callout functions with the filter engine by calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpscalloutregister1">FwpsCalloutRegister1</a> function.

The filter engine calls a callout's 
    <i>classifyFn1</i> callout function with data to be processed whenever all of the test conditions are true
    for a filter in the filter engine that specifies the callout for the filter's action.

A callout's 
    <i>classifyFn1</i> callout function should clear the FWPS_RIGHT_ACTION_WRITE flag in the 
    <b>rights</b> member of the 
    <a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_classify_out0_">FWPS_CLASSIFY_OUT0</a> structure in any of
    the following situations:

<ul>
<li>
When the 
      <i>classifyFn1</i> callout function sets the 
      <b>actionType</b> member of the 
      <a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_classify_out0_">FWPS_CLASSIFY_OUT0</a> structure to
      FWP_ACTION_BLOCK.

</li>
<li>
When the 
      <i>classifyFn1</i> callout function sets the 
      <b>actionType</b> member of the 
      <a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_classify_out0_">FWPS_CLASSIFY_OUT0</a> structure to
      FWP_ACTION_PERMIT and the FWPS_FILTER_FLAG_CLEAR_ACTION_RIGHT flag is set in the 
      <b>Flags</b> member of the 
      <a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_filter1_">FWPS_FILTER1</a> structure.

</li>
<li>
When a callout has indicated that it intends to modify the clone net buffer list by setting the 
      <i>intendToModify</i> parameter to <b>TRUE</b> in a call to the 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsreferencenetbufferlist0">
      FwpsReferenceNetBufferList0</a> function.

</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/associating-context-with-a-data-flow">Associating Context with a Data Flow</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_netvista/">Callout Driver Callout Functions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/data-logging">Data Logging</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/ns-fwpsk-fwps_callout0_">FWPS_CALLOUT0</a>



<a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_classify_out0_">FWPS_CLASSIFY_OUT0</a>



<a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_filter1_">FWPS_FILTER1</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/ns-fwpsk-fwps_incoming_metadata_values0_">
   FWPS_INCOMING_METADATA_VALUES0</a>



<a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_incoming_values0_">FWPS_INCOMING_VALUES0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpscalloutregister1">FwpsCalloutRegister1</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsreferencenetbufferlist0">FwpsReferenceNetBufferList0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/packet-modification-examples">Packet Modification Examples</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/registering-callouts-with-the-filter-engine">Registering Callouts with the Filter Engine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/using-a-callout-for-deep-inspection-of-stream-data">Using a Callout
    for Deep Inspection of Stream Data</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/using-a-callout-for-deep-inspection">Using a Callout for Deep Inspection</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_netvista/">classifyFn</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nc-fwpsk-fwps_callout_classify_fn0">classifyFn0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nc-fwpsk-fwps_callout_classify_fn2">classifyFn2</a>
 

 

