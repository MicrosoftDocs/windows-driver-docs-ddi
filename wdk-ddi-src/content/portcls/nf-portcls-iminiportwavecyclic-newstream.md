---
UID: NF:portcls.IMiniportWaveCyclic.NewStream
title: IMiniportWaveCyclic::NewStream method
author: windows-driver-content
description: The NewStream method creates a new instance of a logical stream that is associated with a specified physical channel.
old-location: audio\iminiportwavecyclic_newstream.htm
old-project: audio
ms.assetid: a83c6eb9-a29a-4695-99d3-168dff68c4a2
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: NewStream method [Audio Devices], IMiniportWaveCyclic::NewStream, IMiniportWaveCyclic, portcls/IMiniportWaveCyclic::NewStream, NewStream method [Audio Devices], IMiniportWaveCyclic interface, NewStream, audio.iminiportwavecyclic_newstream, IMiniportWaveCyclic interface [Audio Devices], NewStream method, audmp-routines_eb476e18-bd94-4665-a3df-3e95f91e1c5b.xml
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
-	IMiniportWaveCyclic.NewStream
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportWaveCyclic::NewStream method


## -description


The <code>NewStream</code> method creates a new instance of a logical stream that is associated with a specified physical channel.


## -syntax


````
NTSTATUS NewStream(
  [out]          PMINIPORTWAVECYCLICSTREAM *Stream,
  [in, optional] PUNKNOWN                  OuterUnknown,
  [in]           POOL_TYPE                 PoolType,
  [in]           ULONG                     Pin,
  [in]           BOOLEAN                   Capture,
  [in]           PKSDATAFORMAT             DataFormat,
  [out]          PDMACHANNEL               *DmaChannel,
  [out]          PSERVICEGROUP             *ServiceGroup
);
````


## -parameters




### -param Stream [out]

Output pointer for the new stream. This parameter points to a caller-allocated pointer variable into which the method writes a pointer to the stream object's <a href="..\portcls\nn-portcls-iminiportwavecyclicstream.md">IMiniportWaveCyclicStream</a> interface. The caller specifies a valid, non-<b>NULL</b> pointer value for this parameter.


### -param OuterUnknown [in, optional]

Pointer to the <b>IUnknown</b> interface of an object that needs to aggregate the stream object. This parameter is optional. If aggregation is not required, the caller specifies this parameter as <b>NULL</b>.


### -param PoolType [in]

Specifies the type of memory pool from which the storage for the DMA-channel object should be allocated. This parameter will be one of the nonpaged pool types defined in the <a href="..\wdm\ne-wdm-_pool_type.md">POOL_TYPE</a> enumeration.


### -param Pin [in]

Number of the pin that is to be opened. If the WaveCyclic miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536765">IMiniport::GetDescription</a> method outputs a filter descriptor that specifies a total of <i>n</i> pin factories on the filter, then valid values for parameter <i>Pin</i> are in the range 0 to <i>n</i>-1.


### -param Capture [in]

Specifies whether to create a capture stream or a render stream. This parameter is <b>TRUE</b> for a capture (input) channel, and <b>FALSE</b> for a playback (output) channel.


### -param DataFormat [in]

Pointer to a <a href="..\ks\ns-ks-ksdataformat.md">KSDATAFORMAT</a> structure indicating the format to use for this instance.


### -param DmaChannel [out]

Output pointer to the DMA channel. This parameter points to a caller-allocated pointer variable into which the method writes a pointer to the <a href="..\portcls\nn-portcls-idmachannel.md">IDmaChannel</a> interface of the miniport driver's DMA-channel object. The caller specifies a valid, non-<b>NULL</b> pointer value for this parameter. For more information, see the following Remarks section.


### -param ServiceGroup [out]

Output pointer for the service group. This parameter points to a caller-allocated pointer variable into which the method writes a pointer to the <a href="..\portcls\nn-portcls-iservicegroup.md">IServiceGroup</a> interface of the stream's service group object. This is the service group that is being registered for interrupt notification. The caller specifies a valid, non-<b>NULL</b> pointer value for this parameter.


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

<a href="..\wdm\ne-wdm-_pool_type.md">POOL_TYPE</a>

<a href="..\ks\ns-ks-ksdataformat.md">KSDATAFORMAT</a>

<a href="..\portcls\nn-portcls-iminiportwavecyclic.md">IMiniportWaveCyclic</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536765">IMiniport::GetDescription</a>

<a href="..\portcls\nn-portcls-iminiportwavecyclicstream.md">IMiniportWaveCyclicStream</a>

<a href="..\portcls\nn-portcls-idmachannel.md">IDmaChannel</a>

<a href="..\portcls\nn-portcls-iservicegroup.md">IServiceGroup</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportWaveCyclic::NewStream method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

