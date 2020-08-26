---
UID: NF:wdm.IoWMISetNotificationCallback
title: IoWMISetNotificationCallback function (wdm.h)
description: The IoWMISetNotificationCallback routine registers a notification callback for a WMI event.
old-location: kernel\iowmisetnotificationcallback.htm
tech.root: kernel
ms.assetid: c1bd12e0-0862-4e51-a9e8-71eb7b2549fd
ms.date: 04/30/2018
keywords: ["IoWMISetNotificationCallback function"]
ms.keywords: IoWMISetNotificationCallback, IoWMISetNotificationCallback routine [Kernel-Mode Driver Architecture], k104_8ee391bd-0abe-4901-b0dc-6266d0c8f5c4.xml, kernel.iowmisetnotificationcallback, wdm/IoWMISetNotificationCallback
f1_keywords:
 - "wdm/IoWMISetNotificationCallback"
 - "IoWMISetNotificationCallback"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating system.
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoWMISetNotificationCallback
targetos: Windows
req.typenames: 
---

# IoWMISetNotificationCallback function


## -description


The <b>IoWMISetNotificationCallback</b> routine registers a notification callback for a WMI event.


## -parameters




### -param Object 
[in, out]
Pointer to a WMI data block object. The caller opens the data block object for the WMI event with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iowmiopenblock">IoWMIOpenBlock</a> routine. The object must be opened with the WMIGUID_NOTIFICATION access right.


### -param Callback 
[in]
Pointer to a function of the form:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre> XxxWmiNotificationCallback(PVOID Wnode, PVOID Context);</pre>
</td>
</tr>
</table></span></div>
WMI calls this function to notify the caller that the specified event has occurred. The <i>Wnode</i> parameter of the callback routine points to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmistr/ns-wmistr-tagwnode_event_item">WNODE_EVENT_ITEM</a> structure returned by the driver triggering the event. The <i>Context</i> parameter of the callback routine points to the value specified in the <i>Context</i> parameter of the <b>IoWMISetNotificationCallback</b> routine.


### -param Context 
[in, optional]
Specifies the value that WMI passes to the callback routine when the event occurs.


## -returns



This routine returns STATUS_SUCCESS on success, and the appropriate NTSTATUS error code on failure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iowmiopenblock">IoWMIOpenBlock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmistr/ns-wmistr-tagwnode_event_item">WNODE_EVENT_ITEM</a>
 

 

