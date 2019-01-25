---
UID: NF:wdm.IoWMIWriteEvent
title: IoWMIWriteEvent function (wdm.h)
description: The IoWMIWriteEvent routine delivers a given event to the user-mode WMI components for notification.
old-location: kernel\iowmiwriteevent.htm
tech.root: kernel
ms.assetid: 6b98861c-b108-4b07-b494-e3647d03de4c
ms.date: 04/30/2018
ms.keywords: IoWMIWriteEvent, IoWMIWriteEvent routine [Kernel-Mode Driver Architecture], k104_ec484b7e-1653-4054-8a54-021a94303ec4.xml, kernel.iowmiwriteevent, wdm/IoWMIWriteEvent
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: "<= APC_LEVEL (see Remarks section)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoWMIWriteEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoWMIWriteEvent function


## -description


The <b>IoWMIWriteEvent</b> routine delivers a given event to the user-mode WMI components for notification.


## -parameters




### -param WnodeEventItem [in, out]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff566373">WNODE_EVENT_ITEM</a> structure to be delivered to the user-mode WMI components that requested notification of the event. 


## -returns



<b>IoWMIWriteEvent</b> returns a status code from the following list:

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
Indicates that WMI has successfully queued the event for delivery to the user-mode WMI components.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
Indicates that WMI services are unavailable. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the event item specified exceeds the maximum allowed size.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Indicates that insufficient resources were available for WMI to queue the event for delivery.

</td>
</tr>
</table>
 




## -remarks



The WNODE_EVENT_ITEM structure that is allocated by the caller and passed in <i>WnodeEventItem</i> must be allocated from nonpaged pool. If <b>IoWMIWriteEvent</b> returns STATUS_SUCCESS, the memory for the event item will automatically be freed by the system. If <b>IoWMIWriteEvent</b> returns anything other than STATUS_SUCCESS, it is the caller's responsibility to free the buffer.

Drivers should only call <b>IoWMIWriteEvent</b> for events that have been enabled for WMI. This ensures that there is an event consumer waiting for indication on that event.

Callers of this routine must be running at IRQL &lt;= APC_LEVEL, with one exception. When the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566375">WNODE_HEADER</a> structure contains WNODE_FLAG_TRACED_GUID, <b>IoWMIWriteEvent</b> can be called at any IRQL. (The <b>WNODE_HEADER</b> structure is a member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566373">WNODE_EVENT_ITEM</a> structure that the <i>WnodeEventItem</i> parameter points to.)




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550433">IoWmiDeviceObjectToProviderId</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566373">WNODE_EVENT_ITEM</a>
 

 

