---
UID: NC:wsk.PFN_WSK_CLIENT_EVENT
title: PFN_WSK_CLIENT_EVENT
author: windows-driver-content
description: The WskClientEvent event callback function notifies a WSK application about events that are not specific to a particular socket.
old-location: netvista\wskclientevent.htm
old-project: netvista
ms.assetid: 5511f540-4448-4cbe-849a-b1712453fae1
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.wskclientevent, WskClientEvent callback function [Network Drivers Starting with Windows Vista], WskClientEvent, PFN_WSK_CLIENT_EVENT, PFN_WSK_CLIENT_EVENT, wsk/WskClientEvent, wskref_c9f563f1-19c1-4f8d-ab44-04eedd74763f.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
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
-	wsk.h
apiname:
-	WskClientEvent
product: Windows
targetos: Windows
req.typenames: WPP_TRIAGE_INFO, *PWPP_TRIAGE_INFO
req.product: Windows 10 or later.
---

# PFN_WSK_CLIENT_EVENT callback


## -description


The 
  <i>WskClientEvent</i> event callback function notifies a WSK application about events that are not specific
  to a particular socket.


## -prototype


````
PFN_WSK_CLIENT_EVENT WskClientEvent;

NTSTATUS APIENTRY WskClientEvent(
  _In_opt_ PVOID  ClientContext,
  _In_     ULONG  Event,
  _In_opt_ PVOID  Information,
  _In_     SIZE_T InformationLength
)
{ ... }
````


## -parameters




### -param ClientContext [in, optional]

A pointer to the context value that was specified by the 
     <i>WskClientNpi</i> parameter passed to the 
     <a href="..\wsk\nf-wsk-wskregister.md">WskRegister</a> function.


### -param EventType


### -param Information [in, optional]

A pointer to a buffer that contains additional information that is associated with the event. If
     there is no additional information associated with the event, this pointer will be <b>NULL</b>.


### -param InformationLength [in]

The length of the additional information that is contained in the buffer that is pointed to by the
     
     <i>Information</i> parameter. If there is no additional information associated with the event, this value
     will be zero.


#### - Event [in]

The specific event about which the WSK application is being notified. There are currently no
     events defined.


## -returns



A WSK application's 
     <i>WskClientEvent</i> event callback function can return one of the following NTSTATUS codes:

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
The event notification was successfully processed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
Support for the event that is passed in the 
       <i>Event</i> parameter is not implemented.

</td>
</tr>
</table>
 




## -remarks



Currently, no events are defined for the 
    <i>WskClientEvent</i> event callback function. Therefore, if a WSK application implements a 
    <i>WskClientEvent</i> event callback function, it should always return STATUS_NOT_IMPLEMENTED.

The additional information that is contained in the buffer that is pointed to by the 
    <i>Information</i> parameter is read-only and is valid only for the duration of the call to the 
    <i>WskClientEvent</i> event callback function.

If a WSK application does not implement a 
    <i>WskClientEvent</i> event callback function, it should set the 
    <i>WskClientEvent</i> member of the 
    <a href="..\wsk\ns-wsk-_wsk_client_dispatch.md">WSK_CLIENT_DISPATCH</a> structure to <b>NULL</b>
    before it calls 
    <a href="..\wsk\nf-wsk-wskregister.md">WskRegister</a>.

The WSK subsystem calls a WSK application's 
    <i>WskClientEvent</i> event callback function at IRQL &lt;= DISPATCH_LEVEL.

A WSK application's <i>WskClientEvent</i> event callback function must not wait for completion of other WSK requests in the context of WSK completion or event callback functions. The callback can initiate other WSK requests (assuming that it doesn't spend too much time at DISPATCH_LEVEL), but it must not wait for their completion even when the callback is called at IRQL = PASSIVE_LEVEL.




## -see-also

<a href="..\wsk\nf-wsk-wskregister.md">WskRegister</a>



<a href="..\wsk\ns-wsk-_wsk_client_dispatch.md">WSK_CLIENT_DISPATCH</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PFN_WSK_CLIENT_EVENT callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

