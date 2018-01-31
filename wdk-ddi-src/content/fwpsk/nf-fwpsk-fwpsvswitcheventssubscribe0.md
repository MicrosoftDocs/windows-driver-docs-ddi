---
UID: NF:fwpsk.FwpsvSwitchEventsSubscribe0
title: FwpsvSwitchEventsSubscribe0 function
author: windows-driver-content
description: The FwpsvSwitchEventsSubscribe0 function registers callback entry points for virtual switch layer events such as virtual port creation and deletion.Note  FwpsvSwitchEventsSubscribe0 is a specific version of FwpsvSwitchEventsSubscribe.
old-location: netvista\fwpsvswitcheventssubscribe0.htm
old-project: netvista
ms.assetid: 479ff048-f57f-42ca-8787-f87ed055fdbf
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: fwpsk/FwpsvSwitchEventsSubscribe0, netvista.fwpsvswitcheventssubscribe0, FwpsvSwitchEventsSubscribe0 function [Network Drivers Starting with Windows Vista], FwpsvSwitchEventsSubscribe0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= PASSIVE_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	fwpkclnt.lib
-	fwpkclnt.dll
apiname:
-	FwpsvSwitchEventsSubscribe0
product: Windows
targetos: Windows
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---

# FwpsvSwitchEventsSubscribe0 function


## -description


The <b>FwpsvSwitchEventsSubscribe0</b> function registers callback entry points for virtual switch  layer events such as virtual port creation and deletion.<div class="alert"><b>Note</b>  <b>FwpsvSwitchEventsSubscribe0</b> is a specific version of <b>FwpsvSwitchEventsSubscribe</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div>
<div> </div>



## -syntax


````
NTSTATUS NTAPI FwpsvSwitchEventsSubscribe0(
   _In_opt_ const GUID                          *providerGuid,
   _In_opt_ void                                *notifyContext,
   _In_ _Reserved_ UINT32                       flags,
   _In_ _Reserved_ void                         *reserved,
   _In_ const FWPS_VSWITCH_EVENT_DISPATCH_TABLE *eventDispatchTable,
   _Out_ UINT32                                 *subscriptionId
);
````


## -parameters




#### - providerGuid

The provider GUID.




#### - notifyContext

An optional pointer to a callout driver–supplied context. Event notification functions  pass this parameter back to the driver.


#### - flags

Reserved. Set to zero.


#### - reserved

Reserved. Set to zero.


#### - eventDispatchTable

A pointer to an <a href="..\fwpsk\ns-fwpsk-fwps_vswitch_event_dispatch_table0_.md">FWPS_VSWITCH_EVENT_DISPATCH_TABLE</a> structure that defines the callback entry points for virtual switch layer events.


#### - subscriptionId

A pointer to a variable that contains a unique identifier that WFP assigns to the subscription. The caller must return the subscription identifier to WFP with the  <a href="..\fwpsk\nf-fwpsk-fwpsvswitcheventsunsubscribe0.md">FwpsvSwitchEventsUnsubscribe0</a> function.


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

The entry points for the callback notification functions are specified in and <a href="..\fwpsk\ns-fwpsk-fwps_vswitch_event_dispatch_table0_.md">FWPS_VSWITCH_EVENT_DISPATCH_TABLE0</a> structure. 

The callout driver must later call 
    <a href="..\fwpsk\nf-fwpsk-fwpsvswitcheventsunsubscribe0.md">FwpsvSwitchEventsUnsubscribe0</a>  to
    free the system resources.



## -see-also

<a href="..\fwpsk\nf-fwpsk-fwpsvswitcheventsunsubscribe0.md">FwpsvSwitchEventsUnsubscribe0</a>

<a href="..\fwpsk\ns-fwpsk-fwps_vswitch_event_dispatch_table0_.md">FWPS_VSWITCH_EVENT_DISPATCH_TABLE0</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsvSwitchEventsSubscribe0 function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

