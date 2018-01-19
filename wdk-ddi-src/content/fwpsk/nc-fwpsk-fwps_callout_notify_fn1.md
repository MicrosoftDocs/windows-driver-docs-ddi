---
UID: NC:fwpsk.FWPS_CALLOUT_NOTIFY_FN1
title: FWPS_CALLOUT_NOTIFY_FN1
author: windows-driver-content
description: The filter engine calls a callout's notifyFn1 callout function to notify the callout driver about events that are associated with the callout.Note  notifyFn1 is the specific version of notifyFn used in Windows 7 and later.
old-location: netvista\notifyfn1.htm
old-project: netvista
ms.assetid: 3f377049-cc5f-427d-9b09-5e49e4b305c5
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: FwpmEngineOpen0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 7.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: notifyFn1
req.alt-loc: Fwpsk.h
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
req.typenames: PINSTANCE_PARTIAL_INFORMATION, INSTANCE_PARTIAL_INFORMATION
---

# FWPS_CALLOUT_NOTIFY_FN1 callback



## -description
The filter engine calls a callout's 
  <i>notifyFn1</i> callout function to notify the callout driver about events that are associated with the
  callout.



## -prototype

````
FWPS_CALLOUT_NOTIFY_FN1 notifyFn1;

NTSTATUS NTAPI notifyFn1(
  _In_       FWPS_CALLOUT_NOTIFY_TYPE notifyType,
  _In_ const GUID                     *filterKey,
  _In_ const FWPS_FILTER1             *filter
)
{ ... }
````


## -parameters

### -param notifyType [in]

A value that indicates the type of notification that the filter engine is sending to the callout.
     Valid values for this parameter are:
     




### -param FWPS_CALLOUT_NOTIFY_ADD_FILTER

A filter is being added to the filter engine that specifies the callout for the filter's
       action.


### -param FWPS_CALLOUT_NOTIFY_DELETE_FILTER

A filter is being deleted from the filter engine that specifies the callout for the filter's
       action.


### -param FWPS_CALLOUT_NOTIFY_TYPE_MAX

A maximum value for testing purposes.

</dd>
</dl>

### -param filterKey [in]

A pointer to the management identifier for the filter, as specified by the application or driver
     that is adding or deleting the filter. Must be <b>NULL</b> if the 
     <i>notifyType</i> parameter is set to FWPS_CALLOUT_NOTIFY_DELETE_FILTER. For more information, see Remarks.


### -param filter [in]

A pointer to an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff552389">FWPS_FILTER1</a> structure. This structure
     describes the filter that is being added to or deleted from the filter engine.
     

A callout driver's 
     <i>notifyFn1</i> function can set the 
     <b>Context</b> member of this structure to point to a callout driver-supplied context structure when the
     filter is added to the filter engine. This context structure is opaque to the filter engine, and can be
     used by the callout driver's 
     <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn1.md">classifyFn1</a> callout function to preserve
     any driver-specific data or state information between calls by the filter engine to the callout driver's
     
     <i>classifyFn1</i> callout function.

A callout driver's 
     <i>notifyFn1</i> function can clean up any context associated with the filter when the filter is deleted
     from the filter engine.


## -returns
A callout's 
     <i>notifyFn1</i> function returns one of the following NTSTATUS codes.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The callout driver accepts the notification from the filter engine.
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred. If the 
       <i>notifyType</i> parameter is FWPS_CALLOUT_NOTIFY_ADD_FILTER, the filter will not be added to the
       filter engine. If the 
       <i>notifyType</i> parameter is FWPS_CALLOUT_NOTIFY_DELETE_FILTER, the filter will still be deleted from
       the filter engine.

 


## -remarks
A callout driver registers a callout's callout functions with the filter engine by calling the 
    <a href="..\fwpsk\nf-fwpsk-fwpscalloutregister1.md">FwpsCalloutRegister1</a> function.

The filter engine calls a callout driver's 
    <i>notifyFn1</i> function to notify the callout driver about events that are associated with the callout.
    If the callout driver's 
    <i>notifyFn1</i> function does not recognize the type of notification that is passed in the 
    <i>notifyType</i> parameter, it should ignore the notification and return STATUS_SUCCESS.

If a callout driver registers a callout with the filter engine after filters that specify the callout
    for the filter's action have already been added to the filter engine, the filter engine does not call the
    callout driver's 
    <i>notifyFn1</i> function to notify the callout about any of the existing filters. The filter engine calls
    the callout driver's 
    <i>notifyFn1</i> function to notify the callout when new filters that specify the callout for the filter's
    action are added to the filter engine. In this situation, a callout's 
    <i>notifyFn1</i> function might not get called for every filter in the filter engine that specifies the
    callout for the filter's action. If a callout driver registers a callout after the filter engine is
    started and the callout needs to know about every filter in the filter engine that specifies the callout
    for the filter's action, the callout driver must call the appropriate management functions to enumerate
    all the filters in the filter engine and sort through the resulting list of filters to find those that
    specify the callout for the filter's action. See 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/calling-other-windows-filtering-platform-functions">Calling Other
    Windows Filtering Platform Functions</a> for more information about calling these functions.

When a filter that specifies a callout for the filter's action is deleted from the filter engine, the
    filter engine calls the callout driver's 
    <i>notifyFn1</i> function and passes FWP_CALLOUT_NOTIFY_DELETE_FILTER in the 
    <i>notifyType</i> parameter and <b>NULL</b> in the 
    <i>filterKey</i> parameter. For more information, see 
    <a href="https://msdn.microsoft.com/d686989e-97f0-4095-b172-1c2ccf7a26e6">Processing Notify Callouts</a>.


## -see-also
<dl>
<dt>
<a href="..\fwpsk\ns-fwpsk-fwps_callout0_.md">FWPS_CALLOUT0</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552389">FWPS_FILTER1</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpscalloutregister1.md">FwpsCalloutRegister1</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568802">notifyFn</a>
</dt>
<dt>
<a href="..\fwpsk\nc-fwpsk-fwps_callout_notify_fn0.md">notifyFn0</a>
</dt>
<dt>
<a href="..\fwpsk\nc-fwpsk-fwps_callout_notify_fn2.md">notifyFn2</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543875">Callout Driver Callout Functions</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_CALLOUT_NOTIFY_FN1 callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

