---
UID: NF:portcls.IMiniportWaveCyclicStream.SetState
title: IMiniportWaveCyclicStream::SetState (portcls.h)
description: The SetState method sets the new state of playback or recording for the stream.
old-location: audio\iminiportwavecyclicstream_setstate.htm
tech.root: audio
ms.assetid: 61d7252e-04af-46f1-a885-4720698ae930
ms.date: 05/08/2018
keywords: ["IMiniportWaveCyclicStream::SetState"]
ms.keywords: IMiniportWaveCyclicStream interface [Audio Devices],SetState method, IMiniportWaveCyclicStream.SetState, IMiniportWaveCyclicStream::SetState, SetState, SetState method [Audio Devices], SetState method [Audio Devices],IMiniportWaveCyclicStream interface, audio.iminiportwavecyclicstream_setstate, audmp-routines_46474aab-87da-4121-9cb8-ee8b280c7852.xml, portcls/IMiniportWaveCyclicStream::SetState
f1_keywords:
 - "portcls/IMiniportWaveCyclicStream.SetState"
 - "IMiniportWaveCyclicStream.SetState"
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
- IMiniportWaveCyclicStream.SetState
targetos: Windows
req.typenames: 
---

# IMiniportWaveCyclicStream::SetState


## -description


The <code>SetState</code> method sets the new state of playback or recording for the stream.


## -parameters




### -param State [in]

Specifies the new state for the stream. This parameter is a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ne-ks-ksstate">KSSTATE</a> enumeration value. For more information, see the following Remarks section.


## -returns



<code>SetState</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.




## -remarks



For an audio filter graph, the four <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ne-ks-ksstate">KSSTATE</a> enumeration values are interpreted as follows:

<ul>
<li>
KSSTATE_RUN 

Data transport in the current audio filter graph is running and functioning as normal.

</li>
<li>
KSSTATE_ACQUIRE 

This is a transitional state that helps to manage the transition between KSSTATE_RUN and KSSTATE_STOP.

</li>
<li>
KSSTATE_PAUSE 

This is a transitional state that helps to manage the transition between KSSTATE_RUN and KSSTATE_STOP. 

</li>
<li>
KSSTATE_STOP 

Data transport is stopped in the current audio filter graph.

</li>
</ul>
For most miniport drivers, KSSTATE_ACQUIRE and KSSTATE_PAUSE are indistinguishable.

Transitions always occur in one of the following two sequences:

<ul>
<li>
STOP -> ACQUIRE -> PAUSE -> RUN

</li>
<li>
RUN -> PAUSE -> ACQUIRE -> STOP

</li>
</ul>
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportwavecyclic-newstream">IMiniportWaveCyclic::NewStream</a> method sets the initial state of the stream to KSSTATE_STOP. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportwavecyclic-newstream">IMiniportWaveCyclic::NewStream</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportwavecyclicstream">IMiniportWaveCyclicStream</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-connection-state">KSPROPERTY_CONNECTION_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ne-ks-ksstate">KSSTATE</a>
 

 

