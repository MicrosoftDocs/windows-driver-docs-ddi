---
UID: NN:portcls.IMiniportWaveRTStream
title: IMiniportWaveRTStream (portcls.h)
description: The IMiniportWaveRTStream interface represents the wave stream that flows through a pin on the KS filter that wraps a WaveRT rendering or capture device.
old-location: audio\iminiportwavertstream.htm
tech.root: audio
ms.assetid: be398a37-0329-411b-ba41-a03dbc5f72a1
ms.date: 03/19/2018
ms.keywords: IMiniportWaveRTStream, IMiniportWaveRTStream interface [Audio Devices], IMiniportWaveRTStream interface [Audio Devices], described, audio.iminiportwavertstream, audmp-routines_9f8c9dbe-8e68-4b7b-b2de-b409d77f15d6.xml, portcls/IMiniportWaveRTStream
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
-	IMiniportWaveRTStream
product:
- Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportWaveRTStream interface


## -description


The <code>IMiniportWaveRTStream</code> interface represents the wave stream that flows through a pin on the KS filter that wraps a WaveRT rendering or capture device. The miniport driver implements the <code>IMiniportWaveRTStream</code> interface and exposes it to the port driver. The miniport driver creates a stream object with this interface when the port driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536762">IMiniportWaveRT::NewStream</a> method. <code>IMiniportWaveRTStream</code> inherits from the <b>IUnknown</b> interface.

<code>IMiniportWaveRTStream</code> is supported in Windows Vista and later Windows operating systems.

