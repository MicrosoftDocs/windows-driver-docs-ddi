---
UID: NF:fwpsk.FwpsStreamContinue0
title: FwpsStreamContinue0 function
author: windows-driver-content
description: The FwpsStreamContinue0 function resumes the processing of an inbound data stream that was previously deferred.Note  FwpsStreamContinue0 is a specific version of FwpsStreamContinue.
old-location: netvista\fwpsstreamcontinue0.htm
old-project: netvista
ms.assetid: 26cf2630-9602-4c70-a326-11e72f188ef9
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , 0, C, F, FwpsStreamContinue0, FwpsStreamContinue0 function [Network Drivers Starting with Windows Vista], S, a, e, fwpsk/FwpsStreamContinue0, i, m, n, netvista.fwpsstreamcontinue0, o, p, r, s, t, u, w, wfp_ref_2_funct_3_fwps_R-Z_c2e0bb3b-854a-4e88-9378-e78e48cb19f2.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Fwpkclnt.lib
-	Fwpkclnt.dll
apiname:
-	FwpsStreamContinue0
product: Windows
targetos: Windows
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---

# FwpsStreamContinue0 function


## -description


The 
  <b>FwpsStreamContinue0</b> function resumes the processing of an inbound data stream that was previously
  deferred.
<div class="alert"><b>Note</b>  <b>FwpsStreamContinue0</b> is a specific version of <b>FwpsStreamContinue</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -syntax


````
NTSTATUS NTAPI FwpsStreamContinue0(
  _In_ UINT64 flowId,
  _In_ UINT32 calloutId,
  _In_ UINT16 layerId,
  _In_ UINT32 streamFlags
);
````


## -parameters




### -param flowId [in]

A run-time identifier that specifies the data flow that is being resumed. The run-time identifier
     for a data flow is provided to a callout driver through the FWPS_METADATA_FIELD_FLOW_HANDLE metadata
     value that the filter engine provided to the callout driver's 
     <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> callout function.


### -param calloutId [in]

The run-time identifier for the callout that deferred the inbound data stream. This identifier was
     returned when the callout driver called either the 
     <a href="..\fwpsk\nf-fwpsk-fwpscalloutregister0.md">FwpsCalloutRegister0</a> or 
     <a href="..\fwpsk\nf-fwpsk-fwpscalloutregister1.md">FwpsCalloutRegister1</a> functions to
     register the callout with the filter engine.


### -param layerId [in]

The run-time identifier for the filtering layer at which the data stream is being processed. This
     value must be either FWPS_LAYER_STREAM_V4 or FWPS_LAYER_STREAM_V6. The run-time identifier for the layer
     at which the data stream is being processed is provided to a callout in the 
     <b>layerId</b> member of the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff552401">FWPS_INCOMING_VALUES0</a> structure that
     the filter engine passed to the callout driver's 
     <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> callout function.


### -param streamFlags [in]

Flags that specify characteristics of the inbound data stream that is being resumed. A callout
     driver should specify the same stream flags that were set in the 
     <b>streamFlags</b> member of the 
     <a href="..\fwpsk\ns-fwpsk-fwps_stream_data0_.md">FWPS_STREAM_DATA0</a> structure that the
     filter engine passed to the callout driver's 
     <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> callout function when the
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
    <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> callout function sets the 
    <b>streamAction</b> member of the 
    <a href="..\fwpsk\ns-fwpsk-fwps_stream_callout_io_packet0_.md">
    FWPS_STREAM_CALLOUT_IO_PACKET0</a> structure to FWPS_STREAM_ACTION_DEFER. The <b>FwpsStreamContinue0</b> function cannot be called from within a callout's <i>classifyFn</i> context.




## -see-also

<a href="..\fwpsk\nf-fwpsk-fwpscalloutregister0.md">FwpsCalloutRegister0</a>



<a href="..\fwpsk\nf-fwpsk-fwpscalloutregister1.md">FwpsCalloutRegister1</a>



<a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552401">FWPS_INCOMING_VALUES0</a>



<a href="..\fwpsk\ns-fwpsk-fwps_stream_callout_io_packet0_.md">
   FWPS_STREAM_CALLOUT_IO_PACKET0</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsStreamContinue0 function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

