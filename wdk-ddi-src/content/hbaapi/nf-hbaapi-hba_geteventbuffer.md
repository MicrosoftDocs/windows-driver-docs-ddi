---
UID: NF:hbaapi.HBA_GetEventBuffer
title: HBA_GetEventBuffer function
author: windows-driver-content
description: The HBA_GetEventBuffer routine retrieves the indicated number of events, if available, from the HBA's event queue.
old-location: storage\hba_geteventbuffer.htm
old-project: storage
ms.assetid: 0f06b154-7d85-4a60-b354-bd61fbc597dc
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: HBA_GetEventBuffer, storage.hba_geteventbuffer, fibreHBA_rtns_782019e1-826f-486d-b8c7-6d58c097aa1d.xml, HBA_GetEventBuffer routine [Storage Devices], hbaapi/HBA_GetEventBuffer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hbaapi.h
req.include-header: Hbaapi.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: Hbaapi.lib
req.dll: Hbaapi.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Hbaapi.dll
apiname:
-	HBA_GetEventBuffer
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---

# HBA_GetEventBuffer function


## -description


The <b>HBA_GetEventBuffer</b> routine retrieves the indicated number of events, if available, from the HBA's event queue. 


## -syntax


````
HBA_STATUS HBA_API HBA_GetEventBuffer(
  _In_    HBA_HANDLE     handle,
  _Out_   PHBA_EVENTINFO EventBuffer,
  _Inout_ HBA_UINT32     *EventCount
);
````


## -parameters




### -param Handle

TBD


### -param EventBuffer [out]

Pointer to a buffer that on return holds a structure of type <a href="..\hbaapi\ns-hbaapi-hba_eventinfo.md">HBA_EventInfo</a> that contains information about an event. 


### -param EventCount [in, out]

Indicates, on input, the number of event records that fit in the buffer pointed to by <i>EventBuffer. </i>If the full number of events requested cannot be retrieved, on return, this member contains the number of event records actually retrieved. 


#### - handle [in]

Contains a value returned by the routine <a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a> that identifies the HBA on which the port is located. 


## -returns



The <b>HBA_GetEventBuffer</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_GetEventBuffer</b> returns one of the following qualifiers.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_OK</b></dt>
</dl>
</td>
<td width="60%">
Returned if the operation was successful and <i>EventCount </i>indicates the number of event records returned. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>
</td>
<td width="60%">
Returned if an unspecified error occurred that prevented the retrieval of the event records. 

</td>
</tr>
</table>
 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>



<a href="..\hbaapi\ns-hbaapi-hba_eventinfo.md">HBA_EventInfo</a>



<a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_GetEventBuffer routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

