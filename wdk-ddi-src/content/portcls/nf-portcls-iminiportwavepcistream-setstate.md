---
UID: NF:portcls.IMiniportWavePciStream.SetState
title: IMiniportWavePciStream::SetState (portcls.h)
description: The SetState method changes the state of the stream transport.
old-location: audio\iminiportwavepcistream_setstate.htm
tech.root: audio
ms.assetid: ae029e17-7229-49a6-bf5f-96e0cb143d5b
ms.date: 05/08/2018
keywords: ["IMiniportWavePciStream::SetState"]
ms.keywords: IMiniportWavePciStream interface [Audio Devices],SetState method, IMiniportWavePciStream.SetState, IMiniportWavePciStream::SetState, SetState, SetState method [Audio Devices], SetState method [Audio Devices],IMiniportWavePciStream interface, audio.iminiportwavepcistream_setstate, audmp-routines_71487eb9-23d5-4428-92c0-fc75e58d0da5.xml, portcls/IMiniportWavePciStream::SetState
f1_keywords:
 - "portcls/IMiniportWavePciStream.SetState"
 - "IMiniportWavePciStream.SetState"
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
- IMiniportWavePciStream.SetState
targetos: Windows
req.typenames: 
---

# IMiniportWavePciStream::SetState


## -description


The <code>SetState</code> method changes the state of the stream transport.


## -parameters




### -param State [in]

Specifies the new state of the stream. This parameter is a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ne-ks-ksstate">KSSTATE</a> enumeration value. For more information, see the following Remarks section.


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
For most miniports, KSSTATE_ACQUIRE and KSSTATE_PAUSE are indistinguishable.

Transitions always occur in one of the following two sequences:

<ul>
<li>
STOP -> ACQUIRE -> PAUSE -> RUN

</li>
<li>
RUN -> PAUSE -> ACQUIRE -> STOP

</li>
</ul>
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportwavepci-newstream">IMiniportWavePci::NewStream</a> method sets the initial state of the stream to KSSTATE_STOP. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportwavepci-newstream">IMiniportWavePci::NewStream</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportwavepcistream">IMiniportWavePciStream</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-connection-state">KSPROPERTY_CONNECTION_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ne-ks-ksstate">KSSTATE</a>
 

 

