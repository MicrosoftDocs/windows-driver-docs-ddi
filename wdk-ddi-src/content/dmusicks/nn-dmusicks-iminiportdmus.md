---
UID: NN:dmusicks.IMiniportDMus
title: IMiniportDMus
author: windows-driver-content
description: The IMiniportDMus interface is the primary interface for a DMus miniport driver for a DirectMusic synthesizer device.
old-location: audio\iminiportdmus.htm
old-project: audio
ms.assetid: 12cd3533-1830-46cd-a1eb-350f7461a61d
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: IMiniportDMus, IMiniportDMus interface [Audio Devices], IMiniportDMus interface [Audio Devices],described, audio.iminiportdmus, audmp-routines_b123c50b-e4b9-4f19-a2c4-b33fb335bec6.xml, dmusicks/IMiniportDMus
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: dmusicks.h
req.include-header: Dmusicks.h
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
-	COM
api_location:
-	dmusicks.h
api_name:
-	IMiniportDMus
product: Windows
targetos: Windows
req.typenames: 
---

# IMiniportDMus interface


## -description


The <code>IMiniportDMus</code> interface is the primary interface for a DMus miniport driver for a DirectMusic synthesizer device. The DMus port driver communicates with the miniport driver through this interface. The adapter driver creates the DMus miniport object and passes the object's <code>IMiniportDMus</code> interface pointer to the port driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536943">IPort::Init</a> method (see the code example in <a href="https://msdn.microsoft.com/e4ba1209-adc6-48c3-9633-247e9e3849bc">Subdevice Creation</a>). <code>IMiniportDMus</code> inherits from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536698">IMiniport</a> interface.

An adapter driver forms a miniport/port driver pair by binding an <code>IMiniportDMus</code> object to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff536879">IPortDMus</a> object. The PortCls system driver registers this pair with the system as a DirectMusic filter (see <a href="https://msdn.microsoft.com/622aa4ae-c855-4088-bc1a-30dff7a24d23">MIDI and DirectMusic Filters</a>).

The <code>IMiniportDMus</code> interface provides methods for initializing the miniport driver, for creating a new DirectMusic stream, and for notifying the miniport driver of an interrupt service request.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IMiniportDMus</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IMiniportDMus</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IMiniportDMus</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536700">IMiniportDMus::Init</a>
</td>
<td align="left" width="63%">
The <code>Init</code> method initializes the DMus miniport object.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536701">IMiniportDMus::NewStream</a>
</td>
<td align="left" width="63%">
The <code>NewStream</code> method creates a new instance of a logical stream associated with a specified physical channel.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536702">IMiniportDMus::Service</a>
</td>
<td align="left" width="63%">

   This method does not currently need to be implemented in the miniport driver. The<code> Service</code> method is currently unused.

</td>
</tr>
</table> 

