---
UID: NF:fwpsk.FwpsFlowRemoveContext0
title: FwpsFlowRemoveContext0 function
author: windows-driver-content
description: The FwpsFlowRemoveContext0 function removes a previously associated context from a data flow.Note  FwpsFlowRemoveContext0 is a specific version of FwpsFlowRemoveContext.
old-location: netvista\fwpsflowremovecontext0.htm
old-project: netvista
ms.assetid: edc257bc-2805-47d8-827a-536e5d74793b
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: FwpsFlowRemoveContext0
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
req.alt-api: FwpsFlowRemoveContext0
req.alt-loc: fwpkclnt.lib,fwpkclnt.dll
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
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---

# FwpsFlowRemoveContext0 function



## -description
The 
  <b>FwpsFlowRemoveContext0</b> function removes a previously associated context from a data flow.



## -syntax

````
NTSTATUS NTAPI FwpsFlowRemoveContext0(
  _In_ UINT64 flowId,
  _In_ UINT16 layerId,
  _In_ UINT32 calloutId
);
````


## -parameters

### -param flowId [in]

A run-time identifier that specifies the data flow from which to remove the context. The run-time
     identifier for a data flow is provided to a callout driver through the FWPS_METADATA_FIELD_FLOW_HANDLE
     metadata value that was passed to the callout driver's 
     <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> callout function.


### -param layerId [in]

The run-time identifier for the filtering layer from which the context is being removed. For more
     information, see 
     <a href="https://msdn.microsoft.com/en-us/library/windows/desktop/aa366492">Run-time Filtering Layer
     Identifiers</a>. A callout driver should specify the same identifier that it specified when it called
     the 
     <a href="..\fwpsk\nf-fwpsk-fwpsflowassociatecontext0.md">FwpsFlowAssociateContext0</a> function to associate the context with the data flow.


### -param calloutId [in]

The run-time identifier for the callout in the filter engine. This identifier was returned when
     the callout driver called either the 
     <a href="..\fwpsk\nf-fwpsk-fwpscalloutregister0.md">FwpsCalloutRegister0</a> or 
     <a href="..\fwpsk\nf-fwpsk-fwpscalloutregister1.md">FwpsCalloutRegister1</a> functions to
     register the callout with the filter engine.


## -returns
The 
     <b>FwpsFlowRemoveContext0</b> function returns one of the following NTSTATUS codes.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The context was successfully removed from the data flow.
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>There is no context currently associated with the data flow.
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred.

 


## -remarks
If the 
    <b>FwpsFlowRemoveContext0</b> function returns STATUS_SUCCESS, 
    <b>FwpsFlowRemoveContext0</b> calls the 
    <a href="..\fwpsk\nc-fwpsk-fwps_callout_flow_delete_notify_fn0.md">flowDeleteFn</a> callout function
    synchronously. If 
    <b>FwpsFlowRemoveContext0</b> returns STATUS_PENDING, 
    <b>FwpsFlowRemoveContext0</b> calls 
    <i>flowDeleteFn</i> asynchronously because an active callout classification is in progress.


## -see-also
<dl>
<dt>
<a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a>
</dt>
<dt>
<a href="..\fwpsk\nc-fwpsk-fwps_callout_flow_delete_notify_fn0.md">flowDeleteFn</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpscalloutregister0.md">FwpsCalloutRegister0</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpscalloutregister1.md">FwpsCalloutRegister1</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsflowassociatecontext0.md">FwpsFlowAssociateContext0</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsFlowRemoveContext0 function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

