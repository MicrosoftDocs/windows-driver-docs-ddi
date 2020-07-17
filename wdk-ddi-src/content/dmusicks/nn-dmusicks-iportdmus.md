---
UID: NN:dmusicks.IPortDMus
title: IPortDMus (dmusicks.h)
description: The IPortDMus interface is the DMus port driver's primary interface.
old-location: audio\iportdmus.htm
tech.root: audio
ms.assetid: 96388400-56f9-4a43-bc37-cfe6cfb233cb
ms.date: 05/08/2018
keywords: ["IPortDMus interface"]
ms.keywords: IPortDMus, IPortDMus interface [Audio Devices], IPortDMus interface [Audio Devices],described, audio.iportdmus, audmp-routines_20e57cde-9732-4592-8bb6-b5775609b833.xml, dmusicks/IPortDMus
f1_keywords:
 - "dmusicks/IPortDMus"
 - "IPortDMus"
req.header: dmusicks.h
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
- dmusicks.h
api_name:
- IPortDMus
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPortDMus interface


## -description


The <code>IPortDMus</code> interface is the DMus port driver's primary interface. The PortCls system driver implements this interface and exposes it to the adapter driver that implements the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dmusicks/nn-dmusicks-iminiportdmus">IMiniportDMus</a> object. An adapter driver creates an <b>IPortWaveDMus</b> object by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-pcnewport">PcNewPort</a> with REFIID <b>IID_IPortWaveDMus</b> (see the code example in <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/subdevice-creation">Subdevice Creation</a>). <code>IPortDMus</code> inherits from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iportmidi">IPortMidi</a> interface.

An adapter driver forms a miniport/port driver pair by binding an <b>IMiniportDMus</b> object to an <code>IPortDMus</code> object. The PortCls system driver registers this pair with the system as a DirectMusic filter (see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/midi-and-directmusic-filters">MIDI and DirectMusic Filters</a>).

