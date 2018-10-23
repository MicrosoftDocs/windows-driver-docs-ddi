---
UID: NC:wsk.PFN_WSK_CLIENT_EVENT
title: PFN_WSK_CLIENT_EVENT
author: windows-driver-content
description: The WskClientEvent event callback function notifies a WSK application about events that are not specific to a particular socket.
old-location: netvista\wskclientevent.htm
tech.root: netvista
ms.assetid: 5511f540-4448-4cbe-849a-b1712453fae1
ms.date: 05/02/2018
ms.keywords: PFN_WSK_CLIENT_EVENT, PFN_WSK_CLIENT_EVENT callback, WskClientEvent, WskClientEvent callback function [Network Drivers Starting with Windows Vista], netvista.wskclientevent, wsk/WskClientEvent, wskref_c9f563f1-19c1-4f8d-ab44-04eedd74763f.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	wsk.h
api_name:
-	WskClientEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFN_WSK_CLIENT_EVENT callback function


## -description


The 
  <i>WskClientEvent</i> event callback function notifies a WSK application about events that are not specific
  to a particular socket.


## -parameters




### -param ClientContext [in, optional]

A pointer to the context value that was specified by the 
     <i>WskClientNpi</i> parameter passed to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571143">WskRegister</a> function.


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
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571159">WSK_CLIENT_DISPATCH</a> structure to <b>NULL</b>
    before it calls 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571143">WskRegister</a>.

The WSK subsystem calls a WSK application's 
    <i>WskClientEvent</i> event callback function at IRQL &lt;= DISPATCH_LEVEL.

A WSK application's <i>WskClientEvent</i> event callback function must not wait for completion of other WSK requests in the context of WSK completion or event callback functions. The callback can initiate other WSK requests (assuming that it doesn't spend too much time at DISPATCH_LEVEL), but it must not wait for their completion even when the callback is called at IRQL = PASSIVE_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff571159">WSK_CLIENT_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571143">WskRegister</a>
 

 

