---
UID: NN:portcls.IPowerNotify
title: IPowerNotify
author: windows-driver-content
description: The IPowerNotify interface is an optional interface that miniport drivers can expose if they require advance notification of impending power-state changes.
old-location: audio\ipowernotify.htm
old-project: audio
ms.assetid: f4856f40-b462-4e69-9324-a2cc837b2893
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: IPowerNotify, IPowerNotify interface [Audio Devices], IPowerNotify interface [Audio Devices],described, audio.ipowernotify, audmp-routines_345bcede-d886-4423-b56e-0b7c15596744.xml, portcls/IPowerNotify
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IPowerNotify
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPowerNotify interface


## -description


The <code>IPowerNotify</code> interface is an optional interface that miniport drivers can expose if they require advance notification of impending power-state changes. To determine whether the miniport driver supports the <code>IPowerNotify</code> interface, the port driver calls the miniport driver object's <b>QueryInterface</b> method with REFIID <b>IID_IPowerNotify</b>. The following miniport driver types can support <code>IPowerNotify</code>:
<dl>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536724">IMiniportWavePci</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536714">IMiniportWaveCyclic</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536703">IMiniportMidi</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536699">IMiniportDMus</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536712">IMiniportTopology</a>


</dd>
</dl><code>IPowerNotify</code> inherits from the <b>IUnknown</b> interface.

The <code>IPowerNotify</code> interface provides a single method that the port driver calls to notify the miniport driver when a change in power state occurs.

For example, when the operating system tells a wave audio device to go to a sleep state, the port driver pauses any active streams and then calls the power-notification callback to inform the miniport driver of the impending power down. The miniport driver then has an opportunity to save any necessary context before the adapter's <b>PowerChangeState</b> method is called.

The process is reversed when the device is powering up. PortCls first calls the adapter's <b>PowerChangeState</b> method to power up the adapter. The port driver then calls the miniport driver's callback to allow the miniport driver to restore its context. Finally, the port driver unpauses any previously paused active audio streams.

For more information, see <a href="https://msdn.microsoft.com/8bd8b4c8-1961-41ea-ba98-41e3a732ed37">Implementing IPowerNotify</a>.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPowerNotify</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IPowerNotify</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPowerNotify</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536949">IPowerNotify::PowerChangeNotify</a>
</td>
<td align="left" width="63%">
The <code>PowerChangeNotify</code> method notifies the miniport driver of changes in the power state.

</td>
</tr>
</table> 

