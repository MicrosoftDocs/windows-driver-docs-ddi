---
UID: NN:portcls.IDmaChannel
title: IDmaChannel
author: windows-driver-content
description: The IDmaChannel interface provides an abstraction of a DMA channel and its associated DMA buffer and usage parameters.
old-location: audio\idmachannel.htm
old-project: audio
ms.assetid: 85fad1fb-d088-46ad-917c-bdbc31134690
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: audio.idmachannel, IDmaChannel interface [Audio Devices], IDmaChannel interface [Audio Devices], described, IDmaChannel, portcls/IDmaChannel, audmp-routines_55e2df1d-771f-4427-a48e-671d4e113d5c.xml
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
-	IDmaChannel
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IDmaChannel interface


## -description


The <code>IDmaChannel</code> interface provides an abstraction of a DMA channel and its associated DMA buffer and usage parameters. A WaveCyclic or WavePci port driver implements this interface and exposes it to the WaveCyclic or WavePci miniport driver. The miniport driver obtains a reference to the port driver's implementation of an <code>IDmaChannel</code> object by calling one of the port driver's New<i>Xxx</i>DmaChannel methods:
<dl>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536916">IPortWavePci::NewMasterDmaChannel</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536900">IPortWaveCyclic::NewMasterDmaChannel</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536902">IPortWaveCyclic::NewSlaveDmaChannel</a>


</dd>
</dl>A miniport driver can also implement its own <code>IDmaChannel</code> interface if it requires capabilities that are not in the port driver's default implementation. For more information about this, see <a href="https://msdn.microsoft.com/9e364c8f-55c3-4ec9-a9ce-9ee0f6a0746b">Wave Filters</a>. When the port driver calls the miniport driver's <b>NewStream</b> method (for example, <a href="https://msdn.microsoft.com/library/windows/hardware/ff536723">IMiniportWaveCyclic::NewStream</a>), the method outputs the miniport driver's <code>IDmaChannel</code> object to the port driver. <code>IDmaChannel</code> inherits from the <b>IUnknown</b> interface.

The current implementation of the <code>IDmaChannel</code> interface in Portcls.sys is not multithread-safe because it does not internally synchronize access to shared data. Typically, a single driver thread calls the methods of an <code>IDmaChannel</code> object. In this case, there is no risk of two method calls simultaneously accessing the same data. However, if multiple threads can potentially call the methods of an <code>IDmaChannel</code> object at the same time, the driver writer must synchronize the method calls to prevent internal data corruption.

For more information, see <a href="https://msdn.microsoft.com/2064bbdf-62b7-454f-8764-b2aa21636c02">DMA Channel Objects</a>.

