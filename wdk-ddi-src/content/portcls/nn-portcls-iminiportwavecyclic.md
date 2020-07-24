---
UID: NN:portcls.IMiniportWaveCyclic
title: IMiniportWaveCyclic (portcls.h)
description: The IMiniportWaveCyclic interface is the primary interface that is exposed by the miniport driver for a WaveCyclic audio device.
old-location: audio\iminiportwavecyclic.htm
tech.root: audio
ms.assetid: 12f19ef8-ce7c-4a04-814a-a8c34beca1b9
ms.date: 05/08/2018
keywords: ["IMiniportWaveCyclic interface"]
ms.keywords: IMiniportWaveCyclic, IMiniportWaveCyclic interface [Audio Devices], IMiniportWaveCyclic interface [Audio Devices],described, audio.iminiportwavecyclic, audmp-routines_e9dda3e8-2545-4734-bf66-e08ff0c4a1e0.xml, portcls/IMiniportWaveCyclic
f1_keywords:
 - "portcls/IMiniportWaveCyclic"
 - "IMiniportWaveCyclic"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- portcls.h
api_name:
- IMiniportWaveCyclic
targetos: Windows
req.typenames: 
---

# IMiniportWaveCyclic interface


## -description


The <code>IMiniportWaveCyclic</code> interface is the primary interface that is exposed by the miniport driver for a WaveCyclic audio device. The WaveCyclic port driver communicates with the miniport driver through this interface. The adapter driver creates the WaveCyclic miniport object and passes the object's <code>IMiniportWaveCyclic</code> interface pointer to the WaveCyclic port driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iport-init">IPort::Init</a> method (see the code example in <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/subdevice-creation">Subdevice Creation</a>). <code>IMiniportWaveCyclic</code> inherits from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiport">IMiniport</a> interface.

An adapter driver forms a miniport/port driver pair by binding an <code>IMiniportWaveCyclic</code> object to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iportwavecyclic">IPortWaveCyclic</a> object. The PortCls system driver registers this pair with the system as a <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/wave-filters">wave filter</a>.

The <code>IMiniportWaveCyclic</code> interface provides a method for initializing the miniport object and a method for creating a miniport stream object. The stream object is associated with a pin on the WaveCyclic filter, which the adapter driver forms by binding the miniport object and the port object together.

