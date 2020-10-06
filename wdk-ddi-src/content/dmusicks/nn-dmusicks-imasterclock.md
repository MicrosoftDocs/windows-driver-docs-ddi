---
UID: NN:dmusicks.IMasterClock
title: IMasterClock (dmusicks.h)
description: The IMasterClock interface provides Microsoft DirectMusic streams with access to the current reference time from the master clock.
old-location: audio\imasterclock.htm
tech.root: audio
ms.assetid: 754aad8a-834c-4197-8505-dbf1cd74c697
ms.date: 05/08/2018
keywords: ["IMasterClock interface"]
ms.keywords: IMasterClock, IMasterClock interface [Audio Devices], IMasterClock interface [Audio Devices],described, audio.imasterclock, audmp-routines_b8172e0e-55ac-4abd-8b62-39be5d708f9b.xml, dmusicks/IMasterClock
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IMasterClock
 - dmusicks/IMasterClock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dmusicks.h
api_name:
 - IMasterClock
---

# IMasterClock interface


## -description

The <code>IMasterClock</code> interface provides Microsoft DirectMusic streams with access to the current reference time from the <a href="/windows-hardware/drivers/stream/master-clocks">master clock</a>. The DMus port driver implements this interface to support accurate timing in the <a href="/windows-hardware/drivers/ddi/dmusicks/nn-dmusicks-imxf">IMXF</a> and <a href="/windows-hardware/drivers/ddi/dmusicks/nn-dmusicks-iallocatormxf">IAllocatorMXF</a> interfaces that make up the MIDI-transport part of the filter graph. When calling a DMus miniport driver's <a href="/windows-hardware/drivers/ddi/dmusicks/nf-dmusicks-iminiportdmus-newstream">IMiniportDMus::NewStream</a> method, the DMus port driver passes an <code>IMasterClock</code> reference as a call parameter. The <code>IMasterClock</code> interface wraps the master clock, as described in <a href="/windows-hardware/drivers/audio/latency-clocks">Latency Clocks</a>.

## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IMasterClock</b> interface inherits from the <a href="/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IMasterClock</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>