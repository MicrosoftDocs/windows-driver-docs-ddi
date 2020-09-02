---
UID: NN:portcls.IMiniportWaveCyclicStream
title: IMiniportWaveCyclicStream (portcls.h)
description: The IMiniportWaveCyclicStream interface represents the wave stream that flows through a pin on a WaveCyclic filter.
old-location: audio\iminiportwavecyclicstream.htm
tech.root: audio
ms.assetid: d1a4bc2e-6f4c-4d40-954b-9dd622490027
ms.date: 05/08/2018
keywords: ["IMiniportWaveCyclicStream interface"]
ms.keywords: IMiniportWaveCyclicStream, IMiniportWaveCyclicStream interface [Audio Devices], IMiniportWaveCyclicStream interface [Audio Devices],described, audio.iminiportwavecyclicstream, audmp-routines_4b32bc10-e6c0-455a-9aa6-f53538b3c7ec.xml, portcls/IMiniportWaveCyclicStream
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IMiniportWaveCyclicStream
 - portcls/IMiniportWaveCyclicStream
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IMiniportWaveCyclicStream
---

# IMiniportWaveCyclicStream interface


## -description

The <code>IMiniportWaveCyclicStream</code> interface represents the wave stream that flows through a pin on a WaveCyclic filter. The filter wraps a WaveCyclic rendering or capture device and is implemented by pairing a WaveCyclic port driver with a WaveCyclic miniport driver. The miniport driver implements the <code>IMiniportWaveCyclicStream</code> interface and exposes it to the port driver. The miniport driver creates a stream object with this interface when the port driver calls the miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportwavecyclic-newstream">IMiniportWaveCyclic::NewStream</a> method. <code>IMiniportWaveCyclicStream</code> inherits from the <b>IUnknown</b> interface.

The <code>IMiniportWaveCyclicStream</code> interface provides methods for managing a single stream of incoming or outgoing audio wave data. This is the interface that exposes most of the miniport driver's functionality.

