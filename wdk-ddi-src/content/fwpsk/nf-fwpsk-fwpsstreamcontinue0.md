---
UID: NF:fwpsk.FwpsStreamContinue0
title: FwpsStreamContinue0 function (fwpsk.h)
description: The FwpsStreamContinue0 function resumes the processing of an inbound data stream that was previously deferred.Note  FwpsStreamContinue0 is a specific version of FwpsStreamContinue.
old-location: netvista\fwpsstreamcontinue0.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["FwpsStreamContinue0 function"]
ms.keywords: FwpsStreamContinue0, FwpsStreamContinue0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsStreamContinue0, netvista.fwpsstreamcontinue0, wfp_ref_2_funct_3_fwps_R-Z_c2e0bb3b-854a-4e88-9378-e78e48cb19f2.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - FwpsStreamContinue0
 - fwpsk/FwpsStreamContinue0
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Fwpkclnt.lib
 - Fwpkclnt.dll
api_name:
 - FwpsStreamContinue0
---

# FwpsStreamContinue0 function


## -description

The 
  <b>FwpsStreamContinue0</b> function resumes the processing of an inbound data stream that was previously
  deferred.
<div class="alert"><b>Note</b>  <b>FwpsStreamContinue0</b> is a specific version of <b>FwpsStreamContinue</b>. See <a href="/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters

### -param flowId 

[in]
A run-time identifier that specifies the data flow that is being resumed. The run-time identifier
     for a data flow is provided to a callout driver through the FWPS_METADATA_FIELD_FLOW_HANDLE metadata
     value that the filter engine provided to the callout driver's 
     <a href="/windows-hardware/drivers/ddi/_netvista/">classifyFn</a> callout function.

### -param calloutId 

[in]
The run-time identifier for the callout that deferred the inbound data stream. This identifier was
     returned when the callout driver called either the 
     <a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpscalloutregister0">FwpsCalloutRegister0</a> or 
     <a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpscalloutregister1">FwpsCalloutRegister1</a> functions to
     register the callout with the filter engine.

### -param layerId 

[in]
The run-time identifier for the filtering layer at which the data stream is being processed. This
     value must be either FWPS_LAYER_STREAM_V4 or FWPS_LAYER_STREAM_V6. The run-time identifier for the layer
     at which the data stream is being processed is provided to a callout in the 
     <b>layerId</b> member of the 
     <a href="/windows/win32/api/fwpstypes/ns-fwpstypes-fwps_incoming_values0">FWPS_INCOMING_VALUES0</a> structure that
     the filter engine passed to the callout driver's 
     <a href="/windows-hardware/drivers/ddi/_netvista/">classifyFn</a> callout function.

### -param streamFlags 

[in]
Flags that specify characteristics of the inbound data stream that is being resumed. A callout
     driver should specify the same stream flags that were set in the 
     <b>streamFlags</b> member of the 
     <a href="/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_stream_data0_">FWPS_STREAM_DATA0</a> structure that the
     filter engine passed to the callout driver's 
     <a href="/windows-hardware/drivers/ddi/_netvista/">classifyFn</a> callout function when the
     callout deferred the data stream.

## -returns

The 
     <b>FwpsStreamContinue0</b> function returns one of the following NTSTATUS codes.

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
Processing of the data stream was successfully resumed.

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
    <b>FwpsStreamContinue0</b> function to resume processing an inbound data stream that was previously
    deferred. A data stream is deferred when a callout's 
    <a href="/windows-hardware/drivers/ddi/_netvista/">classifyFn</a> callout function sets the 
    <b>streamAction</b> member of the 
    <a href="/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_stream_callout_io_packet0_">
    FWPS_STREAM_CALLOUT_IO_PACKET0</a> structure to FWPS_STREAM_ACTION_DEFER. The <b>FwpsStreamContinue0</b> function cannot be called from within a callout's <i>classifyFn</i> context.

## -see-also

<a href="/windows/win32/api/fwpstypes/ns-fwpstypes-fwps_incoming_values0">FWPS_INCOMING_VALUES0</a>



<a href="/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_stream_callout_io_packet0_">
   FWPS_STREAM_CALLOUT_IO_PACKET0</a>



<a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpscalloutregister0">FwpsCalloutRegister0</a>



<a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpscalloutregister1">FwpsCalloutRegister1</a>



<a href="/windows-hardware/drivers/ddi/_netvista/">classifyFn</a>
