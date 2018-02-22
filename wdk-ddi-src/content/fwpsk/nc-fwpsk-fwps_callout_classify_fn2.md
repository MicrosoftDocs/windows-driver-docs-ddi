---
UID: NC:fwpsk.FWPS_CALLOUT_CLASSIFY_FN2
title: FWPS_CALLOUT_CLASSIFY_FN2
author: windows-driver-content
description: The filter engine calls a callout's classifyFn2 callout function whenever there is data to be processed by the callout.Note  classifyFn2 is the specific version of classifyFn used in Windows 8 and later.
old-location: netvista\classifyfn2.htm
old-project: netvista
ms.assetid: de8220de-cf71-4718-876e-ef02c15fc948
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.classifyfn2, classifyFn2 callback function [Network Drivers Starting with Windows Vista], classifyFn2, FWPS_CALLOUT_CLASSIFY_FN2, FWPS_CALLOUT_CLASSIFY_FN2, fwpsk/classifyFn2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Fwpsk.h
apiname:
-	classifyFn2
product: Windows
targetos: Windows
req.typenames: INSTANCE_PARTIAL_INFORMATION, PINSTANCE_PARTIAL_INFORMATION
---

# FWPS_CALLOUT_CLASSIFY_FN2 callback


## -description


The filter engine calls a callout's 
  <i>classifyFn2</i> callout function whenever there is data to be processed by the callout.<div class="alert"><b>Note</b>  <i>classifyFn2</i> is the specific version of <a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a> used in Windows 8 and later. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information. For Windows 7, <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn1.md">classifyFn1</a> is available. For Windows Vista, <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn0</a> is available.</div>
<div> </div>



## -prototype


````
FWPS_CALLOUT_CLASSIFY_FN2 classifyFn2;

void NTAPI classifyFn2(
  _In_        const FWPS_INCOMING_VALUES0          *inFixedValues,
  _In_        const FWPS_INCOMING_METADATA_VALUES0 *inMetaValues,
  _Inout_opt_       void                           *layerData,
  _In_opt_    const void                           *classifyContext,
  _In_        const FWPS_FILTER2                   *filter,
  _In_              UINT64                         flowContext,
  _Inout_           FWPS_CLASSIFY_OUT0             *classifyOut
)
{ ... }
````


## -parameters




### -param *inFixedValues [in]

A pointer to an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff552401">FWPS_INCOMING_VALUES0</a> structure. This
     structure contains the values for each of the data fields in the layer being filtered.


### -param *inMetaValues [in]

A pointer to an 
     <a href="..\fwpsk\ns-fwpsk-fwps_incoming_metadata_values0_.md">
     FWPS_INCOMING_METADATA_VALUES0</a> structure. This structure contains the values for each of the
     metadata fields in the layer being filtered.


### -param *layerData [in, out, optional]

A pointer to a structure that describes the raw data in the layer being filtered. This parameter
     might be NULL, depending on the layer being filtered and the conditions under which the 
     <i>classifyFn2</i> callout function is called. For the stream layer, this parameter points to an 
     <a href="..\fwpsk\ns-fwpsk-fwps_stream_callout_io_packet0_.md">
     FWPS_STREAM_CALLOUT_IO_PACKET0</a> structure. For all of the other layers, this parameter points to a 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure if it is not
     NULL.


### -param *classifyContext [in, optional]

A pointer to context data associated with the callout driver by the filter engine.


### -param *filter [in]

A pointer to an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/hh439768">FWPS_FILTER2</a> structure. This structure
     describes the filter that specifies the callout for the filter's action.


### -param flowContext [in]

A UINT64-typed variable that contains the context associated with the data flow. If no context is
     associated with the data flow, then this parameter is zero. If the callout is added to the filter engine
     at a filtering layer that does not support data flows, the 
     <i>classifyFn2</i> callout function should ignore this parameter.


### -param *classifyOut [in, out]

A pointer to an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff551229">FWPS_CLASSIFY_OUT0</a> structure that
     receives any data that the 
     <i>classifyFn2</i> callout function returns to the caller.


## -returns



None




## -remarks



A callout driver registers a callout's callout functions with the filter engine by calling the 
    <a href="..\fwpsk\nf-fwpsk-fwpscalloutregister2.md">FwpsCalloutRegister2</a> function.

The filter engine calls a callout's 
    <i>classifyFn2</i> callout function with data to be processed whenever all of the test conditions are true
    for a filter in the filter engine that specifies the callout for the filter's action.

A callout's 
    <i>classifyFn2</i> callout function should clear the FWPS_RIGHT_ACTION_WRITE flag in the 
    <b>rights</b> member of the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff551229">FWPS_CLASSIFY_OUT0</a> structure in any of
    the following situations:

<ul>
<li>
When the 
      <i>classifyFn2</i> callout function sets the 
      <b>actionType</b> member of the 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff551229">FWPS_CLASSIFY_OUT0</a> structure to
      FWP_ACTION_BLOCK.

</li>
<li>
When the 
      <i>classifyFn2</i> callout function sets the 
      <b>actionType</b> member of the 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff551229">FWPS_CLASSIFY_OUT0</a> structure to
      FWP_ACTION_PERMIT and the FWPS_FILTER_FLAG_CLEAR_ACTION_RIGHT flag is set in the 
      <b>Flags</b> member of the 
      <a href="https://msdn.microsoft.com/library/windows/hardware/hh439768">FWPS_FILTER2</a> structure.

</li>
<li>
When a callout has indicated that it intends to modify the clone net buffer list by setting the 
      <i>intendToModify</i> parameter to TRUE in a call to the 
      <a href="..\fwpsk\nf-fwpsk-fwpsreferencenetbufferlist0.md">
      FwpsReferenceNetBufferList0</a> function.

This function is essentially identical to the previous version, 
    <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn1.md">classifyFn1</a>. However, the updated <a href="https://msdn.microsoft.com/library/windows/hardware/hh439768">FWPS_FILTER2</a> structure is pointed to by the 
       <i>filter</i> parameter and the <i>layerData</i> parameter is optional.

</li>
</ul>



## -see-also

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/using-a-callout-for-deep-inspection-of-stream-data">Using a Callout
    for Deep Inspection of Stream Data</a>



<a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543875">Callout Driver Callout Functions</a>



<a href="https://msdn.microsoft.com/75f5838e-626d-4a59-810e-fec9a40640ed">Associating Context with a Data Flow</a>



<a href="..\fwpsk\nf-fwpsk-fwpscalloutregister2.md">FwpsCalloutRegister2</a>



<a href="https://msdn.microsoft.com/464c74ae-5e37-41f1-b305-ef57039b28ba">Using a Callout for Deep Inspection</a>



<a href="https://msdn.microsoft.com/a5bade33-e3d1-4e1d-8503-51485097046e">Registering Callouts with the Filter Engine</a>



<a href="https://msdn.microsoft.com/1e4f00e0-0fc6-459d-bbdd-02fbca5b9945">Data Logging</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551229">FWPS_CLASSIFY_OUT0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439768">FWPS_FILTER2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a>



<a href="https://msdn.microsoft.com/dec76575-041b-4cbd-8042-184b15354f61">Packet Modification Examples</a>



<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="..\fwpsk\nf-fwpsk-fwpsreferencenetbufferlist0.md">FwpsReferenceNetBufferList0</a>



<a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn1.md">classifyFn1</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552401">FWPS_INCOMING_VALUES0</a>



<a href="..\fwpsk\ns-fwpsk-fwps_incoming_metadata_values0_.md">
   FWPS_INCOMING_METADATA_VALUES0</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_CALLOUT_CLASSIFY_FN2 callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

