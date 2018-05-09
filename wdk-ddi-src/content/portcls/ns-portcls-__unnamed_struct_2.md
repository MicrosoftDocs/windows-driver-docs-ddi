---
UID: NS:portcls.__unnamed_struct_2
title: PCEVENT_ITEM
author: windows-driver-content
description: The PCEVENT_ITEM structure is used to describe an event that is supported by a particular filter, pin, or node.
old-location: audio\pcevent_item.htm
old-project: audio
ms.assetid: b91a7582-e146-4ded-a6b7-cb77850bfd2c
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: "*PPCEVENT_ITEM, PCEVENT_ITEM, PCEVENT_ITEM structure [Audio Devices], PPCEVENT_ITEM, PPCEVENT_ITEM structure pointer [Audio Devices], audio.pcevent_item, audpc-struct_54e5d50f-6902-47d3-8170-3ee459b8dfb8.xml, portcls/PCEVENT_ITEM, portcls/PPCEVENT_ITEM"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	portcls.h
api_name:
-	PCEVENT_ITEM
product:
- Windows
targetos: Windows
req.typenames: PCEVENT_ITEM, *PPCEVENT_ITEM
---

# PCEVENT_ITEM structure


## -description


The <b>PCEVENT_ITEM</b> structure is used to describe an event that is supported by a particular filter, pin, or node.


## -struct-fields




### -field Set

Specifies the event set. This member is a pointer to a GUID that uniquely identifies the event set. See the list of event-set GUIDs in <a href="https://msdn.microsoft.com/library/windows/hardware/ff536195">Audio Drivers Event Sets</a>.


### -field Id

Specifies the event ID. This member identifies an event item within the event set. If the event set contains N items, valid event IDs are integers in the range 0 to N-1.


### -field Flags

Specifies the type of event. This member is set to one of the following values:





#### PCEVENT_ITEM_FLAG_ENABLE

Indicates the event notification should be enabled for this event type. The driver should continue event notification until the client explicitly disables it.



#### PCEVENT_ITEM_FLAG_ONESHOT

Indicates that the event notification should be enabled for the next occurrence of this event only. The client does not (and should not) disable the event once it has occurred.



#### PCEVENT_ITEM_FLAG_BASICSUPPORT

If the client specifies this flag, the driver returns STATUS_SUCCESS if it supports the event and an error code if it does not.


### -field Handler

Pointer to the miniport driver's event-handler routine. This member is a function pointer of type PCPFNEVENT_HANDLER, which is defined as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>  typedef NTSTATUS (*PCPFNEVENT_HANDLER)
  (
      IN PPCEVENT_REQUEST  EventRequest
  );</pre>
</td>
</tr>
</table></span></div>
When calling the <b>Handler</b> routine, the caller passes in a single call parameter, which is a pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff537693">PCEVENT_REQUEST</a> structure.


## -remarks



The <b>PCEVENT_ITEM</b> structure specifies a particular event item in an automation table. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff537685">PCAUTOMATION_TABLE</a> structure points to an array of <b>PCEVENT_ITEM</b> structures.

In WDM audio, the target for an event request is either a pin instance or a node on a pin. A filter instance cannot be the target of an event request.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537685">PCAUTOMATION_TABLE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537693">PCEVENT_REQUEST</a>
 

 

