---
UID: NN:portcls.IMiniportWavePci
title: IMiniportWavePci (portcls.h)
description: The IMiniportWavePci interface is the primary interface that is exposed by the miniport driver for a WavePci audio device.
old-location: audio\iminiportwavepci.htm
tech.root: audio
ms.assetid: 74619f9b-cd67-47f2-8c67-6fb42b794b9a
ms.date: 05/08/2018
keywords: ["IMiniportWavePci interface"]
ms.keywords: IMiniportWavePci, IMiniportWavePci interface [Audio Devices], IMiniportWavePci interface [Audio Devices],described, audio.iminiportwavepci, audmp-routines_bd4a9d9c-d3eb-40bc-93d9-277abe4ee258.xml, portcls/IMiniportWavePci
f1_keywords:
 - "portcls/IMiniportWavePci"
 - "IMiniportWavePci"
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
- IMiniportWavePci
targetos: Windows
req.typenames: 
---

# IMiniportWavePci interface


## -description


The <code>IMiniportWavePci</code> interface is the primary interface that is exposed by the miniport driver for a WavePci audio device. The WavePci port driver communicates with the miniport driver through this interface. The adapter driver creates the WavePci miniport object and passes the object's <b>IMiniportPci</b> interface pointer to the WavePci port driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iport-init">IPort::Init</a> method (see code example in <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/subdevice-creation">Subdevice Creation</a>). <code>IMiniportWavePci</code> inherits from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiport">IMiniport</a> interface.

An adapter driver forms a miniport/port driver pair by binding an <code>IMiniportWavePci</code> object to an <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff536905(v=vs.85)">IPortWavePci</a> object. The PortCls system driver registers this pair with the system as a <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/wave-filters">wave filter</a>.

The <code>IMiniportWavePci</code> interface provides a method for initializing the miniport object, a method for creating a miniport stream object, and a method for notifying the miniport driver of a service request. The stream object is associated with a pin on the WavePci filter, which the adapter driver forms by binding the miniport object with the port object.

