---
UID: NF:portcls.IMiniportWavePciStream.SetState
title: IMiniportWavePciStream::SetState method
author: windows-driver-content
description: The SetState method changes the state of the stream transport.
old-location: audio\iminiportwavepcistream_setstate.htm
old-project: audio
ms.assetid: ae029e17-7229-49a6-bf5f-96e0cb143d5b
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: portcls/IMiniportWavePciStream::SetState, SetState method [Audio Devices], IMiniportWavePciStream interface, audmp-routines_71487eb9-23d5-4428-92c0-fc75e58d0da5.xml, audio.iminiportwavepcistream_setstate, IMiniportWavePciStream interface [Audio Devices], SetState method, IMiniportWavePciStream, SetState method [Audio Devices], IMiniportWavePciStream::SetState, SetState
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
-	IMiniportWavePciStream.SetState
product: Windows
targetos: Windows
req.typenames: "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---

# IMiniportWavePciStream::SetState method


## -description


The <code>SetState</code> method changes the state of the stream transport.


## -syntax


````
NTSTATUS SetState(
  [in] KSSTATE State
);
````


## -parameters




### -param State [in]

Specifies the new state of the stream. This parameter is a <a href="..\ks\ne-ks-pksstate.md">KSSTATE</a> enumeration value. For more information, see the following Remarks section.


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
For most miniports, KSSTATE_ACQUIRE and KSSTATE_PAUSE are indistinguishable.

Transitions always occur in one of the following two sequences:

<ul>
<li>
STOP -&gt; ACQUIRE -&gt; PAUSE -&gt; RUN

</li>
<li>
RUN -&gt; PAUSE -&gt; ACQUIRE -&gt; STOP

</li>
</ul>
The <a href="https://msdn.microsoft.com/library/windows/hardware/ff536735">IMiniportWavePci::NewStream</a> method sets the initial state of the stream to KSSTATE_STOP. 




## -see-also

<a href="..\ks\ne-ks-pksstate.md">KSSTATE</a>



<a href="..\portcls\nn-portcls-iminiportwavepcistream.md">IMiniportWavePciStream</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565110">KSPROPERTY_CONNECTION_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536735">IMiniportWavePci::NewStream</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportWavePciStream::SetState method%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

