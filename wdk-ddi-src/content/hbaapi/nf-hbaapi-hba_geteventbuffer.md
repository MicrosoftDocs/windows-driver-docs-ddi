---
UID: NF:hbaapi.HBA_GetEventBuffer
title: HBA_GetEventBuffer function
author: windows-driver-content
description: The HBA_GetEventBuffer routine retrieves the indicated number of events, if available, from the HBA's event queue.
old-location: storage\hba_geteventbuffer.htm
old-project: storage
ms.assetid: 0f06b154-7d85-4a60-b354-bd61fbc597dc
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: HBA_GetEventBuffer, HBA_GetEventBuffer routine [Storage Devices], fibreHBA_rtns_782019e1-826f-486d-b8c7-6d58c097aa1d.xml, hbaapi/HBA_GetEventBuffer, storage.hba_geteventbuffer
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Hbaapi.dll
api_name:
-	HBA_GetEventBuffer
product: Windows
targetos: Windows
req.typenames: 
---

# HBA_GetEventBuffer function


## -description


The <b>HBA_GetEventBuffer</b> routine retrieves the indicated number of events, if available, from the HBA's event queue. 


## -parameters




### -param Handle

TBD


### -param EventBuffer [out]

Pointer to a buffer that on return holds a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff556048">HBA_EventInfo</a> that contains information about an event. 


### -param EventCount [in, out]

Indicates, on input, the number of event records that fit in the buffer pointed to by <i>EventBuffer. </i>If the full number of events requested cannot be retrieved, on return, this member contains the number of event records actually retrieved. 


#### - handle [in]

Contains a value returned by the routine <a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a> that identifies the HBA on which the port is located. 


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556048">HBA_EventInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>
 

 

