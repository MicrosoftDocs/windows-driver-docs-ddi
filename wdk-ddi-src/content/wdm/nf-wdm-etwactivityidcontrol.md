---
UID: NF:wdm.EtwActivityIdControl
title: EtwActivityIdControl function (wdm.h)
description: The EtwActivityIdControl function creates, queries, and sets the current activity identifier.
old-location: devtest\etwactivityidcontrol.htm
tech.root: devtest
ms.assetid: dd2e1558-db5d-4d48-a55e-fbdf2838ec55
ms.date: 02/23/2018
keywords: ["EtwActivityIdControl function"]
ms.keywords: EVENT_ACTIVITY_CTRL_CREATE_ID, EVENT_ACTIVITY_CTRL_CREATE_SET_ID, EVENT_ACTIVITY_CTRL_GET_ID, EVENT_ACTIVITY_CTRL_GET_SET_ID, EVENT_ACTIVITY_CTRL_SET_ID, EtwActivityIdControl, EtwActivityIdControl function [Driver Development Tools], devtest.etwactivityidcontrol, etw_km_ecbfd65a-dd05-422b-9039-bb2a307d5978.xml, wdm/EtwActivityIdControl
f1_keywords:
 - "wdm/EtwActivityIdControl"
 - "EtwActivityIdControl"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: See Comments section
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- EtwActivityIdControl
targetos: Windows
req.typenames: 
---

# EtwActivityIdControl function


## -description


The <b>EtwActivityIdControl</b> function creates, queries, and sets the current activity identifier. 


## -parameters




### -param ControlCode 
[in]
The <i>ControlCode</i> parameter can be one of the following defined values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="EVENT_ACTIVITY_CTRL_GET_ID"></a><a id="event_activity_ctrl_get_id"></a><dl>
<dt><b>EVENT_ACTIVITY_CTRL_GET_ID</b></dt>
</dl>
</td>
<td width="60%">
Returns the current thread's activity identifier in the <i>ActivityId</i> parameter.  

</td>
</tr>
<tr>
<td width="40%"><a id="EVENT_ACTIVITY_CTRL_SET_ID"></a><a id="event_activity_ctrl_set_id"></a><dl>
<dt><b>EVENT_ACTIVITY_CTRL_SET_ID</b></dt>
</dl>
</td>
<td width="60%">
Sets the current thread's activity identifier to the value specified in <i>ActivityId</i>. Note that the <i>ActivityId</i> you pass to this function
            does not necessarily have to be one created by EVENT_ACTIVITY_CTRL_CREATE_ID or EVENT_ACTIVITY_CTRL_CREATE_SET_ID control code.
            You can use any value that fits inside a GUID, including any available
            local value that would serve your need for
            some type of activity identifier.

</td>
</tr>
<tr>
<td width="40%"><a id="EVENT_ACTIVITY_CTRL_CREATE_ID"></a><a id="event_activity_ctrl_create_id"></a><dl>
<dt><b>EVENT_ACTIVITY_CTRL_CREATE_ID</b></dt>
</dl>
</td>
<td width="60%">
Creates a new identifier and sets the <i>ActivityId</i> parameter to the value of the new identifier.  

</td>
</tr>
<tr>
<td width="40%"><a id="EVENT_ACTIVITY_CTRL_GET_SET_ID"></a><a id="event_activity_ctrl_get_set_id"></a><dl>
<dt><b>EVENT_ACTIVITY_CTRL_GET_SET_ID</b></dt>
</dl>
</td>
<td width="60%">
Sets the current thread's activity identifier to the value specified in <i>ActivityId</i>, and then returns <i>ActivityId</i> with the value of the thread's activity identifier prior to the function call.  

</td>
</tr>
<tr>
<td width="40%"><a id="EVENT_ACTIVITY_CTRL_CREATE_SET_ID"></a><a id="event_activity_ctrl_create_set_id"></a><dl>
<dt><b>EVENT_ACTIVITY_CTRL_CREATE_SET_ID</b></dt>
</dl>
</td>
<td width="60%">
Copies the current thread's activity identifier. Creates a new identifier and sets the current thread's   activity identifier to the new value. Returns <i>ActivityId</i> with the value of the thread's activity identifier prior to the function call. 

</td>
</tr>
</table>
 


### -param ActivityId 
[in, out]
The identifier that indicates the activity associated with the event. The <i>ActivityId</i> parameter provides a way to group related events and is used in end-to-end tracing.


## -returns



<b>EtwActivityIdControl</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value.




## -remarks



Activity identifiers provide a method of linking separate events in a common thread of computation. An <i>activity</i> is a work item performed by an application and or a driver. The concept of activity is a core component in end-to-end tracing.

Callers of <b>EtwActivityIdControl</b> must be running at IRQL < DISPATCH_LEVEL, unless the <i>ControlCode</i> is EVENT_ACTIVITY_CTRL_CREATE_ID, in which case the function can be called at any IRQL.

Use the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/dn268326(v=vs.85)">EtwActivityIdControlKernel</a> function to  query or set  activity identifiers  kernel threads. 




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/dn268326(v=vs.85)">EtwActivityIdControlKernel</a>
 

 

