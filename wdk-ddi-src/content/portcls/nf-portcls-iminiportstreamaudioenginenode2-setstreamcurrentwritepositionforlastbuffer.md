---
UID: NF:portcls.IMiniportStreamAudioEngineNode2.SetStreamCurrentWritePositionForLastBuffer
title: IMiniportStreamAudioEngineNode2::SetStreamCurrentWritePositionForLastBuffer method
author: windows-driver-content
description: Sets the current cursor position in the last audio data stream that was written to the audio buffer.
old-location: audio\iminiportstreamaudioenginenode2_setstreamcurrentwritepositionforlastbuffer.htm
old-project: audio
ms.assetid: 93E3D03B-6FA1-49D5-AF38-6C2FEA3FC95D
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IMiniportStreamAudioEngineNode2, IMiniportStreamAudioEngineNode2 interface [Audio Devices], SetStreamCurrentWritePositionForLastBuffer method, IMiniportStreamAudioEngineNode2::SetStreamCurrentWritePositionForLastBuffer, SetStreamCurrentWritePositionForLastBuffer method [Audio Devices], SetStreamCurrentWritePositionForLastBuffer method [Audio Devices], IMiniportStreamAudioEngineNode2 interface, SetStreamCurrentWritePositionForLastBuffer,IMiniportStreamAudioEngineNode2.SetStreamCurrentWritePositionForLastBuffer, audio.iminiportstreamaudioenginenode2_setstreamcurrentwritepositionforlastbuffer, portcls/IMiniportStreamAudioEngineNode2::SetStreamCurrentWritePositionForLastBuffer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Portcls.h
api_name:
-	IMiniportStreamAudioEngineNode2.SetStreamCurrentWritePositionForLastBuffer
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportStreamAudioEngineNode2::SetStreamCurrentWritePositionForLastBuffer method


## -description


Sets the current cursor position in the last audio data stream that was written to the audio buffer.


## -syntax


````
NTSTATUS SetStreamCurrentWritePositionForLastBuffer(
  [in] ULONG ulWritePosition
);
````


## -parameters




### -param _ulWritePosition [in]

The current cursor position in the last audio data stream.


## -returns



<b>SetStreamCurrentWritePositionForLastBuffer</b> returns S_OK if the call was successful. Otherwise, the method returns an appropriate error code.




## -remarks



When a client app performs the very last write operation to the audio buffer to be processed by the audio  driver of an offloaded stream, the audio driver calls <b>SetStreamCurrentWritePositionForLastBuffer</b>.  The <b>SetStreamCurrentWritePositionForLastBuffer</b> method indicates the “write position” of the very last buffer in a stream. Note that this last buffer could be only partially filled.

If the buffer is only partially filled, then the audio driver needs to notify the audio engine when the last valid byte in the buffer has been <i>rendered</i>.  This differs from the normal functionality where the audio driver notified the audio engine when the driver <i>fetched</i> the last byte in the buffer.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn292492">KSPROPERTY_AUDIO_WAVERT_CURRENT_WRITE_LASTBUFFER_POSITION</a>



<a href="..\portcls\nn-portcls-iminiportstreamaudioenginenode2.md">IMiniportStreamAudioEngineNode2</a>



 

 


