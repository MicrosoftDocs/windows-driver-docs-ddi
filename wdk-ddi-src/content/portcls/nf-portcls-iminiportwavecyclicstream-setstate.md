---
UID: NF:portcls.IMiniportWaveCyclicStream.SetState
title: IMiniportWaveCyclicStream::SetState method
author: windows-driver-content
description: The SetState method sets the new state of playback or recording for the stream.
old-location: audio\iminiportwavecyclicstream_setstate.htm
old-project: audio
ms.assetid: 61d7252e-04af-46f1-a885-4720698ae930
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: SetState, SetState method [Audio Devices], IMiniportWaveCyclicStream, portcls/IMiniportWaveCyclicStream::SetState, audio.iminiportwavecyclicstream_setstate, audmp-routines_46474aab-87da-4121-9cb8-ee8b280c7852.xml, IMiniportWaveCyclicStream::SetState, IMiniportWaveCyclicStream interface [Audio Devices], SetState method, SetState method [Audio Devices], IMiniportWaveCyclicStream interface
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
-	IMiniportWaveCyclicStream.SetState
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportWaveCyclicStream::SetState method


## -description


The <code>SetState</code> method sets the new state of playback or recording for the stream.


## -syntax


````
NTSTATUS SetState(
  [in] KSSTATE State
);
````


## -parameters




### -param State [in]

Specifies the new state for the stream. This parameter is a <a href="..\ks\ne-ks-pksstate.md">KSSTATE</a> enumeration value. For more information, see the following Remarks section.


## -returns



<code>SetState</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.




## -remarks



For an audio filter graph, the four <a href="..\ks\ne-ks-pksstate.md">KSSTATE</a> enumeration values are interpreted as follows:

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

<a href="..\ks\ne-ks-pksstate.md">KSSTATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536723">IMiniportWaveCyclic::NewStream</a>



<a href="..\portcls\nn-portcls-iminiportwavecyclicstream.md">IMiniportWaveCyclicStream</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565110">KSPROPERTY_CONNECTION_STATE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportWaveCyclicStream::SetState method%20 RELEASE:%20(2/21/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

