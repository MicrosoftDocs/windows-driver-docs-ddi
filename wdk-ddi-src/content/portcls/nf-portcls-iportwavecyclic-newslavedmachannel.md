---
UID: NF:portcls.IPortWaveCyclic.NewSlaveDmaChannel
title: IPortWaveCyclic::NewSlaveDmaChannel method
author: windows-driver-content
description: The NewSlaveDmaChannel method creates a new instance of a subordinate DMA channel.
old-location: audio\iportwavecyclic_newslavedmachannel.htm
old-project: audio
ms.assetid: 4d20bd03-9fde-4fcf-a90b-5933221cda93
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, ., :, C, D, I, IPortWaveCyclic, IPortWaveCyclic interface [Audio Devices], NewSlaveDmaChannel method, IPortWaveCyclic::NewSlaveDmaChannel, N, NewSlaveDmaChannel method [Audio Devices], NewSlaveDmaChannel method [Audio Devices], IPortWaveCyclic interface, NewSlaveDmaChannel,IPortWaveCyclic.NewSlaveDmaChannel, P, S, W, a, audio.iportwavecyclic_newslavedmachannel, audmp-routines_63146fe2-162d-4457-9dda-807f1d3931ac.xml, c, e, h, i, l, m, n, o, portcls/IPortWaveCyclic::NewSlaveDmaChannel, r, t, v, w, y"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	portcls.h
apiname:
-	IPortWaveCyclic.NewSlaveDmaChannel
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IPortWaveCyclic::NewSlaveDmaChannel method


## -description


The <code>NewSlaveDmaChannel</code> method creates a new instance of a subordinate DMA channel.


## -syntax


````
NTSTATUS NewSlaveDmaChannel(
  [out] PDMACHANNELSLAVE *DmaChannel,
  [in]  PUNKNOWN         OuterUnknown,
  [in]  PRESOURCELIST    ResourceList,
  [in]  ULONG            DmaIndex,
  [in]  ULONG            MaximumLength,
  [in]  BOOLEAN          DemandMode,
  [in]  DMA_SPEED        DmaSpeed
);
````


## -parameters




### -param DmaChannel [out]

Pointer to a caller-allocated pointer variable into which the method writes a pointer to the new DMA-channel object's <a href="..\portcls\nn-portcls-idmachannelslave.md">IDmaChannelSlave</a> interface. Specify a valid, non-<b>NULL</b> pointer value for this parameter.


### -param OuterUnknown [in]

Pointer to the <b>IUnknown</b> interface of an object that needs to aggregate the DMA-channel object. This parameter is optional. If aggregation is not required, specify this parameter as <b>NULL</b>.


### -param ResourceList [in]

Pointer to an <a href="..\portcls\nn-portcls-iresourcelist.md">IResourceList</a> object. This resource list contains the resource that describes the DMA channel.


### -param DmaIndex [in]

Index in the resource list of the DMA-channel descriptor. The function uses this value as a call parameter to the <i>ResourceList</i> object's IResourceList::Find<i>xxx</i>Entry method.


### -param MaximumLength [in]

Maximum length in bytes of the cyclic DMA buffer that will be associated with this channel.


### -param DemandMode [in]

Indicates whether the device associated with the DMA channel supports demand mode.


### -param DmaSpeed [in]

The DMA speed can be specified as one of the following DMA_SPEED enumeration values: <b>Compatible</b>, <b>TypeA</b>, <b>TypeB</b>, <b>TypeC</b>, or <b>TypeF</b>.


## -returns



<code>NewSlaveDmaChannel</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.




## -remarks



Parameters <i>MaximumLength</i>, <i>DemandMode</i>, and <i>DmaSpeed</i> are similar in meaning to the members of the <a href="..\wdm\ns-wdm-_device_description.md">DEVICE_DESCRIPTION</a> structure with the same names.

A WaveCyclic device that lacks DMA-hardware capabilities is referred to as a <i>subordinate device</i>. In contrast, a <i>master device</i> has built-in bus-mastering DMA hardware. A subordinate device has to rely on the system DMA controller to perform any data transfers that it requires. The <code>NewSlaveDmaChannel</code> method creates a DMA-channel object for a subordinate device. To create a DMA-channel object for a master device, call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536900">IPortWaveCyclic::NewMasterDmaChannel</a> method instead. The sb16 sample audio driver in the Microsoft Windows Driver Kit (WDK) is an example of a WaveCyclic miniport driver for a subordinate device. For more information about master and subordinate devices, see <a href="..\portcls\nn-portcls-idmachannel.md">IDmaChannel</a> and <a href="..\portcls\nn-portcls-idmachannelslave.md">IDmaChannelSlave</a>.

The <i>DmaChannel</i>, <i>OuterUnknown</i>, and <i>ResourceList</i> parameters follow the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>.




## -see-also

<a href="..\portcls\nn-portcls-idmachannelslave.md">IDmaChannelSlave</a>



<a href="..\portcls\nn-portcls-idmachannel.md">IDmaChannel</a>



<a href="..\portcls\nn-portcls-iresourcelist.md">IResourceList</a>



<a href="..\wdm\ns-wdm-_device_description.md">DEVICE_DESCRIPTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536900">IPortWaveCyclic::NewMasterDmaChannel</a>



<a href="..\portcls\nn-portcls-iportwavecyclic.md">IPortWaveCyclic</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPortWaveCyclic::NewSlaveDmaChannel method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

