---
UID: NC:fwpsk.FWPS_CALLOUT_NOTIFY_FN2
title: FWPS_CALLOUT_NOTIFY_FN2
author: windows-driver-content
description: The filter engine calls a callout's notifyFn2 callout function to notify the callout driver about events that are associated with the callout.Note  notifyFn2 is the specific version of notifyFn used in Windows 8 and later.
old-location: netvista\notifyfn2.htm
tech.root: netvista
ms.assetid: c70c987b-5b4c-4ddd-8eb8-8c3c40003ab3
ms.date: 05/02/2018
ms.keywords: FWPS_CALLOUT_NOTIFY_FN2, FWPS_CALLOUT_NOTIFY_FN2 callback, fwpsk/notifyFn2, netvista.notifyfn2, notifyFn2, notifyFn2 callback function [Network Drivers Starting with Windows Vista]
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Fwpsk.h
api_name:
-	notifyFn2
product:
- Windows
targetos: Windows
req.typenames: 
---

# FWPS_CALLOUT_NOTIFY_FN2 callback function


## -description


The filter engine calls a callout's 
  <i>notifyFn2</i> callout function to notify the callout driver about events that are associated with the
  callout.<div class="alert"><b>Note</b>  <i>notifyFn2</i> is the specific version of <a href="https://msdn.microsoft.com/library/windows/hardware/ff568802">notifyFn</a> used in Windows 8 and later. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information. For Windows 7, <a href="https://msdn.microsoft.com/3f377049-cc5f-427d-9b09-5e49e4b305c5">notifyFn1</a> is available. For Windows Vista, <a href="https://msdn.microsoft.com/c0f94079-7398-4998-b2b2-471aa8c538a1">notifyFn0</a> is available.</div>
<div> </div>



## -parameters




### -param notifyType [in]

A value that indicates the type of notification that the filter engine is sending to the callout.
     Valid values for this parameter are:
     





#### FWPS_CALLOUT_NOTIFY_ADD_FILTER

A filter is being added to the filter engine that specifies the callout for the filter's
       action.



#### FWPS_CALLOUT_NOTIFY_DELETE_FILTER

A filter is being deleted from the filter engine that specifies the callout for the filter's
       action.



#### FWPS_CALLOUT_NOTIFY_TYPE_MAX

A maximum value for testing purposes.


### -param *filterKey [in]

A pointer to the management identifier for the filter, as specified by the application or driver
     that is adding or deleting the filter. Must be NULL if the 
     <i>notifyType</i> parameter is set to FWPS_CALLOUT_NOTIFY_DELETE_FILTER. For more information, see the
     following Remarks section.


### -param *filter [in, out]

A pointer to an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/hh439768">FWPS_FILTER2</a> structure. This structure
     describes the filter that is being added to or deleted from the filter engine.
     

A callout driver's 
     <i>notifyFn2</i> function can set the 
     <b>Context</b> member of this structure to point to a callout driver-supplied context structure when the
     filter is added to the filter engine. This context structure is opaque to the filter engine, and can be
     used by the callout driver's 
     <a href="https://msdn.microsoft.com/de8220de-cf71-4718-876e-ef02c15fc948">classifyFn2</a> callout function to preserve
     any driver-specific data or state information between calls by the filter engine to the callout driver's     
     <i>classifyFn2</i> callout function.

A callout driver's 
     <i>notifyFn2</i> function can clean up any context associated with the filter when the filter is deleted
     from the filter engine.


## -returns



A callout's 
     <i>notifyFn2</i> function returns one of the following NTSTATUS codes.

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
The callout driver accepts the notification from the filter engine.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred. If the 
       <i>notifyType</i> parameter is FWPS_CALLOUT_NOTIFY_ADD_FILTER, the filter will not be added to the
       filter engine. If the 
       <i>notifyType</i> parameter is FWPS_CALLOUT_NOTIFY_DELETE_FILTER, the filter will still be deleted from
       the filter engine.

</td>
</tr>
</table>
 




## -remarks



A callout driver registers a callout's callout functions with the filter engine by calling the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/hh439576">FwpsCalloutRegister2</a> function.

The filter engine calls a callout driver's 
    <i>notifyFn2</i> function to notify the callout driver about events that are associated with the callout.
    If the callout driver's 
    <i>notifyFn2</i> function does not recognize the type of notification that is passed in the 
    <i>notifyType</i> parameter, it should ignore the notification and return STATUS_SUCCESS.

If a callout driver registers a callout with the filter engine after filters that specify the callout
    for the filter's action have already been added to the filter engine, the filter engine does not call the
    callout driver's 
    <i>notifyFn2</i> function to notify the callout about any of the existing filters. The filter engine calls
    the callout driver's 
    <i>notifyFn2</i> function to notify the callout when new filters that specify the callout for the filter's
    action are added to the filter engine. In this situation, a callout's 
    <i>notifyFn2</i> function might not get called for every filter in the filter engine that specifies the
    callout for the filter's action. If a callout driver registers a callout after the filter engine is
    started and the callout needs to know about every filter in the filter engine that specifies the callout
    for the filter's action, the callout driver must call the appropriate management functions to enumerate
    all the filters in the filter engine and sort through the resulting list of filters to find those that
    specify the callout for the filter's action. See 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/calling-other-windows-filtering-platform-functions">Calling Other
    Windows Filtering Platform Functions</a> for more information about calling these functions.

When a filter that specifies a callout for the filter's action is deleted from the filter engine, the
    filter engine calls the callout driver's 
    <i>notifyFn2</i> function and passes FWP_CALLOUT_NOTIFY_DELETE_FILTER in the 
    <i>notifyType</i> parameter and NULL in the 
    <i>filterKey</i> parameter. For more information, see 
    <a href="https://msdn.microsoft.com/d686989e-97f0-4095-b172-1c2ccf7a26e6">Processing Notify Callouts</a>.

This function is essentially identical to the previous version, 
    <a href="https://msdn.microsoft.com/3f377049-cc5f-427d-9b09-5e49e4b305c5">notifyFn1</a>. The only difference is the 
       updated <a href="https://msdn.microsoft.com/library/windows/hardware/hh439768">FWPS_FILTER2</a> structure pointed to by the 
       <i>filter</i> parameter.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543875">Callout Driver Callout Functions</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439768">FWPS_FILTER2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439576">FwpsCalloutRegister2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568802">notifyFn</a>



<a href="https://msdn.microsoft.com/c0f94079-7398-4998-b2b2-471aa8c538a1">notifyFn0</a>



<a href="https://msdn.microsoft.com/3f377049-cc5f-427d-9b09-5e49e4b305c5">notifyFn1</a>
 

 

