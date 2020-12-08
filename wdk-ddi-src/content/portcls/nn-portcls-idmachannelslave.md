---
UID: NN:portcls.IDmaChannelSlave
title: IDmaChannelSlave (portcls.h)
description: The IDmaChannelSlave interface provides methods for monitoring and controlling a DMA channel for a subordinate device (as described in Introduction to Adapter Objects).
old-location: audio\idmachannelslave.htm
tech.root: audio
ms.date: 03/19/2018
keywords: ["IDmaChannelSlave interface"]
ms.keywords: IDmaChannelSlave, IDmaChannelSlave interface [Audio Devices], IDmaChannelSlave interface [Audio Devices], described, audio.idmachannelslave, audmp-routines_309d3b3a-de27-478d-a82f-0677e3d61bd2.xml, portcls/IDmaChannelSlave
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
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
f1_keywords:
 - IDmaChannelSlave
 - portcls/IDmaChannelSlave
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IDmaChannelSlave
---

# IDmaChannelSlave interface

> [!NOTE]
> Microsoft supports a diverse and inclusive environment. This article contains references to terminology that the [Microsoft style guide for bias-free communication](/style-guide/bias-free-communication) recognizes as exclusionary. The word or phrase is used in this article for consistency because it currently appears in the software. When the software is updated to remove the language, this article will be updated to be in alignment.

## -description

The <code>IDmaChannelSlave</code> interface provides methods for monitoring and controlling a DMA channel for a subordinate device (as described in <a href="/windows-hardware/drivers/kernel/introduction-to-adapter-objects">Introduction to Adapter Objects</a>). A WaveCyclic port driver implements this interface and exposes it to the WaveCyclic miniport driver. The miniport driver obtains a reference to the port driver's implementation of an <code>IDmaChannelSlave</code> object by calling the port driver's <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iportwavecyclic-newslavedmachannel">IPortWaveCyclic::NewSlaveDmaChannel</a> method. A miniport driver also has the option of implementing its own <code>IDmaChannelSlave</code> interface if it requires capabilities that are not in the port driver's default implementation (for more information, see <a href="/windows-hardware/drivers/audio/wave-filters">Wave Filters</a>). When the port driver calls the miniport driver's <b>NewStream</b> method (for example, <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportwavecyclic-newstream">IMiniportWaveCyclic::NewStream</a>), the method outputs the miniport driver's <code>IDmaChannelSlave</code> object to the port driver. <code>IDmaChannelSlave</code> inherits from the <a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-idmachannel">IDmaChannel</a> interface.

For more information, see <a href="/windows-hardware/drivers/audio/dma-channel-objects">DMA Channel Objects</a>.

In addition to the methods that are inherited from <b>IUnknown</b> interface, <code>IDmaChannelSlave</code> also inherits from <a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-idmachannel">IDmaChannel</a>.
