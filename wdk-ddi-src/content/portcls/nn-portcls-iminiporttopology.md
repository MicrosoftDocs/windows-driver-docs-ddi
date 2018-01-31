---
UID: NN:portcls.IMiniportTopology
title: IMiniportTopology
author: windows-driver-content
description: The IMiniportTopology interface is the primary interface of a Topology miniport driver.
old-location: audio\iminiporttopology.htm
old-project: audio
ms.assetid: f66129df-07c4-4472-aa14-6c4d9578a92d
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: audio.iminiporttopology, IMiniportTopology interface [Audio Devices], IMiniportTopology interface [Audio Devices], described, IMiniportTopology, portcls/IMiniportTopology, audmp-routines_c2137cf2-ab04-4b0b-aeda-d50fe3225324.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	portcls.h
apiname:
-	IMiniportTopology
product: Windows
targetos: Windows
req.typenames: "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---

# IMiniportTopology interface


## -description


The <code>IMiniportTopology</code> interface is the primary interface of a Topology miniport driver. Through this interface, the miniport driver exposes the topology of the mixing circuitry in an audio adapter. In a typical adapter, this circuitry mixes together the playback streams from the wave renderer and MIDI synthesizer. The Topology port driver communicates with the miniport driver through the <code>IMiniportTopology</code> interface. The adapter driver creates the topology miniport object and passes the object's <code>IMiniportTopology</code> interface pointer to the topology port driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536943">IPort::Init</a> method (see the code example in <a href="https://msdn.microsoft.com/e4ba1209-adc6-48c3-9633-247e9e3849bc">Subdevice Creation</a>). <code>IMiniportTopology</code> inherits from the <a href="..\portcls\nn-portcls-iminiport.md">IMiniport</a> interface.

An adapter driver forms a miniport/port driver pair by binding an <code>IMiniportTopology</code> object to an <a href="..\portcls\nn-portcls-iporttopology.md">IPortTopology</a> object. The PortCls system driver registers this pair with the system as a <a href="https://msdn.microsoft.com/1b3d35e9-5858-407c-9cd0-06307d82ce58">topology filter</a>.

Through a sequence of property requests, the <b>mixer</b> API uses the topology filter to enumerate the pins, nodes, and connections that comprise the internal topology of the audio adapter. The filter also supports the acquisition of control-change information. The pins of a topology filter represent hardwired connections within the adapter and therefore cannot be instantiated. For more information, see <a href="https://msdn.microsoft.com/ee89dc67-c9f3-41cd-8a09-0c46d636fe64">Kernel Streaming Topology to Audio Mixer API Translation</a>.

