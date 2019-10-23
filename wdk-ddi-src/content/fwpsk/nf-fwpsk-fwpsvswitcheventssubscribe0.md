---
UID: NF:fwpsk.FwpsvSwitchEventsSubscribe0
title: FwpsvSwitchEventsSubscribe0 function (fwpsk.h)
description: The FwpsvSwitchEventsSubscribe0 function registers callback entry points for virtual switch layer events such as virtual port creation and deletion.Note  FwpsvSwitchEventsSubscribe0 is a specific version of FwpsvSwitchEventsSubscribe.
old-location: netvista\fwpsvswitcheventssubscribe0.htm
tech.root: netvista
ms.assetid: 479ff048-f57f-42ca-8787-f87ed055fdbf
ms.date: 05/02/2018
ms.keywords: FwpsvSwitchEventsSubscribe0, FwpsvSwitchEventsSubscribe0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsvSwitchEventsSubscribe0, netvista.fwpsvswitcheventssubscribe0
ms.topic: function
f1_keywords:
 - "fwpsk/FwpsvSwitchEventsSubscribe0"
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
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
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: <= PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- fwpkclnt.lib
- fwpkclnt.dll
api_name:
- FwpsvSwitchEventsSubscribe0
product:
- Windows
targetos: Windows
req.typenames: 
---

# FwpsvSwitchEventsSubscribe0 function


## -description


The <b>FwpsvSwitchEventsSubscribe0</b> function registers callback entry points for virtual switch  layer events such as virtual port creation and deletion.<div class="alert"><b>Note</b>  <b>FwpsvSwitchEventsSubscribe0</b> is a specific version of <b>FwpsvSwitchEventsSubscribe</b>. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div>
<div> </div>



## -parameters




### -param providerGuid

The provider GUID.




### -param notifyContext

An optional pointer to a callout driver–supplied context. Event notification functions  pass this parameter back to the driver.


### -param flags

Reserved. Set to zero.


### -param reserved

Reserved. Set to zero.


### -param eventDispatchTable

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_vswitch_event_dispatch_table0_">FWPS_VSWITCH_EVENT_DISPATCH_TABLE</a> structure that defines the callback entry points for virtual switch layer events.


### -param subscriptionId

A pointer to a variable that contains a unique identifier that WFP assigns to the subscription. The caller must return the subscription identifier to WFP with the  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsvswitcheventsunsubscribe0">FwpsvSwitchEventsUnsubscribe0</a> function.


## -returns



The 
     <b>FwpsvSwitchEventsSubscribe0</b> function returns one of the following NTSTATUS codes.

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
A handle to the classify request was successfully returned. The variable that the 
       <i>classifyHandle</i> parameter points to contains the handle for the classify request.

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



A callout driver calls the <b>FwpsvSwitchEventsSubscribe0</b> function to register callback entry points for virtual switch  layer events.

The entry points for the callback notification functions are specified in and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_vswitch_event_dispatch_table0_">FWPS_VSWITCH_EVENT_DISPATCH_TABLE0</a> structure. 

The callout driver must later call 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsvswitcheventsunsubscribe0">FwpsvSwitchEventsUnsubscribe0</a>  to
    free the system resources.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_vswitch_event_dispatch_table0_">FWPS_VSWITCH_EVENT_DISPATCH_TABLE0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsvswitcheventsunsubscribe0">FwpsvSwitchEventsUnsubscribe0</a>
 

 

