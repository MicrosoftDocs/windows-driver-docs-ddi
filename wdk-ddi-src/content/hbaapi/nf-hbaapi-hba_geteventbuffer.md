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
ms.keywords: HBA_GetEventBuffer
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
req.alt-api: HBA_GetEventBuffer
req.alt-loc: Hbaapi.dll
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

### -param handle [in]

Contains a value returned by the routine <a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a> that identifies the HBA on which the port is located. 


### -param EventBuffer [out]

Pointer to a buffer that on return holds a structure of type <a href="..\hbaapi\ns-hbaapi-hba_eventinfo.md">HBA_EventInfo</a> that contains information about an event. 


### -param EventCount [in, out]

Indicates, on input, the number of event records that fit in the buffer pointed to by <i>EventBuffer. </i>If the full number of events requested cannot be retrieved, on return, this member contains the number of event records actually retrieved. 


## -returns
The <b>HBA_GetEventBuffer</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_GetEventBuffer</b> returns one of the following qualifiers.
<dl>
<dt><b>HBA_STATUS_OK</b></dt>
</dl>Returned if the operation was successful and <i>EventCount </i>indicates the number of event records returned. 
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>Returned if an unspecified error occurred that prevented the retrieval of the event records. 

 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a>
</dt>
<dt>
<a href="..\hbaapi\ns-hbaapi-hba_eventinfo.md">HBA_EventInfo</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_GetEventBuffer routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

