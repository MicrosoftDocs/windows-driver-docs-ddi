---
UID: NN:dmusicks.IMasterClock
title: IMasterClock
author: windows-driver-content
description: The IMasterClock interface provides Microsoft DirectMusic streams with access to the current reference time from the master clock.
old-location: audio\imasterclock.htm
old-project: audio
ms.assetid: 754aad8a-834c-4197-8505-dbf1cd74c697
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: IMasterClock, IMasterClock interface [Audio Devices], IMasterClock interface [Audio Devices], described, audio.imasterclock, audmp-routines_b8172e0e-55ac-4abd-8b62-39be5d708f9b.xml, dmusicks/IMasterClock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: dmusicks.h
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
-	dmusicks.h
api_name:
-	IMasterClock
product: Windows
targetos: Windows
req.typenames: DMUS_STREAM_TYPE
---

# IMasterClock interface


## -description


The <code>IMasterClock</code> interface provides Microsoft DirectMusic streams with access to the current reference time from the <a href="https://msdn.microsoft.com/bdd228c1-a15f-4c08-8991-299a3f2e1ee8">master clock</a>. The DMus port driver implements this interface to support accurate timing in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536782">IMXF</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff536491">IAllocatorMXF</a> interfaces that make up the MIDI-transport part of the filter graph. When calling a DMus miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536701">IMiniportDMus::NewStream</a> method, the DMus port driver passes an <code>IMasterClock</code> reference as a call parameter. The <code>IMasterClock</code> interface wraps the master clock, as described in <a href="https://msdn.microsoft.com/3cdd4c69-d99d-48bc-a1d9-9da2a2511e94">Latency Clocks</a>. 


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IMasterClock</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IMasterClock</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IMasterClock</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536697">IMasterClock::GetTime</a>
</td>
<td align="left" width="63%">
The <code>GetTime</code> method retrieves the current reference time read from the master clock.

</td>
</tr>
</table> 

