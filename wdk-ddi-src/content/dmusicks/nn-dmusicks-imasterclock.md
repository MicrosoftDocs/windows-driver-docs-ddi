---
UID: NN:dmusicks.IMasterClock
title: IMasterClock
author: windows-driver-content
description: The IMasterClock interface provides Microsoft DirectMusic streams with access to the current reference time from the master clock.
old-location: audio\imasterclock.htm
old-project: audio
ms.assetid: 754aad8a-834c-4197-8505-dbf1cd74c697
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: ISynthSinkDMus, ISynthSinkDMus::SyncToMaster, SyncToMaster
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
req.alt-api: IMasterClock
req.alt-loc: dmusicks.h
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
req.typenames: DMUS_STREAM_TYPE
---

# IMasterClock interface



## -description
The <code>IMasterClock</code> interface provides Microsoft DirectMusic streams with access to the current reference time from the <a href="https://msdn.microsoft.com/bdd228c1-a15f-4c08-8991-299a3f2e1ee8">master clock</a>. The DMus port driver implements this interface to support accurate timing in the <a href="..\dmusicks\nn-dmusicks-imxf.md">IMXF</a> and <a href="..\dmusicks\nn-dmusicks-iallocatormxf.md">IAllocatorMXF</a> interfaces that make up the MIDI-transport part of the filter graph. When calling a DMus miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536701">IMiniportDMus::NewStream</a> method, the DMus port driver passes an <code>IMasterClock</code> reference as a call parameter. The <code>IMasterClock</code> interface wraps the master clock, as described in <a href="https://msdn.microsoft.com/3cdd4c69-d99d-48bc-a1d9-9da2a2511e94">Latency Clocks</a>. 



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IMasterClock</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IMasterClock</b> also has these types of members:

The <b>IMasterClock</b> interface has these methods.

The <code>GetTime</code> method retrieves the current reference time read from the master clock.

 


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
</table>The <code>GetTime</code> method retrieves the current reference time read from the master clock.

 


## -remarks
