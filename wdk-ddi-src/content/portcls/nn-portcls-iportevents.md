---
UID: NN:portcls.IPortEvents
title: IPortEvents
author: windows-driver-content
description: The IPortEvents interface is used by miniport drivers to notify clients of hardware events.
old-location: audio\iportevents.htm
old-project: audio
ms.assetid: bbbb5486-1217-4c4d-9421-96994a5fec82
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: audio.iportevents, IPortEvents interface [Audio Devices], IPortEvents interface [Audio Devices], described, IPortEvents, portcls/IPortEvents, audmp-routines_8e6cf7c4-af42-4c89-8c00-29470317a455.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: portcls.h
req.include-header: 
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
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	portcls.h
apiname:
-	IPortEvents
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IPortEvents interface


## -description


The <code>IPortEvents</code> interface is used by miniport drivers to notify clients of <a href="https://msdn.microsoft.com/b91e02dd-0de4-4de3-ade6-778339ce47a8">hardware events</a>. In Windows 98/Me and in Windows 2000 and later, all port drivers in portcls.sys implement this interface and expose it to miniport drivers. To determine whether a port driver supports the <code>IPortEvents</code> interface, the miniport driver calls the IPort<i>Xxx</i> object's <b>QueryInterface</b> method with REFIID <b>IID_IPortEvents</b>. <code>IPortEvents</code> inherits from the <b>IUnknown</b> interface.

Drivers typically use the <code>IPortEvents</code> interface to notify the system of hardware-generated volume or mute changes, although <code>IPortEvents</code> can be used for any type of event notification. <code>IPortEvents</code> interface is an optional lower-edge port driver interface. It can be used, for example, to notify <b>mixer</b> applications of control or mixer-line changes. For information about the <b>mixer</b> API, see the Microsoft Windows SDK documentation.

A miniport driver exposes an event in the same way that it exposes properties: through an automation table (see <a href="..\portcls\ns-portcls-__unnamed_struct_0cb6_6.md">PCAUTOMATION_TABLE</a>). The following objects, all of which are exposed by the miniport driver, can specify an automation table that contains properties and/or events:
<ul>
<li>
The filter that the miniport driver implements

</li>
<li>
Each pin that the filter exposes

</li>
<li>
Each node that the filter exposes

</li>
</ul>Each event entry in an automation table is a structure of type <a href="..\portcls\ns-portcls-__unnamed_struct_0cb6_5.md">PCEVENT_ITEM</a> that specifies the following:
<ul>
<li>
An event set

</li>
<li>
An event within the set

</li>
<li>
Flags indicating support options

</li>
<li>
A function pointer to the handler for the event

</li>
</ul>Once the adapter driver is started and its port/miniport driver pairs have been registered as filters with the system, the <a href="https://msdn.microsoft.com/067944fb-6854-4ae8-81ca-9b8f2eed939e">WDMAud system driver</a>, which translates <b>mixer</b> API calls into KS commands to WDM audio drivers, will open each port/miniport driver pair and interrogate its capabilities. During this process, WDMAud will traverse the miniport driver's filter topology in search of a control node that supports a hardware event. The event is represented by the combination of event-set GUID <a href="https://msdn.microsoft.com/library/windows/hardware/ff537122">KSEVENTSETID_AudioControlChange</a> and event ID <a href="https://msdn.microsoft.com/library/windows/hardware/ff537128">KSEVENT_CONTROL_CHANGE</a>. When WdmAud finds these, it enables the event, effectively registering itself as a client of the event. Subsequently, each time the miniport driver signals the event, this notifies WDMAud, which generates the appropriate windows messages for its clients.

In addition to exposing the event in the automation table, a miniport driver that needs to expose events should query the port driver for its <code>IPortEvents</code> interface.

This section also describes the following routine for handling event requests:
<dl>
<dd>

<a href="..\portcls\nc-portcls-pcpfnevent_handler.md">EventHandler</a>


</dd>
</dl>
