---
UID: NS:portcls.__unnamed_struct_0c93_5
title: PCEVENT_ITEM
author: windows-driver-content
description: The PCEVENT_ITEM structure is used to describe an event that is supported by a particular filter, pin, or node.
old-location: audio\pcevent_item.htm
tech.root: audio
ms.assetid: b91a7582-e146-4ded-a6b7-cb77850bfd2c
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PCEVENT_ITEM structure [Audio Devices], *PPCEVENT_ITEM, PPCEVENT_ITEM structure pointer [Audio Devices], audpc-struct_54e5d50f-6902-47d3-8170-3ee459b8dfb8.xml, portcls/PPCEVENT_ITEM, audio.pcevent_item, portcls/PCEVENT_ITEM, PCEVENT_ITEM, PPCEVENT_ITEM
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	portcls.h
apiname:
-	PCEVENT_ITEM
product:
- Windows
targetos: Windows
req.typenames: PCEVENT_ITEM, *PPCEVENT_ITEM
---

# PCEVENT_ITEM structure


## -description


The <b>PCEVENT_ITEM</b> structure is used to describe an event that is supported by a particular filter, pin, or node.


## -syntax


````
typedef struct {
  const GUID         *Set;
  ULONG              Id;
  ULONG              Flags;
  PCPFNEVENT_HANDLER Handler;
} PCEVENT_ITEM, *PPCEVENT_ITEM;
````


## -struct-fields




### -field portcls.Set




### -field portcls.Id




### -field portcls.Flags




### -field portcls.Handler





#### - Set

Specifies the event set. This member is a pointer to a GUID that uniquely identifies the event set. See the list of event-set GUIDs in <a href="https://msdn.microsoft.com/library/windows/hardware/ff536195">Audio Drivers Event Sets</a>.


#### - Id

Specifies the event ID. This member identifies an event item within the event set. If the event set contains N items, valid event IDs are integers in the range 0 to N-1.


#### - Flags

Specifies the type of event. This member is set to one of the following values:




#### PCEVENT_ITEM_FLAG_ENABLE

Indicates the event notification should be enabled for this event type. The driver should continue event notification until the client explicitly disables it.


#### PCEVENT_ITEM_FLAG_ONESHOT

Indicates that the event notification should be enabled for the next occurrence of this event only. The client does not (and should not) disable the event once it has occurred.


#### PCEVENT_ITEM_FLAG_BASICSUPPORT

If the client specifies this flag, the driver returns STATUS_SUCCESS if it supports the event and an error code if it does not.


#### - Handler

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
</table></span></div>When calling the <b>Handler</b> routine, the caller passes in a single call parameter, which is a pointer to a caller-allocated <a href="..\portcls\ns-portcls-_pcevent_request.md">PCEVENT_REQUEST</a> structure.


## -remarks


The <b>PCEVENT_ITEM</b> structure specifies a particular event item in an automation table. The <a href="..\portcls\ns-portcls-__unnamed_struct_0c93_6.md">PCAUTOMATION_TABLE</a> structure points to an array of <b>PCEVENT_ITEM</b> structures.

In WDM audio, the target for an event request is either a pin instance or a node on a pin. A filter instance cannot be the target of an event request.



## -see-also

<a href="..\portcls\ns-portcls-__unnamed_struct_0c93_6.md">PCAUTOMATION_TABLE</a>

<a href="..\portcls\ns-portcls-_pcevent_request.md">PCEVENT_REQUEST</a>

 

 


