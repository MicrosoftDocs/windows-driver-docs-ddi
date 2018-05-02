---
UID: NF:portcls.IMiniportWaveCyclicStream.SetState
title: IMiniportWaveCyclicStream::SetState
author: windows-driver-content
description: The SetState method sets the new state of playback or recording for the stream.
old-location: audio\iminiportwavecyclicstream_setstate.htm
old-project: audio
ms.assetid: 61d7252e-04af-46f1-a885-4720698ae930
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: IMiniportWaveCyclicStream interface [Audio Devices],SetState method, IMiniportWaveCyclicStream.SetState, IMiniportWaveCyclicStream::SetState, SetState, SetState method [Audio Devices], SetState method [Audio Devices],IMiniportWaveCyclicStream interface, audio.iminiportwavecyclicstream_setstate, audmp-routines_46474aab-87da-4121-9cb8-ee8b280c7852.xml, portcls/IMiniportWaveCyclicStream::SetState
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
-	IMiniportWaveCyclicStream.SetState
product:
- Windows
targetos: Windows
req.typenames: 
---

# IMiniportWaveCyclicStream::SetState


## -description


The <code>SetState</code> method sets the new state of playback or recording for the stream.


## -parameters




### -param State [in]

Specifies the new state for the stream. This parameter is a <a href="https://msdn.microsoft.com/library/windows/hardware/ff566856">KSSTATE</a> enumeration value. For more information, see the following Remarks section.


## -returns



<code>SetState</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.




## -remarks



For an audio filter graph, the four <a href="https://msdn.microsoft.com/library/windows/hardware/ff566856">KSSTATE</a> enumeration values are interpreted as follows:

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
STOP -&gt; ACQUIRE -&gt; PAUSE -&gt; RUN

</li>
<li>
RUN -&gt; PAUSE -&gt; ACQUIRE -&gt; STOP

</li>
</ul>
The <a href="https://msdn.microsoft.com/library/windows/hardware/ff536723">IMiniportWaveCyclic::NewStream</a> method sets the initial state of the stream to KSSTATE_STOP. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536723">IMiniportWaveCyclic::NewStream</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536715">IMiniportWaveCyclicStream</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565110">KSPROPERTY_CONNECTION_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566856">KSSTATE</a>
 

 

