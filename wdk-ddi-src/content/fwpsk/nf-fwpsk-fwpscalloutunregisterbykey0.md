---
UID: NF:fwpsk.FwpsCalloutUnregisterByKey0
title: FwpsCalloutUnregisterByKey0 function
author: windows-driver-content
description: The FwpsCalloutUnregisterByKey0 function unregisters a callout from the filter engine.Note  FwpsCalloutUnregisterByKey0 is a specific version of FwpsCalloutUnregisterByKey.
old-location: netvista\fwpscalloutunregisterbykey0.htm
old-project: netvista
ms.assetid: 24254e56-c7f5-4424-98b5-3b99bf210d5b
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: FwpsCalloutUnregisterByKey0, FwpsCalloutUnregisterByKey0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsCalloutUnregisterByKey0, netvista.fwpscalloutunregisterbykey0, wfp_ref_2_funct_3_fwps_C_e5a98dbf-23ee-4383-96d5-d8ce8a85614e.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
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
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	fwpkclnt.lib
-	fwpkclnt.dll
api_name:
-	FwpsCalloutUnregisterByKey0
product: Windows
targetos: Windows
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---

# FwpsCalloutUnregisterByKey0 function


## -description


The 
  <b>FwpsCalloutUnregisterByKey0</b> function unregisters a callout from the filter engine.
<div class="alert"><b>Note</b>  <b>FwpsCalloutUnregisterByKey0</b> is a specific version of <b>FwpsCalloutUnregisterByKey</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -syntax


````
NTSTATUS NTAPI FwpsCalloutUnregisterByKey0(
  _In_ const GUID *calloutKey
);
````


## -parameters




### -param calloutKey [in]

A pointer to a GUID that uniquely identifies the callout that is being unregistered from the
     filter engine. This must be a pointer to the same GUID that was specified when the callout driver called
     either the 
     <a href="..\fwpsk\nf-fwpsk-fwpscalloutregister0.md">FwpsCalloutRegister0</a> or 
     <a href="..\fwpsk\nf-fwpsk-fwpscalloutregister1.md">FwpsCalloutRegister1</a> functions to
     register the callout with the filter engine.


## -returns



The 
     <b>FwpsCalloutUnregisterByKey0</b> function returns one of the following NTSTATUS codes.

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
The callout was successfully unregistered from the filter engine.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_BUSY</b></dt>
</dl>
</td>
<td width="60%">
There are one or more data flows being processed by the callout that have an outstanding context
       associated with the data flow. A callout driver must call the 
       <a href="..\fwpsk\nf-fwpsk-fwpsflowremovecontext0.md">FwpsFlowRemoveContext0</a> function
       for each of these data flows to remove the associated context. After the context has been successfully
       removed from each of these data flows, the callout driver must call the 
       <b>FwpsCalloutUnregisterByKey0</b> function again to finish unregistering the callout from the filter
       engine.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FWP_CALLOUT_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
There is not a callout registered with the filter engine that matches the GUID specified in the 
       <i>calloutKey</i> parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FWP_IN_USE</b></dt>
</dl>
</td>
<td width="60%">
The callout is already in the process of being registered or unregistered in another
       thread.

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
    <b>FwpsCalloutUnregisterByKey0</b> function to unregister a callout from the filter engine, using the GUID
    key to identify the callout to be unregistered. This function succeeds even if there are filters in
    the filter engine that specify the callout for the filter's action. In this situation, filters with an
    action type of <b>FWP_ACTION_CALLOUT_TERMINATING</b> or <b>FWP_ACTION_CALLOUT_UNKNOWN</b> are treated as
    <b>FWP_ACTION_BLOCK</b>, and filters with an action type of <b>FWP_ACTION_CALLOUT_INSPECTION</b> are ignored after the
    callout has been deregistered from the filter engine.

A callout driver cannot be unloaded until all of the callouts that were previously registered with the
    filter engine have been successfully unregistered.




## -see-also

<a href="..\fwpsk\nf-fwpsk-fwpscalloutunregisterbyid0.md">FwpsCalloutUnregisterById0</a>



<a href="..\fwpsk\nf-fwpsk-fwpscalloutregister1.md">FwpsCalloutRegister1</a>



<a href="https://msdn.microsoft.com/d9539403-7657-4e95-8791-309673d1207d">Types of Callouts</a>



<a href="..\fwpsk\nf-fwpsk-fwpsflowremovecontext0.md">FwpsFlowRemoveContext0</a>



<a href="..\fwpsk\nf-fwpsk-fwpscalloutregister0.md">FwpsCalloutRegister0</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsCalloutUnregisterByKey0 function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

