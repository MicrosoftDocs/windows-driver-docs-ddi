---
UID: NC:hdaudio.PSET_DMA_ENGINE_STATE
title: PSET_DMA_ENGINE_STATE
author: windows-driver-content
description: The SetDmaEngineState routine sets the state of one or more DMA engines to the Running, Stopped, Paused, or Reset state.The function pointer type for a SetDmaEngineState routine is defined as:
old-location: audio\setdmaenginestate.htm
old-project: audio
ms.assetid: 05cfb827-e143-4d77-b378-e02dd381e429
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: audio.setdmaenginestate, SetDmaEngineState callback function [Audio Devices], SetDmaEngineState, PSET_DMA_ENGINE_STATE, PSET_DMA_ENGINE_STATE, hdaudio/SetDmaEngineState, aud-prop2_a1455dc1-3ed9-43c3-a5b6-af321c26eefe.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: hdaudio.h
req.include-header: Hdaudio.h
req.target-type: Desktop
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	hdaudio.h
apiname:
-	SetDmaEngineState
product: Windows
targetos: Windows
req.typenames: GPIO_WRITE_PINS_PARAMETERS, *PGPIO_WRITE_PINS_PARAMETERS
---

# PSET_DMA_ENGINE_STATE callback


## -description


The <i>SetDmaEngineState</i> routine sets the state of one or more DMA engines to the Running, Stopped, Paused, or Reset state.

The function pointer type for a <i>SetDmaEngineState</i> routine is defined as:


## -prototype


````
PSET_DMA_ENGINE_STATE SetDmaEngineState;

NTSTATUS SetDmaEngineState(
  _In_ PVOID                context,
  _In_ HDAUDIO_STREAM_STATE streamState,
  _In_ ULONG                numberOfHandles,
  _In_ PHANDLE              handles
)
{ ... }
````


## -parameters




### -param _context



### -param StreamState



### -param NumberOfHandles



### -param Handles






#### - context [in]

Specifies the context value from the <b>Context</b> member of the <a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface.md">HDAUDIO_BUS_INTERFACE</a><u>, </u><a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_v2.md">HDAUDIO_BUS_INTERFACE_V2</a>, or <a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_bdl.md">HDAUDIO_BUS_INTERFACE_BDL</a> structure.


#### - streamState [in]

Specifies the new stream state. Set this parameter to one of the following HDAUDIO_STREAM_STATE enumeration values:
<ul>
<li>
<b>PauseState</b> (paused)

</li>
<li>
<b>ResetState</b> (reset)

</li>
<li>
<b>RunState</b> (running)

</li>
<li>
<b>StopState</b> (stopped)

</li>
</ul>In the current implementation, <b>PauseState</b> and <b>StopState</b> represent the same hardware state.


#### - numberOfHandles [in]

Specifies the number of handles in the <i>handles</i> array. Set this parameter to a nonzero value.


#### - handles [in]

Pointer to an array of handles to DMA engines. Specify a non-<b>NULL</b> value for this parameter.


## -returns


<i>SetDmaEngineState</i> returns STATUS_SUCCESS if the call succeeds in changing the DMA engines' states. Otherwise, the routine returns an appropriate error code. The following table shows some of the possible return status codes.
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
Indicates that one of the handles is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Indicates that one of the parameter values is incorrect (invalid parameter value or bad pointer).

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
Indicates that no buffer is currently allocated for one of the DMA engines.

</td>
</tr>
</table> 



## -remarks


This routine changes the state of one or more DMA engines to the state that the <i>streamState</i> parameter specifies. The routine synchronizes the state transitions of all the DMA engines that the handles in the <i>handles</i> array identify. For more information, see <a href="https://msdn.microsoft.com/c25f4ca2-8a9f-43bc-a1bf-b71826b446ff">Synchronizing Two or More Streams</a>.

Before calling this routine, set up each DMA engine in the <i>handles</i> array:
<ul>
<li>
If using the HDAUDIO_BUS_INTERFACE version of the HD Audio DDI, call <a href="..\hdaudio\nc-hdaudio-pallocate_dma_buffer.md">AllocateDmaBuffer</a> to set up the DMA engine.

</li>
<li>
If using the HDAUDIO_BUS_INTERFACE_BDL version of the DDI, call <a href="..\hdaudio\nc-hdaudio-psetup_dma_engine_with_bdl.md">SetupDmaEngineWithBdl</a> to set up the DMA engine.

</li>
</ul>If no DMA buffer is currently allocated for any DMA engine in the <i>handles</i> array, an attempt to change the stream to any state other than Reset causes the <i>SetDmaEngineState</i> call to fail and return error code STATUS_INVALID_DEVICE_REQUEST.

The stream state cannot transition directly between Running and Reset. Instead, the stream must first pass through an intermediate state of Paused or Stopped:
<ul>
<li>
From a Running or Reset state, the stream state can change directly to either Paused or Stopped.

</li>
<li>
From a paused or stopped state, the stream state can change directly to either Running or Reset.

</li>
</ul>A WDM audio driver calls this routine during a call to its <b>SetState</b> method. For example, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff536720">IMiniportWaveCyclicStream::SetState</a>.



## -see-also

<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface.md">HDAUDIO_BUS_INTERFACE</a>

<a href="..\hdaudio\nc-hdaudio-pallocate_dma_buffer.md">AllocateDmaBuffer</a>

<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_bdl.md">HDAUDIO_BUS_INTERFACE_BDL</a>

<a href="..\hdaudio\ns-hdaudio-_hdaudio_bus_interface_v2.md">HDAUDIO_BUS_INTERFACE_V2</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536720">IMiniportWaveCyclicStream::SetState</a>

<a href="..\hdaudio\nc-hdaudio-psetup_dma_engine_with_bdl.md">SetupDmaEngineWithBdl</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PSET_DMA_ENGINE_STATE callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

