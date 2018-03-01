---
UID: NF:wdm.IoWMIWriteEvent
title: IoWMIWriteEvent function
author: windows-driver-content
description: The IoWMIWriteEvent routine delivers a given event to the user-mode WMI components for notification.
old-location: kernel\iowmiwriteevent.htm
old-project: kernel
ms.assetid: 6b98861c-b108-4b07-b494-e3647d03de4c
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IoWMIWriteEvent, IoWMIWriteEvent routine [Kernel-Mode Driver Architecture], k104_ec484b7e-1653-4054-8a54-021a94303ec4.xml, kernel.iowmiwriteevent, wdm/IoWMIWriteEvent
ms.prod: windows-hardware
ms.technology: windows-devices
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
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoWMIWriteEvent function


## -description


The <b>IoWMIWriteEvent</b> routine delivers a given event to the user-mode WMI components for notification.


## -syntax


````
NTSTATUS IoWMIWriteEvent(
  _Inout_ PVOID WnodeEventItem
);
````


## -parameters




### -param WnodeEventItem [in, out]

Pointer to a <a href="..\wmistr\ns-wmistr-tagwnode_event_item.md">WNODE_EVENT_ITEM</a> structure to be delivered to the user-mode WMI components that requested notification of the event. 


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

Callers of this routine must be running at IRQL &lt;= APC_LEVEL, with one exception. When the <b>Flags</b> member of the <a href="..\wmistr\ns-wmistr-_wnode_header.md">WNODE_HEADER</a> structure contains WNODE_FLAG_TRACED_GUID, <b>IoWMIWriteEvent</b> can be called at any IRQL. (The <b>WNODE_HEADER</b> structure is a member of the <a href="..\wmistr\ns-wmistr-tagwnode_event_item.md">WNODE_EVENT_ITEM</a> structure that the <i>WnodeEventItem</i> parameter points to.)




## -see-also

<a href="..\wmistr\ns-wmistr-tagwnode_event_item.md">WNODE_EVENT_ITEM</a>



<a href="..\wdm\nf-wdm-iowmideviceobjecttoproviderid.md">IoWmiDeviceObjectToProviderId</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoWMIWriteEvent routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

