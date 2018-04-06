---
UID: NN:portcls.IPortMidi
title: IPortMidi
author: windows-driver-content
description: The IPortMidi interface is the MIDI port driver's primary interface.
old-location: audio\iportmidi.htm
old-project: audio
ms.assetid: e5403377-fd24-4fd5-8158-194f30238c44
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: IPortMidi, IPortMidi interface [Audio Devices], IPortMidi interface [Audio Devices], described, audio.iportmidi, audmp-routines_52a1c6a3-7658-4c69-a4c9-6d965a1d99c9.xml, portcls/IPortMidi
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
-	IPortMidi
product:
- Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IPortMidi interface


## -description


The <code>IPortMidi</code> interface is the MIDI port driver's primary interface. The PortCls system driver implements this interface and exposes it to the adapter driver that implements the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536703">IMiniportMidi</a> object. An adapter driver creates an <code>IPortMidi</code> object by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff537715">PcNewPort</a> and specifying REFIID <b>IID_IPortMidi</b>. <code>IPortMidi</code> inherits from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536842">IPort</a> interface.

An adapter driver forms a miniport/port driver pair by binding an <b>IMiniportMidi</b> object to an <code>IPortMidi</code> object. The PortCls system driver registers this pair with the system as a MIDI filter (see <a href="https://msdn.microsoft.com/622aa4ae-c855-4088-bc1a-30dff7a24d23">MIDI and DirectMusic Filters</a>).

