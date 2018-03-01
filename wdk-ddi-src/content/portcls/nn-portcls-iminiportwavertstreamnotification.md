---
UID: NN:portcls.IMiniportWaveRTStreamNotification
title: IMiniportWaveRTStreamNotification
author: windows-driver-content
description: The IMiniportWaveRTStreamNotification interface is supported in Windows Vista and later Windows operating systems, and it augments the IMiniportWaveRTStream interface, providing additional methods to facilitate DMA driver event notifications.
old-location: audio\iminiportwavertstreamnotification.htm
old-project: audio
ms.assetid: e009c459-77f7-43ee-9e95-8408324b0a9b
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IMiniportWaveRTStreamNotification, IMiniportWaveRTStreamNotification interface [Audio Devices], IMiniportWaveRTStreamNotification interface [Audio Devices], described, audio.iminiportwavertstreamnotification, audmp-routines_a49bf74b-367b-44f4-b8de-a3adf6240b36.xml, portcls/IMiniportWaveRTStreamNotification
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IMiniportWaveRTStreamNotification
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportWaveRTStreamNotification interface


## -description


The <code>IMiniportWaveRTStreamNotification</code> interface is supported in Windows Vista and later Windows operating systems, and it augments the <a href="..\portcls\nn-portcls-iminiportwavertstream.md">IMiniportWaveRTStream</a> interface, providing additional methods to facilitate DMA driver event notifications. 

To access the <code>IMiniportWaveRTStreamNotification</code> interface, the <a href="https://msdn.microsoft.com/d25e37e2-2e29-4bf9-8150-221ebef88c87">WaveRT port driver</a> calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536762">IMiniportWaveRT::NewStream</a> method and receives an <a href="..\portcls\nn-portcls-iminiportwavertstream.md">IMiniportWaveRTStream</a> interface. The WaveRT port driver then queries the <b>IMiniportWaveRTStream</b> interface, uisng QueryInterface, and receives the <code>IMiniportWaveRTStreamNotification</code> interface. 

<code>IMiniportWaveRTStreamNotification</code> inherits from the <b>IUnknown</b> interface.

