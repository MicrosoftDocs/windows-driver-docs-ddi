---
UID: NF:portcls.IMiniportWaveRTOutputStream.GetOutputStreamPresentationPosition
title: IMiniportWaveRTOutputStream::GetOutputStreamPresentationPosition method
author: windows-driver-content
description: Returns stream presentation information.
old-location: audio\iminiportwavertoutputstream_getoutputstreampresentationposition.htm
old-project: audio
ms.assetid: 8E52A10E-5666-41B5-B342-491E5AF9DD38
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GetOutputStreamPresentationPosition method [Audio Devices], IMiniportWaveRTOutputStream interface, portcls/IMiniportWaveRTOutputStream::GetOutputStreamPresentationPosition, IMiniportWaveRTOutputStream::GetOutputStreamPresentationPosition, audio.iminiportwavertoutputstream_getoutputstreampresentationposition, GetOutputStreamPresentationPosition, GetOutputStreamPresentationPosition method [Audio Devices], IMiniportWaveRTOutputStream interface [Audio Devices], GetOutputStreamPresentationPosition method, IMiniportWaveRTOutputStream
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 10 and later.
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
req.irql: Passive level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	portcls.h
apiname:
-	IMiniportWaveRTOutputStream.GetOutputStreamPresentationPosition
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportWaveRTOutputStream::GetOutputStreamPresentationPosition method


## -description


Returns stream presentation information.


## -syntax


````
NTSTATUS GetOutputStreamPresentationPosition(
  [out] KSAUDIO_PRESENTATION_POSITION *pPresentationPosition
);
````


## -parameters




### -param pPresentationPosition [out]

 pPresentationPosition returns a <a href="..\ksmedia\ns-ksmedia-ksaudio_presentation_position.md">KSAUDIO_PRESENTATION_POSITION</a> structure that represents a recent presentation position in the audio data stream. For more information, see <a href="https://msdn.microsoft.com/872A4445-8E0B-4804-ADDC-8CD9608E3EBF">IMiniportStreamAudioEngineNode::GetStreamPresentationPosition</a>.


## -returns


<code>GetOutputStreamPresentationPosition</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the function returns an appropriate error status code.



## -remarks


The OS may periodically get this property from the driver to retrieve recent presentation position information from the driver in order to allow upper layers to synchronize video or other activity with the audio stream.

The value returned in the u64PositionInBlocks member of KSAUDIO_PRESENTATION_POSITION should be consistent with the packet count returned by GetPacketCount and the driver’s interpretation of the packet number passed to SetWritePacket. In other words, the first sample of packet 0 is block 0. 



This does not mean that GetPacketCount and GetOutputStreamPresentationPosition, if called simultaneously, would return values that refer to the same sample. GetPacketCount returns information about the samples transferred from the WaveRT buffer to the hardware, while GetOutputStreamPresentationPosition returns information about samples presented at the output of the system. These are two different pieces of information. 




## -see-also

<a href="..\portcls\nn-portcls-iminiportwavertoutputstream.md">IMiniportWaveRTOutputStream</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportWaveRTOutputStream::GetOutputStreamPresentationPosition method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

