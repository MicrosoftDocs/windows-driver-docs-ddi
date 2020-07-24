---
UID: NF:portcls.IMiniportWavePci.NewStream
title: IMiniportWavePci::NewStream (portcls.h)
description: The NewStream method creates a new instance of a logical stream associated with a specified physical channel.
old-location: audio\iminiportwavepci_newstream.htm
tech.root: audio
ms.assetid: cad3eeb5-2106-4648-97e5-cf3bb8601599
ms.date: 05/08/2018
keywords: ["IMiniportWavePci::NewStream"]
ms.keywords: IMiniportWavePci interface [Audio Devices],NewStream method, IMiniportWavePci.NewStream, IMiniportWavePci::NewStream, NewStream, NewStream method [Audio Devices], NewStream method [Audio Devices],IMiniportWavePci interface, audio.iminiportwavepci_newstream, audmp-routines_cf0b0f93-033d-47f1-8e07-c0407e0a89f3.xml, portcls/IMiniportWavePci::NewStream
f1_keywords:
 - "portcls/IMiniportWavePci.NewStream"
 - "IMiniportWavePci.NewStream"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- portcls.h
api_name:
- IMiniportWavePci.NewStream
targetos: Windows
req.typenames: 
---

# IMiniportWavePci::NewStream


## -description


The <code>NewStream</code> method creates a new instance of a logical stream associated with a specified physical channel.


## -parameters




### -param Stream [out]

Output pointer for the new stream. This parameter points to a caller-allocated pointer variable into which the method writes a pointer to the stream object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportwavepcistream">IMiniportWavePciStream</a> interface. The caller specifies a valid, non-<b>NULL</b> pointer for this parameter.


### -param OuterUnknown [in, optional]

Pointer to the <b>IUnknown</b> interface of an object that needs to aggregate the stream object. This parameter is optional. If aggregation is not required, the caller specifies this parameter as <b>NULL</b>.


### -param PoolType [in]

Specifies the type of memory pool from which the storage for the DMA-channel object should be allocated. This parameter will be one of the nonpaged pool types defined in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_pool_type">POOL_TYPE</a> enumeration.


### -param PortStream [in]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iportwavepcistream">IPortWavePciStream</a> interface of the port driver's stream object.


### -param Pin [in]

Specifies a pin ID identifying the pin that is to be opened. If the WavePci miniport driver's filter descriptor specifies a total of <i>n</i> pin factories on the filter, then valid values for parameter <i>Pin</i> are in the range 0 to <i>n</i>-1.


### -param Capture [in]

Specifies whether to create a capture stream or a render stream. This parameter is <b>TRUE</b> for an capture (input) channel, and <b>FALSE</b> for an playback (output) channel.


### -param DataFormat [in]

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksdataformat">KSDATAFORMAT</a> structure that specifies the stream's data format.


### -param DmaChannel [out]

Output pointer for the DMA channel. This parameter points to a caller-allocated pointer variable into which the method writes a pointer to the stream's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-idmachannel">IDmaChannel</a> object. The caller specifies a valid, non-<b>NULL</b> pointer for this parameter.


### -param ServiceGroup [out]

Output pointer for the service group. This parameter points to a caller-allocated pointer variable into which the method writes a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iservicegroup">IServiceGroup</a> interface of the stream's service group object. This is the service group that is being registered for interrupt notification. The caller specifies a valid, non-<b>NULL</b> pointer for this parameter.


## -returns



<code>NewStream</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.




## -remarks



The <code>NewStream</code> method sets the initial state of the stream to KSSTATE_STOP and its initial position to zero. (See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportwavepcistream-setstate">IMiniportWavePciStream::SetState</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportwavepcistream-getposition">IMiniportWavePciStream::GetPosition</a>.)

The <i>DataFormat</i> parameter, which specifies the data format of the stream, points to one of the following audio-specific, extended versions of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksdataformat">KSDATAFORMAT</a> structure:


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksdataformat_waveformatex">KSDATAFORMAT_WAVEFORMATEX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksdataformat_dsound">KSDATAFORMAT_DSOUND</a>


If the miniport driver does not provide a service group pointer (that is, if the <code>NewStream</code> call outputs <b>NULL</b> through the <i>ServiceGroup</i> pointer), the port driver sets up its own periodic timer instead for processing stream position and clock events. The period for this timer is currently 20 milliseconds, but the period might change in future implementations.

The <i>Stream</i>, <i>OuterUnknown</i>, <i>PortStream</i>, and <i>ServiceGroup</i> parameters follow the <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/reference-counting-conventions-for-com-objects">reference-counting conventions for COM objects</a>.

Note that <code>NewStream</code> does not follow the usual reference-counting conventions in its handling of the pointer that it outputs through the <i>DmaChannel</i> OUT parameter. When the port driver finishes using the references that it receives through the <code>NewStream</code> method's other OUT parameters, <i>Stream</i> and <i>ServiceGroup</i>, it releases them, as expected. In contrast, the port driver never uses the <i>DmaChannel</i> pointer that it receives from the <code>NewStream</code> call and it never calls <b>Release</b> on the <i>DmaChannel</i> object.

The ac97 sample audio driver in the Microsoft Windows Driver Kit (WDK) reflects this behavior. This sample's implementation of the <code>IMiniportWavePci::NewStream</code> method calls <b>AddRef</b> on the <i>Stream</i> and <i>ServiceGroup</i> references that it outputs but not the <i>DmaChannel</i> reference. This behavior is preserved for the sake of backward compatibility.

Note that the <code>NewStream</code> methods for the other port types (WaveCyclic, in particular) follow the usual reference-counting conventions for all their OUT parameters. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-idmachannel">IDmaChannel</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportwavepci">IMiniportWavePci</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportwavepcistream">IMiniportWavePciStream</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iportwavepcistream">IPortWavePciStream</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iservicegroup">IServiceGroup</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksdataformat">KSDATAFORMAT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksdataformat_dsound">KSDATAFORMAT_DSOUND</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksdataformat_waveformatex">KSDATAFORMAT_WAVEFORMATEX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_pool_type">POOL_TYPE</a>
 

 

