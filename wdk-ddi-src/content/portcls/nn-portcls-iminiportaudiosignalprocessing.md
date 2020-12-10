---
UID: NN:portcls.IMiniportAudioSignalProcessing
title: IMiniportAudioSignalProcessing (portcls.h)
description: The IMiniportAudioSignalProcessing interface is implemented by the WaveRT miniport component of any audio driver, if any of its pins support audio signal processing modes.
old-location: audio\iminiportaudiosignalprocessing.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["IMiniportAudioSignalProcessing interface"]
ms.keywords: IMiniportAudioSignalProcessing, IMiniportAudioSignalProcessing interface [Audio Devices], IMiniportAudioSignalProcessing interface [Audio Devices],described, audio.iminiportaudiosignalprocessing, portcls/IMiniportAudioSignalProcessing
req.header: portcls.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
 - IMiniportAudioSignalProcessing
 - portcls/IMiniportAudioSignalProcessing
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Portcls.h
api_name:
 - IMiniportAudioSignalProcessing
---

# IMiniportAudioSignalProcessing interface


## -description

The IMiniportAudioSignalProcessing interface is implemented by the WaveRT miniport component of any audio driver, if any of its pins support audio signal processing modes.

## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IMiniportAudioSignalProcessing</b> interface inherits from the <a href="/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IMiniportAudioSignalProcessing</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -remarks

Any of the Portcls miniport drivers can also implement the <b>GetModes</b> method.
