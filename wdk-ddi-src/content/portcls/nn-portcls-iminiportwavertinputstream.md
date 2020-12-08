---
UID: NN:portcls.IMiniportWaveRTInputStream
title: IMiniportWaveRTInputStream (portcls.h)
description: The IMiniportWaveRTInputStream interface represents the input wave stream that flows through a pin on the KS filter that wraps a WaveRT rendering or capture device. IMiniportWaveRTInputStream inherits from the IUnknown interface.
old-location: audio\iminiportwavertinputstream.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["IMiniportWaveRTInputStream interface"]
ms.keywords: IMiniportWaveRTInputStream, IMiniportWaveRTInputStream interface [Audio Devices], IMiniportWaveRTInputStream interface [Audio Devices],described, audio.iminiportwavertinputstream, portcls/IMiniportWaveRTInputStream
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
 - IMiniportWaveRTInputStream
 - portcls/IMiniportWaveRTInputStream
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IMiniportWaveRTInputStream
---

# IMiniportWaveRTInputStream interface


## -description

The <code>IMiniportWaveRTInputStream</code> interface represents the input wave stream that flows through a pin on the KS filter that wraps a WaveRT rendering or capture device. <code>IMiniportWaveRTInputStream</code> inherits from the <b>IUnknown</b> interface.

A driver can implement this interface for better coordination of audio dataflow from the driver to OS. If this interface is available on a capture stream, the OS uses methods on this interface to access data in the WaveRt buffer. 
     <code>IMiniportWaveRTInputStream</code> is supported in Windows 10 and later.

