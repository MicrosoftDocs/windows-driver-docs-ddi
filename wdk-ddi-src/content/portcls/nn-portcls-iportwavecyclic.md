---
UID: NN:portcls.IPortWaveCyclic
title: IPortWaveCyclic (portcls.h)
description: The IPortWaveCyclic interface is the WaveCyclic port driver's primary interface.
old-location: audio\iportwavecyclic.htm
tech.root: audio
ms.assetid: de241c4c-2012-4d57-b069-d169b1e0aec3
ms.date: 05/08/2018
keywords: ["IPortWaveCyclic interface"]
ms.keywords: IPortWaveCyclic, IPortWaveCyclic interface [Audio Devices], IPortWaveCyclic interface [Audio Devices],described, audio.iportwavecyclic, audmp-routines_079bd398-d9f2-4a35-9ee0-6ced8fecdeb4.xml, portcls/IPortWaveCyclic
f1_keywords:
 - "portcls/IPortWaveCyclic"
 - "IPortWaveCyclic"
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
- IPortWaveCyclic
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPortWaveCyclic interface


## -description


The <code>IPortWaveCyclic</code> interface is the WaveCyclic port driver's primary interface. The PortCls system driver implements this interface and exposes it to the adapter driver that implements the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportwavecyclic">IMiniportWaveCyclic</a> object. The <code>IPortWaveCyclic</code> interface provides a notification method that the miniport driver's interrupt service routine calls. Subordinate and bus-master DMA channels can also be instantiated on this interface. An adapter driver creates an <code>IPortWaveCyclic</code> object by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-pcnewport">PcNewPort</a> and specifying REFIID <b>IID_IPortWaveCyclic</b>. <code>IPortWaveCyclic</code> inherits from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iport">IPort</a> interface.

An adapter driver forms a miniport/port driver pair by binding an <b>IMiniportWaveCyclic</b> object to an <code>IPortWaveCyclic</code> object. The PortCls system driver registers this pair with the system as a <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/wave-filters">wave filter</a>.

