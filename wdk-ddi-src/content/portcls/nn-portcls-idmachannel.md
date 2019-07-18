---
UID: NN:portcls.IDmaChannel
title: IDmaChannel (portcls.h)
description: The IDmaChannel interface provides an abstraction of a DMA channel and its associated DMA buffer and usage parameters.
old-location: audio\idmachannel.htm
tech.root: audio
ms.assetid: 85fad1fb-d088-46ad-917c-bdbc31134690
ms.date: 03/19/2018
ms.keywords: IDmaChannel, IDmaChannel interface [Audio Devices], IDmaChannel interface [Audio Devices], described, audio.idmachannel, audmp-routines_55e2df1d-771f-4427-a48e-671d4e113d5c.xml, portcls/IDmaChannel
ms.topic: interface
f1_keywords:
 - "portcls/IDmaChannel"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- portcls.h
api_name:
- IDmaChannel
product:
- Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IDmaChannel interface


## -description


The <code>IDmaChannel</code> interface provides an abstraction of a DMA channel and its associated DMA buffer and usage parameters. A WaveCyclic or WavePci port driver implements this interface and exposes it to the WaveCyclic or WavePci miniport driver. The miniport driver obtains a reference to the port driver's implementation of an <code>IDmaChannel</code> object by calling one of the port driver's New<i>Xxx</i>DmaChannel methods:
<dl>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-iportwavepci-newmasterdmachannel">IPortWavePci::NewMasterDmaChannel</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-iportwavecyclic-newmasterdmachannel">IPortWaveCyclic::NewMasterDmaChannel</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-iportwavecyclic-newslavedmachannel">IPortWaveCyclic::NewSlaveDmaChannel</a>


</dd>
</dl>A miniport driver can also implement its own <code>IDmaChannel</code> interface if it requires capabilities that are not in the port driver's default implementation. For more information about this, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/wave-filters">Wave Filters</a>. When the port driver calls the miniport driver's <b>NewStream</b> method (for example, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-iminiportwavecyclic-newstream">IMiniportWaveCyclic::NewStream</a>), the method outputs the miniport driver's <code>IDmaChannel</code> object to the port driver. <code>IDmaChannel</code> inherits from the <b>IUnknown</b> interface.

The current implementation of the <code>IDmaChannel</code> interface in Portcls.sys is not multithread-safe because it does not internally synchronize access to shared data. Typically, a single driver thread calls the methods of an <code>IDmaChannel</code> object. In this case, there is no risk of two method calls simultaneously accessing the same data. However, if multiple threads can potentially call the methods of an <code>IDmaChannel</code> object at the same time, the driver writer must synchronize the method calls to prevent internal data corruption.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/dma-channel-objects">DMA Channel Objects</a>.

