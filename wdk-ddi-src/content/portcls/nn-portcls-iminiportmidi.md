---
UID: NN:portcls.IMiniportMidi
title: IMiniportMidi (portcls.h)
description: The IMiniportMidi interface is the primary interface for a MIDI miniport driver for a MIDI synthesizer device.
old-location: audio\iminiportmidi.htm
tech.root: audio
ms.assetid: 42170a24-377c-4cc5-962e-97ed74302d63
ms.date: 05/08/2018
keywords: ["IMiniportMidi interface"]
ms.keywords: IMiniportMidi, IMiniportMidi interface [Audio Devices], IMiniportMidi interface [Audio Devices],described, audio.iminiportmidi, audmp-routines_bba7ae00-6719-49dd-9770-9292a96f42ec.xml, portcls/IMiniportMidi
f1_keywords:
 - "portcls/IMiniportMidi"
 - "IMiniportMidi"
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
- IMiniportMidi
product:
- Windows
targetos: Windows
req.typenames: 
---

# IMiniportMidi interface


## -description


The <code>IMiniportMidi</code> interface is the primary interface for a MIDI miniport driver for a MIDI synthesizer device. The MIDI port driver communicates with the miniport driver through this interface. The adapter driver creates the MIDI miniport object and passes the object's <code>IMiniportMidi</code> interface pointer to the MIDI port driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iport-init">IPort::Init</a> method (see the code example in <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/subdevice-creation">Subdevice Creation</a>). <code>IMiniportMidi</code> inherits from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiport">IMiniport</a> interface.

An adapter driver forms a miniport/port driver pair by binding an <code>IMiniportMidi</code> object to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iportmidi">IPortMidi</a> object. The PortCls system driver registers this pair with the system as a MIDI filter (see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/midi-and-directmusic-filters">MIDI and DirectMusic Filters</a>).

The <code>IMiniportMidi</code> interface provides methods for initializing the miniport object, for creating a new MIDI stream, and for notifying the miniport driver of an interrupt service request.

