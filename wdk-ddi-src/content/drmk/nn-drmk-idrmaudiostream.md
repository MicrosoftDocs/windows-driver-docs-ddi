---
UID: NN:drmk.IDrmAudioStream
title: IDrmAudioStream
author: windows-driver-content
description: The IDrmAudioStream interface assigns DRM protection to the digital content in an audio stream.
old-location: audio\idrmaudiostream.htm
old-project: audio
ms.assetid: 18c90367-f87d-4028-af58-cfb65e8ff01b
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: IDrmAudioStream, IDrmAudioStream interface [Audio Devices], IDrmAudioStream interface [Audio Devices], described, audio.idrmaudiostream, audmp-routines_aba04fe2-a050-48c5-82ba-3ce454e0bc84.xml, drmk/IDrmAudioStream
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: drmk.h
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
req.lib: drmk.h
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	drmk.h
api_name:
-	IDrmAudioStream
product: Windows
targetos: Windows
req.typenames: WDI_TX_METADATA, *PWDI_TX_METADATA
---

# IDrmAudioStream interface


## -description


The <code>IDrmAudioStream</code> interface assigns DRM protection to the digital content in an audio stream. (For information about DRM-protected content, see <a href="https://msdn.microsoft.com/7ce19196-5180-421f-b6be-ac4a235a8c16">Digital Rights Management</a>) This interface is implemented by a WaveCyclic or WavePci miniport driver and is exposed to the WaveCyclic or WavePci port driver. To determine whether a miniport driver supports this interface, the WaveCyclic or WavePci port driver calls the miniport stream object's <b>QueryInterface</b> method with REFIID <b>IID_IDrmAudioStream</b>. <code>IDrmAudioStream</code> inherits from the <b>IUnknown</b> interface.

The port driver uses the <code>IDrmAudioStream</code> interface if it is supported by either of the following stream objects:
<ul>
<li>
A stream object created by <a href="https://msdn.microsoft.com/library/windows/hardware/ff536723">IMiniportWaveCyclic::NewStream</a>


</li>
<li>
A stream object created by <a href="https://msdn.microsoft.com/library/windows/hardware/ff536735">IMiniportWavePci::NewStream</a>


</li>
</ul>
