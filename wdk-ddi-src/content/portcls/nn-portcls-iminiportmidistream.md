---
UID: NN:portcls.IMiniportMidiStream
title: IMiniportMidiStream
author: windows-driver-content
description: The IMiniportMidiStream interface represents the MIDI stream that flows through a pin on a MIDI filter.
old-location: audio\iminiportmidistream.htm
old-project: audio
ms.assetid: a3b763af-2800-4e6d-b9f8-060ba80de7e6
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: IMiniportMidiStream, IMiniportMidiStream interface [Audio Devices], IMiniportMidiStream interface [Audio Devices], described, audio.iminiportmidistream, audmp-routines_604abeae-e44f-418a-913f-39502b6f266b.xml, portcls/IMiniportMidiStream
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
-	IMiniportMidiStream
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportMidiStream interface


## -description


The <code>IMiniportMidiStream</code> interface represents the MIDI stream that flows through a pin on a MIDI filter. The filter wraps a MIDI synthesizer or capture device and is implemented by pairing a MIDI port driver with a MIDI miniport driver. The miniport driver implements the <code>IMiniportMidiStream</code> interface and exposes it to the port driver. The port driver creates a stream object with this interface by calling the miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536710">IMiniportMidi::NewStream</a> method. <code>IMiniportMidiStream</code> inherits from the <b>IUnknown</b> interface.

 This interface provides methods for reading and writing a MIDI stream and for setting the format and state of a MIDI stream.

