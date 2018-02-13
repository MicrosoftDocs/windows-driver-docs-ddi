---
UID: NN:dmusicks.IMXF
title: IMXF
author: windows-driver-content
description: The IMXF interface represents the DirectMusic stream on a MIDI transport filter (MXF).
old-location: audio\imxf.htm
old-project: audio
ms.assetid: 97e24c86-a97d-42ed-9402-4c387c7cec5b
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: audio.imxf, IMXF interface [Audio Devices], IMXF interface [Audio Devices], described, IMXF, dmusicks/IMXF, audmp-routines_41562676-678d-48c5-8a19-2c8699420a51.xml
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
req.lib: dmusicks.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dmusicks.h
apiname:
-	IMXF
product: Windows
targetos: Windows
req.typenames: DMUS_STREAM_TYPE
---

# IMXF interface


## -description


The <code>IMXF</code> interface represents the DirectMusic stream on a MIDI transport filter (MXF). The DMus miniport driver implements this interface and exposes it to the DMus port driver. MIDI transport occurs through IMXF, which is the DMus miniport driver's primary interface for managing DirectMusic streams. The DMus port driver uses this interface to manage a DirectMusic stream on a MIDI transport filter (MXF). The miniport driver creates a stream object with this interface when the port driver calls the miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536701">IMiniportDMus::NewStream</a> method. <code>IMXF</code> inherits from the <b>IUnknown</b> interface.

The <a href="..\dmusicks\nn-dmusicks-iallocatormxf.md">IAllocatorMXF</a> and <a href="..\dmusicks\nn-dmusicks-isynthsinkdmus.md">ISynthSinkDMus</a> interfaces both inherit from <code>IMXF</code>. For information about using these interfaces to manage MIDI streams, see <a href="https://msdn.microsoft.com/ce9ec589-0aea-4ed9-a60d-50f2ddfb0c13">MIDI Transport</a>.

