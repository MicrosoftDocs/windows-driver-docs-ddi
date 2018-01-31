---
UID: NN:portcls.IMiniportWaveCyclicStream
title: IMiniportWaveCyclicStream
author: windows-driver-content
description: The IMiniportWaveCyclicStream interface represents the wave stream that flows through a pin on a WaveCyclic filter.
old-location: audio\iminiportwavecyclicstream.htm
old-project: audio
ms.assetid: d1a4bc2e-6f4c-4d40-954b-9dd622490027
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: audio.iminiportwavecyclicstream, IMiniportWaveCyclicStream interface [Audio Devices], IMiniportWaveCyclicStream interface [Audio Devices], described, IMiniportWaveCyclicStream, portcls/IMiniportWaveCyclicStream, audmp-routines_4b32bc10-e6c0-455a-9aa6-f53538b3c7ec.xml
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
-	IMiniportWaveCyclicStream
product: Windows
targetos: Windows
req.typenames: "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---

# IMiniportWaveCyclicStream interface


## -description


The <code>IMiniportWaveCyclicStream</code> interface represents the wave stream that flows through a pin on a WaveCyclic filter. The filter wraps a WaveCyclic rendering or capture device and is implemented by pairing a WaveCyclic port driver with a WaveCyclic miniport driver. The miniport driver implements the <code>IMiniportWaveCyclicStream</code> interface and exposes it to the port driver. The miniport driver creates a stream object with this interface when the port driver calls the miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536723">IMiniportWaveCyclic::NewStream</a> method. <code>IMiniportWaveCyclicStream</code> inherits from the <b>IUnknown</b> interface.

The <code>IMiniportWaveCyclicStream</code> interface provides methods for managing a single stream of incoming or outgoing audio wave data. This is the interface that exposes most of the miniport driver's functionality.

