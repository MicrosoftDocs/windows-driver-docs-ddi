---
UID: NN:dmusicks.IMiniportDMus
title: IMiniportDMus (dmusicks.h)
description: The IMiniportDMus interface is the primary interface for a DMus miniport driver for a DirectMusic synthesizer device.
old-location: audio\iminiportdmus.htm
tech.root: audio
ms.assetid: 12cd3533-1830-46cd-a1eb-350f7461a61d
ms.date: 05/08/2018
keywords: ["IMiniportDMus interface"]
ms.keywords: IMiniportDMus, IMiniportDMus interface [Audio Devices], IMiniportDMus interface [Audio Devices],described, audio.iminiportdmus, audmp-routines_b123c50b-e4b9-4f19-a2c4-b33fb335bec6.xml, dmusicks/IMiniportDMus
req.header: dmusicks.h
req.include-header: Dmusicks.h
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
 - IMiniportDMus
 - dmusicks/IMiniportDMus
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dmusicks.h
api_name:
 - IMiniportDMus
---

# IMiniportDMus interface


## -description

The <code>IMiniportDMus</code> interface is the primary interface for a DMus miniport driver for a DirectMusic synthesizer device. The DMus port driver communicates with the miniport driver through this interface. The adapter driver creates the DMus miniport object and passes the object's <code>IMiniportDMus</code> interface pointer to the port driver's <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iport-init">IPort::Init</a> method (see the code example in <a href="/windows-hardware/drivers/audio/subdevice-creation">Subdevice Creation</a>). <code>IMiniportDMus</code> inherits from the <a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiport">IMiniport</a> interface.

An adapter driver forms a miniport/port driver pair by binding an <code>IMiniportDMus</code> object to an <a href="/windows-hardware/drivers/ddi/dmusicks/nn-dmusicks-iportdmus">IPortDMus</a> object. The PortCls system driver registers this pair with the system as a DirectMusic filter (see <a href="/windows-hardware/drivers/audio/midi-and-directmusic-filters">MIDI and DirectMusic Filters</a>).

The <code>IMiniportDMus</code> interface provides methods for initializing the miniport driver, for creating a new DirectMusic stream, and for notifying the miniport driver of an interrupt service request.

## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IMiniportDMus</b> interface inherits from the <a href="/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IMiniportDMus</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>