---
UID: NN:portcls.IServiceSink
title: IServiceSink
author: windows-driver-content
description: The IServiceSink interface encapsulates handling of a service request.
old-location: audio\iservicesink.htm
old-project: audio
ms.assetid: 329ae226-02fb-438b-b461-da51e3afd6eb
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: IServiceSink, IServiceSink interface [Audio Devices], IServiceSink interface [Audio Devices], described, audio.iservicesink, audmp-routines_68a03e77-6246-44e7-acad-6de0fbe10c41.xml, portcls/IServiceSink
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IServiceSink
product:
- Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IServiceSink interface


## -description


The <code>IServiceSink</code> interface encapsulates handling of a service request. The source of the service request is typically the miniport driver's interrupt service routine. PortCls supports the <code>IServiceSink</code> interface. An <code>IServiceSink</code> object is typically a member of a service group that is managed by an <a href="https://msdn.microsoft.com/library/windows/hardware/ff536994">IServiceGroup</a> object. <code>IServiceSink</code> inherits from the <b>IUnknown</b> interface.

<code>IServiceSink</code> is the base interface for <b>IServiceGroup</b>. This allows an <b>IServiceGroup</b> object to add itself (as an object with an <code>IServiceSink</code> interface) to another <b>IServiceGroup</b> object's service group.

Although the PortCls system driver provides a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537719">PcNewServiceGroup</a> function for creating a service group object, no similar function exists for creating a service sink object. Instead, a driver object that requires a service sink simply implements an <code>IServiceSink</code> interface in the driver object. For convenience, header file portcls.h includes an <b>IMP_IServiceSink</b> constant for adding the <code>IServiceSink</code> implementation to the object's class definition. The cost of adding an <code>IServiceSink</code> interface to an object is small because the interface supports only a single method. A port driver typically adds an <code>IServiceSink</code> interface to its port object and stream objects so that they can receive notification of interrupts from an audio device.

For more information, see <a href="https://msdn.microsoft.com/00e17e01-8889-4fae-a0ff-e110d7a9b21e">Service Sink and Service Group Objects</a>.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IServiceSink</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IServiceSink</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IServiceSink</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537009">IServiceSink::RequestService</a>
</td>
<td align="left" width="63%">
The <code>RequestService</code> method is called to forward a service request to an <b>IServiceSink</b> object.

</td>
</tr>
</table> 

