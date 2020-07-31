---
UID: NN:portcls.IMiniportTopology
title: IMiniportTopology (portcls.h)
description: The IMiniportTopology interface is the primary interface of a Topology miniport driver.
old-location: audio\iminiporttopology.htm
tech.root: audio
ms.assetid: f66129df-07c4-4472-aa14-6c4d9578a92d
ms.date: 05/08/2018
keywords: ["IMiniportTopology interface"]
ms.keywords: IMiniportTopology, IMiniportTopology interface [Audio Devices], IMiniportTopology interface [Audio Devices],described, audio.iminiporttopology, audmp-routines_c2137cf2-ab04-4b0b-aeda-d50fe3225324.xml, portcls/IMiniportTopology
f1_keywords:
 - "portcls/IMiniportTopology"
 - "IMiniportTopology"
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
- IMiniportTopology
targetos: Windows
req.typenames: 
---

# IMiniportTopology interface


## -description


The <code>IMiniportTopology</code> interface is the primary interface of a Topology miniport driver. Through this interface, the miniport driver exposes the topology of the mixing circuitry in an audio adapter. In a typical adapter, this circuitry mixes together the playback streams from the wave renderer and MIDI synthesizer. The Topology port driver communicates with the miniport driver through the <code>IMiniportTopology</code> interface. The adapter driver creates the topology miniport object and passes the object's <code>IMiniportTopology</code> interface pointer to the topology port driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iport-init">IPort::Init</a> method (see the code example in <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/subdevice-creation">Subdevice Creation</a>). <code>IMiniportTopology</code> inherits from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiport">IMiniport</a> interface.

An adapter driver forms a miniport/port driver pair by binding an <code>IMiniportTopology</code> object to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iporttopology">IPortTopology</a> object. The PortCls system driver registers this pair with the system as a <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/topology-filters">topology filter</a>.

Through a sequence of property requests, the <b>mixer</b> API uses the topology filter to enumerate the pins, nodes, and connections that comprise the internal topology of the audio adapter. The filter also supports the acquisition of control-change information. The pins of a topology filter represent hardwired connections within the adapter and therefore cannot be instantiated. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/kernel-streaming-topology-to-audio-mixer-api-translation">Kernel Streaming Topology to Audio Mixer API Translation</a>.

