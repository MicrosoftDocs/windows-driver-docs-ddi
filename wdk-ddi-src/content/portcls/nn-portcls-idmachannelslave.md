---
UID: NN:portcls.IDmaChannelSlave
title: IDmaChannelSlave
author: windows-driver-content
description: The IDmaChannelSlave interface provides methods for monitoring and controlling a DMA channel for a subordinate device (as described in Introduction to Adapter Objects).
old-location: audio\idmachannelslave.htm
old-project: audio
ms.assetid: 1d628035-ffcf-4657-8310-f851b3f508f9
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: audio.idmachannelslave, IDmaChannelSlave interface [Audio Devices], IDmaChannelSlave interface [Audio Devices], described, IDmaChannelSlave, portcls/IDmaChannelSlave, audmp-routines_309d3b3a-de27-478d-a82f-0677e3d61bd2.xml
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
-	IDmaChannelSlave
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IDmaChannelSlave interface


## -description


The <code>IDmaChannelSlave</code> interface provides methods for monitoring and controlling a DMA channel for a subordinate device (as described in <a href="https://msdn.microsoft.com/library/windows/hardware/ff547986">Introduction to Adapter Objects</a>). A WaveCyclic port driver implements this interface and exposes it to the WaveCyclic miniport driver. The miniport driver obtains a reference to the port driver's implementation of an <code>IDmaChannelSlave</code> object by calling the port driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536902">IPortWaveCyclic::NewSlaveDmaChannel</a> method. A miniport driver also has the option of implementing its own <code>IDmaChannelSlave</code> interface if it requires capabilities that are not in the port driver's default implementation (for more information, see <a href="https://msdn.microsoft.com/9e364c8f-55c3-4ec9-a9ce-9ee0f6a0746b">Wave Filters</a>). When the port driver calls the miniport driver's <b>NewStream</b> method (for example, <a href="https://msdn.microsoft.com/library/windows/hardware/ff536723">IMiniportWaveCyclic::NewStream</a>), the method outputs the miniport driver's <code>IDmaChannelSlave</code> object to the port driver. <code>IDmaChannelSlave</code> inherits from the <a href="..\portcls\nn-portcls-idmachannel.md">IDmaChannel</a> interface.

For more information, see <a href="https://msdn.microsoft.com/2064bbdf-62b7-454f-8764-b2aa21636c02">DMA Channel Objects</a>.

In addition to the methods that are inherited from <b>IUnknown</b> interface, <code>IDmaChannelSlave</code> also inherits from <a href="..\portcls\nn-portcls-idmachannel.md">IDmaChannel</a>.

