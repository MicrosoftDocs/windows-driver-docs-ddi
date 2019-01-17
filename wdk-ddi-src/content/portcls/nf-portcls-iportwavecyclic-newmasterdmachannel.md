---
UID: NF:portcls.IPortWaveCyclic.NewMasterDmaChannel
title: IPortWaveCyclic::NewMasterDmaChannel
description: The NewMasterDmaChannel method creates a new instance of a bus-master DMA channel.
old-location: audio\iportwavecyclic_newmasterdmachannel.htm
tech.root: audio
ms.assetid: bbd2b6e2-e332-49ae-aa18-490fd5631479
ms.date: 05/08/2018
ms.keywords: IPortWaveCyclic interface [Audio Devices],NewMasterDmaChannel method, IPortWaveCyclic.NewMasterDmaChannel, IPortWaveCyclic::NewMasterDmaChannel, NewMasterDmaChannel, NewMasterDmaChannel method [Audio Devices], NewMasterDmaChannel method [Audio Devices],IPortWaveCyclic interface, audio.iportwavecyclic_newmasterdmachannel, audmp-routines_831f81bd-545d-47e5-ae1a-8ecaa631497c.xml, portcls/IPortWaveCyclic::NewMasterDmaChannel
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IPortWaveCyclic.NewMasterDmaChannel
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPortWaveCyclic::NewMasterDmaChannel


## -description


The <code>NewMasterDmaChannel</code> method creates a new instance of a bus-master DMA channel.


## -parameters




### -param DmaChannel [out]

Pointer to a caller-allocated pointer variable into which the method writes a pointer to the new <a href="https://msdn.microsoft.com/library/windows/hardware/ff536547">IDmaChannel</a> object. Specify a valid, non-<b>NULL</b> pointer value for this parameter.


### -param OuterUnknown [in]

Pointer to the <b>IUnknown</b> interface of an object that needs to aggregate the DMA-channel object. This parameter is optional. If aggregation is not required, specify this parameter as <b>NULL</b>.


### -param ResourceList [in, optional]

Pointer to the miniport driver's resource list, which is an <a href="https://msdn.microsoft.com/library/windows/hardware/ff536976">IResourceList</a> object. This parameter is optional and can be specified as <b>NULL</b>. The <code>NewMasterDmaChannel</code> method currently makes no use of this parameter.


### -param MaximumLength [in]

Maximum length in bytes of the cyclic DMA buffer that will be associated with this channel.


### -param Dma32BitAddresses [in]

Specifies the use of 32-bit addresses.


### -param Dma64BitAddresses [in]

Specifies the use of 64-bit addresses.


### -param DmaWidth [in]

Not used. Set to (DMA_WIDTH)(-1).


### -param DmaSpeed [in]

Not used. Set to (DMA_SPEED)(-1).


## -returns



<code>NewMasterDmaChannel</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.




## -remarks



Parameters <i>MaximumLength</i>, <i>Dma32BitAddresses</i>, <i>Dma64BitAddresses</i>, <i>DmaWidth</i>, and <i>DmaSpeed</i> are similar in meaning to the members of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543107">DEVICE_DESCRIPTION</a> structure with the same names.

A WaveCyclic device with built-in bus-mastering DMA hardware is referred to as a <i>master device</i>. In contrast, a <i>subordinate device</i> lacks DMA hardware and has to rely on the system DMA controller to perform any data transfers that it requires. The <code>NewMasterDmaChannel</code> method creates a DMA-channel object for a master device. To create a DMA-channel object for a subordinate device, call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536902">IPortWaveCyclic::NewSlaveDmaChannel</a> method instead. For more information about master and subordinate devices, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff536547">IDmaChannel</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff536548">IDmaChannelSlave</a>.

The <i>DmaChannel</i>, <i>OuterUnknown</i>, and <i>ResourceList</i> parameters follow the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543107">DEVICE_DESCRIPTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536547">IDmaChannel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536548">IDmaChannelSlave</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536899">IPortWaveCyclic</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536902">IPortWaveCyclic::NewSlaveDmaChannel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536976">IResourceList</a>
 

 

