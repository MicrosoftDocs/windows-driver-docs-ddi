---
UID: NF:portcls.IMiniportWaveCyclic.NewStream
title: IMiniportWaveCyclic::NewStream
author: windows-driver-content
description: The NewStream method creates a new instance of a logical stream that is associated with a specified physical channel.
old-location: audio\iminiportwavecyclic_newstream.htm
tech.root: audio
ms.assetid: a83c6eb9-a29a-4695-99d3-168dff68c4a2
ms.author: windowsdriverdev
ms.date: 5/8/2018
ms.keywords: IMiniportWaveCyclic interface [Audio Devices],NewStream method, IMiniportWaveCyclic.NewStream, IMiniportWaveCyclic::NewStream, NewStream, NewStream method [Audio Devices], NewStream method [Audio Devices],IMiniportWaveCyclic interface, audio.iminiportwavecyclic_newstream, audmp-routines_eb476e18-bd94-4665-a3df-3e95f91e1c5b.xml, portcls/IMiniportWaveCyclic::NewStream
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
-	IMiniportWaveCyclic.NewStream
product:
- Windows
targetos: Windows
req.typenames: 
---

# IMiniportWaveCyclic::NewStream


## -description


The <code>NewStream</code> method creates a new instance of a logical stream that is associated with a specified physical channel.


## -parameters




### -param Stream [out]

Output pointer for the new stream. This parameter points to a caller-allocated pointer variable into which the method writes a pointer to the stream object's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536715">IMiniportWaveCyclicStream</a> interface. The caller specifies a valid, non-<b>NULL</b> pointer value for this parameter.


### -param OuterUnknown [in, optional]

Pointer to the <b>IUnknown</b> interface of an object that needs to aggregate the stream object. This parameter is optional. If aggregation is not required, the caller specifies this parameter as <b>NULL</b>.


### -param PoolType [in]

Specifies the type of memory pool from which the storage for the DMA-channel object should be allocated. This parameter will be one of the nonpaged pool types defined in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559707">POOL_TYPE</a> enumeration.


### -param Pin [in]

Number of the pin that is to be opened. If the WaveCyclic miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536765">IMiniport::GetDescription</a> method outputs a filter descriptor that specifies a total of <i>n</i> pin factories on the filter, then valid values for parameter <i>Pin</i> are in the range 0 to <i>n</i>-1.


### -param Capture [in]

Specifies whether to create a capture stream or a render stream. This parameter is <b>TRUE</b> for a capture (input) channel, and <b>FALSE</b> for a playback (output) channel.


### -param DataFormat [in]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561656">KSDATAFORMAT</a> structure indicating the format to use for this instance.


### -param DmaChannel [out]

Output pointer to the DMA channel. This parameter points to a caller-allocated pointer variable into which the method writes a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536547">IDmaChannel</a> interface of the miniport driver's DMA-channel object. The caller specifies a valid, non-<b>NULL</b> pointer value for this parameter. For more information, see the following Remarks section.


### -param ServiceGroup [out]

Output pointer for the service group. This parameter points to a caller-allocated pointer variable into which the method writes a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536994">IServiceGroup</a> interface of the stream's service group object. This is the service group that is being registered for interrupt notification. The caller specifies a valid, non-<b>NULL</b> pointer value for this parameter.


## -returns



<code>NewStream</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.




## -remarks



The <code>NewStream</code> method sets the initial state of the stream to KSSTATE_STOP and its initial position to zero. (See <a href="https://msdn.microsoft.com/library/windows/hardware/ff536720">IMiniportWaveCyclicStream::SetState</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff536716">IMiniportWaveCyclicStream::GetPosition</a>.)

The port driver calls only the following methods on the <i>DmaChannel</i> object:


<a href="https://msdn.microsoft.com/library/windows/hardware/ff536554">IDmaChannel::AllocatedBufferSize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536556">IDmaChannel::BufferSize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536557">IDmaChannel::CopyFrom</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536558">IDmaChannel::CopyTo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536563">IDmaChannel::SetBufferSize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536564">IDmaChannel::SystemAddress</a>


The <i>Stream</i>, <i>OuterUnknown</i>, <i>DmaChannel</i>, and <i>ServiceGroup</i> parameters follow the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536547">IDmaChannel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536765">IMiniport::GetDescription</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536714">IMiniportWaveCyclic</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536715">IMiniportWaveCyclicStream</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536994">IServiceGroup</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561656">KSDATAFORMAT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559707">POOL_TYPE</a>
 

 

