---
UID: NC:fwpsk.FWPS_CALLOUT_NOTIFY_FN0
title: FWPS_CALLOUT_NOTIFY_FN0 (fwpsk.h)
description: The filter engine calls a callout's notifyFn0 callout function to notify the callout driver about events that are associated with the callout.Note  notifyFn0 is the specific version of notifyFn used in Windows Vista and later.
old-location: netvista\notifyfn0.htm
tech.root: netvista
ms.assetid: c0f94079-7398-4998-b2b2-471aa8c538a1
ms.date: 05/02/2018
ms.keywords: FWPS_CALLOUT_NOTIFY_FN0, FWPS_CALLOUT_NOTIFY_FN0 callback, fwpsk/notifyFn0, netvista.notifyfn0, notifyFn0, notifyFn0 callback function [Network Drivers Starting with Windows Vista], wfp_ref_2_funct_4_callout_67d79632-69ad-41a2-8a0e-21f4020b0550.xml
ms.topic: callback
f1_keywords:
 - "fwpsk/notifyFn0"
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
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
- notifyFn0
product:
- Windows
targetos: Windows
req.typenames: 
---

# FWPS_CALLOUT_NOTIFY_FN0 callback function


## -description


The filter engine calls a callout's 
  <i>notifyFn0</i> callout function to notify the callout driver about events that are associated with the
  callout.
<div class="alert"><b>Note</b>  <i>notifyFn0</i> is the specific version of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_netvista/">notifyFn</a> used in Windows Vista and later. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information. For Windows 8, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nc-fwpsk-fwps_callout_notify_fn2">notifyFn2</a> is available. For Windows 7, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nc-fwpsk-fwps_callout_notify_fn1">notifyFn1</a> is available.</div><div> </div>

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
     that is adding or deleting the filter. Must be <b>NULL</b> if the 
     <i>notifyType</i> parameter is set to FWPS_CALLOUT_NOTIFY_DELETE_FILTER. For more information, see Remarks.


### -param *filter [in]

A pointer to an 
     <a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_filter0_">FWPS_FILTER0</a> structure. This structure
     describes the filter that is being added to or deleted from the filter engine.
     

A callout's 
     <i>notifyFn0</i> callout function can set the 
     <b>Context</b> member of this structure to point to a callout driver-supplied context structure when the
     filter is added to the filter engine. This context structure is opaque to the filter engine, and can be
     used by the callout driver's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nc-fwpsk-fwps_callout_classify_fn0">classifyFn0</a> callout function to preserve
     any driver-specific data or state information between calls by the filter engine to the callout driver's     
     <i>classifyFn0</i> callout function.

A callout's 
     <i>notifyFn0</i> callout function can clean up any context associated with the filter when the filter is
     deleted from the filter engine.


## -returns



A callout's 
     <i>notifyFn0</i> function returns one of the following NTSTATUS codes.

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
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpscalloutregister0">FwpsCalloutRegister0</a> function.

The filter engine calls a callout's 
    <i>notifyFn0</i> callout function to notify the callout driver about events that are associated with the
    callout. If the callout driver's 
    <i>notifyFn0</i> callout function does not recognize the type of notification that is passed in the 
    <i>notifyType</i> parameter, it ignores the notification and return STATUS_SUCCESS.

If a callout driver registers a callout with the filter engine after filters that specify the callout
    for the filter's action have already been added to the filter engine, the filter engine does not call the
    callout driver's 
    <i>notifyFn0</i> callout function to notify the callout about any of the existing filters. The filter
    engine calls the callout driver's 
    <i>notifyFn0</i> callout function to notify the callout when new filters that specify the callout for the
    filter's action are added to the filter engine. In this situation, a callout's 
    <i>notifyFn0</i> callout function might not get called for every filter in the filter engine that
    specifies the callout for the filter's action. If a callout driver registers a callout after the filter
    engine is started and the callout needs to know about every filter in the filter engine that specifies
    the callout for the filter's action, the callout driver must call the appropriate management functions to
    enumerate all the filters in the filter engine and sort through the resulting list of filters to find
    those that specify the callout for the filter's action. See 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/calling-other-windows-filtering-platform-functions">Calling Other
    Windows Filtering Platform Functions</a> for more information about calling these functions.

When a filter that specifies a callout for the filter's action is deleted from the filter engine, the
    filter engine calls the callout driver's 
    <i>notifyFn0</i> callout function and passes FWP_CALLOUT_NOTIFY_DELETE_FILTER in the 
    <i>notifyType</i> parameter and <b>NULL</b> in the 
    <i>filterKey</i> parameter. For more information, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/processing-notify-callouts">Processing Notify Callouts</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_netvista/">Callout Driver Callout Functions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/ns-fwpsk-fwps_callout0_">FWPS_CALLOUT0</a>



<a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_filter0_">FWPS_FILTER0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpscalloutregister0">FwpsCalloutRegister0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_netvista/">notifyFn</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nc-fwpsk-fwps_callout_notify_fn1">notifyFn1</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nc-fwpsk-fwps_callout_notify_fn2">notifyFn2</a>
 

 

