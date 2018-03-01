---
UID: NF:portcls.IPortWaveCyclic.NewMasterDmaChannel
title: IPortWaveCyclic::NewMasterDmaChannel method
author: windows-driver-content
description: The NewMasterDmaChannel method creates a new instance of a bus-master DMA channel.
old-location: audio\iportwavecyclic_newmasterdmachannel.htm
old-project: audio
ms.assetid: bbd2b6e2-e332-49ae-aa18-490fd5631479
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IPortWaveCyclic, IPortWaveCyclic interface [Audio Devices], NewMasterDmaChannel method, IPortWaveCyclic::NewMasterDmaChannel, NewMasterDmaChannel method [Audio Devices], NewMasterDmaChannel method [Audio Devices], IPortWaveCyclic interface, NewMasterDmaChannel,IPortWaveCyclic.NewMasterDmaChannel, audio.iportwavecyclic_newmasterdmachannel, audmp-routines_831f81bd-545d-47e5-ae1a-8ecaa631497c.xml, portcls/IPortWaveCyclic::NewMasterDmaChannel
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: portcls.h
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
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IPortWaveCyclic::NewMasterDmaChannel method


## -description


The <code>NewMasterDmaChannel</code> method creates a new instance of a bus-master DMA channel.


## -syntax


````
NTSTATUS NewMasterDmaChannel(
  [out]          PDMACHANNEL   *DmaChannel,
  [in]           PUNKNOWN      OuterUnknown,
  [in, optional] PRESOURCELIST ResourceList,
  [in]           ULONG         MaximumLength,
  [in]           BOOLEAN       Dma32BitAddresses,
  [in]           BOOLEAN       Dma64BitAddresses,
  [in]           DMA_WIDTH     DmaWidth,
  [in]           DMA_SPEED     DmaSpeed
);
````


## -parameters




### -param DmaChannel [out]

Pointer to a caller-allocated pointer variable into which the method writes a pointer to the new <a href="..\portcls\nn-portcls-idmachannel.md">IDmaChannel</a> object. Specify a valid, non-<b>NULL</b> pointer value for this parameter.


### -param OuterUnknown [in]

Pointer to the <b>IUnknown</b> interface of an object that needs to aggregate the DMA-channel object. This parameter is optional. If aggregation is not required, specify this parameter as <b>NULL</b>.


### -param ResourceList [in, optional]

Pointer to the miniport driver's resource list, which is an <a href="..\portcls\nn-portcls-iresourcelist.md">IResourceList</a> object. This parameter is optional and can be specified as <b>NULL</b>. The <code>NewMasterDmaChannel</code> method currently makes no use of this parameter.


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



Parameters <i>MaximumLength</i>, <i>Dma32BitAddresses</i>, <i>Dma64BitAddresses</i>, <i>DmaWidth</i>, and <i>DmaSpeed</i> are similar in meaning to the members of the <a href="..\wdm\ns-wdm-_device_description.md">DEVICE_DESCRIPTION</a> structure with the same names.

A WaveCyclic device with built-in bus-mastering DMA hardware is referred to as a <i>master device</i>. In contrast, a <i>subordinate device</i> lacks DMA hardware and has to rely on the system DMA controller to perform any data transfers that it requires. The <code>NewMasterDmaChannel</code> method creates a DMA-channel object for a master device. To create a DMA-channel object for a subordinate device, call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536902">IPortWaveCyclic::NewSlaveDmaChannel</a> method instead. For more information about master and subordinate devices, see <a href="..\portcls\nn-portcls-idmachannel.md">IDmaChannel</a> and <a href="..\portcls\nn-portcls-idmachannelslave.md">IDmaChannelSlave</a>.

The <i>DmaChannel</i>, <i>OuterUnknown</i>, and <i>ResourceList</i> parameters follow the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>.




## -see-also

<a href="..\portcls\nn-portcls-idmachannel.md">IDmaChannel</a>



<a href="..\portcls\nn-portcls-iportwavecyclic.md">IPortWaveCyclic</a>



<a href="..\wdm\ns-wdm-_device_description.md">DEVICE_DESCRIPTION</a>



<a href="..\portcls\nn-portcls-idmachannelslave.md">IDmaChannelSlave</a>



<a href="..\portcls\nn-portcls-iresourcelist.md">IResourceList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536902">IPortWaveCyclic::NewSlaveDmaChannel</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPortWaveCyclic::NewMasterDmaChannel method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

