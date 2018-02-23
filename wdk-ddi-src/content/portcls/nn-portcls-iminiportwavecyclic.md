---
UID: NN:portcls.IMiniportWaveCyclic
title: IMiniportWaveCyclic
author: windows-driver-content
description: The IMiniportWaveCyclic interface is the primary interface that is exposed by the miniport driver for a WaveCyclic audio device.
old-location: audio\iminiportwavecyclic.htm
old-project: audio
ms.assetid: 12f19ef8-ce7c-4a04-814a-a8c34beca1b9
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: audio.iminiportwavecyclic, IMiniportWaveCyclic interface [Audio Devices], IMiniportWaveCyclic interface [Audio Devices], described, IMiniportWaveCyclic, portcls/IMiniportWaveCyclic, audmp-routines_e9dda3e8-2545-4734-bf66-e08ff0c4a1e0.xml
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
-	IMiniportWaveCyclic
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportWaveCyclic interface


## -description


The <code>IMiniportWaveCyclic</code> interface is the primary interface that is exposed by the miniport driver for a WaveCyclic audio device. The WaveCyclic port driver communicates with the miniport driver through this interface. The adapter driver creates the WaveCyclic miniport object and passes the object's <code>IMiniportWaveCyclic</code> interface pointer to the WaveCyclic port driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536943">IPort::Init</a> method (see the code example in <a href="https://msdn.microsoft.com/e4ba1209-adc6-48c3-9633-247e9e3849bc">Subdevice Creation</a>). <code>IMiniportWaveCyclic</code> inherits from the <a href="..\portcls\nn-portcls-iminiport.md">IMiniport</a> interface.

An adapter driver forms a miniport/port driver pair by binding an <code>IMiniportWaveCyclic</code> object to an <a href="..\portcls\nn-portcls-iportwavecyclic.md">IPortWaveCyclic</a> object. The PortCls system driver registers this pair with the system as a <a href="https://msdn.microsoft.com/9e364c8f-55c3-4ec9-a9ce-9ee0f6a0746b">wave filter</a>.

The <code>IMiniportWaveCyclic</code> interface provides a method for initializing the miniport object and a method for creating a miniport stream object. The stream object is associated with a pin on the WaveCyclic filter, which the adapter driver forms by binding the miniport object and the port object together.

