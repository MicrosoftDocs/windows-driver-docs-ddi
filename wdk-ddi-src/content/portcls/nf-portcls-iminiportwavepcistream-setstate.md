---
UID: NF:portcls.IMiniportWavePciStream.SetState
title: IMiniportWavePciStream::SetState method
author: windows-driver-content
description: The SetState method changes the state of the stream transport.
old-location: audio\iminiportwavepcistream_setstate.htm
old-project: audio
ms.assetid: ae029e17-7229-49a6-bf5f-96e0cb143d5b
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IMiniportWavePciStream, IMiniportWavePciStream::SetState, SetState
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
req.alt-api: IMiniportWavePciStream.SetState
req.alt-loc: portcls.h
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
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
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

KSSTATE_RUN 

Data transport in the current audio filter graph is running and functioning as normal.

KSSTATE_ACQUIRE 

This is a transitional state that helps to manage the transition between KSSTATE_RUN and KSSTATE_STOP.

KSSTATE_PAUSE 

This is a transitional state that helps to manage the transition between KSSTATE_RUN and KSSTATE_STOP. 

KSSTATE_STOP 

Data transport is stopped in the current audio filter graph.

For most miniports, KSSTATE_ACQUIRE and KSSTATE_PAUSE are indistinguishable.

Transitions always occur in one of the following two sequences:

STOP -&gt; ACQUIRE -&gt; PAUSE -&gt; RUN

RUN -&gt; PAUSE -&gt; ACQUIRE -&gt; STOP

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff536735">IMiniportWavePci::NewStream</a> method sets the initial state of the stream to KSSTATE_STOP. 


## -see-also
<dl>
<dt>
<a href="..\portcls\nn-portcls-iminiportwavepcistream.md">IMiniportWavePciStream</a>
</dt>
<dt>
<a href="..\ks\ne-ks-pksstate.md">KSSTATE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565110">KSPROPERTY_CONNECTION_STATE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536735">IMiniportWavePci::NewStream</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportWavePciStream::SetState method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

