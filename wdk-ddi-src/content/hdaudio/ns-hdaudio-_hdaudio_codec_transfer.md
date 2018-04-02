---
UID: NS:hdaudio._HDAUDIO_CODEC_TRANSFER
title: "_HDAUDIO_CODEC_TRANSFER"
author: windows-driver-content
description: The HDAUDIO_CODEC_TRANSFER structure specifies a codec command and the response to that command.
old-location: audio\hdaudio_codec_transfer.htm
old-project: audio
ms.assetid: ee73c5d2-9c4d-4d6f-b792-7966964fedf7
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: "*PHDAUDIO_CODEC_TRANSFER, HDAUDIO_CODEC_TRANSFER, HDAUDIO_CODEC_TRANSFER structure [Audio Devices], PHDAUDIO_CODEC_TRANSFER, PHDAUDIO_CODEC_TRANSFER structure pointer [Audio Devices], _HDAUDIO_CODEC_TRANSFER, aud-prop2_7bb7a1d5-ed28-48d4-8ca4-ff2f85002d7c.xml, audio.hdaudio_codec_transfer, hdaudio/HDAUDIO_CODEC_TRANSFER, hdaudio/PHDAUDIO_CODEC_TRANSFER"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hdaudio.h
req.include-header: Hdaudio.h
req.target-type: Windows
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
req.irql: PASSIVE_LEVEL.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	hdaudio.h
api_name:
-	HDAUDIO_CODEC_TRANSFER
product: Windows
targetos: Windows
req.typenames: HDAUDIO_CODEC_TRANSFER, *PHDAUDIO_CODEC_TRANSFER
---

# _HDAUDIO_CODEC_TRANSFER structure


## -description


The HDAUDIO_CODEC_TRANSFER structure specifies a codec command and the response to that command.


## -struct-fields




### -field Output

Specifies a codec command for the HD Audio bus driver to output to a codec that is attached to the HD Audio controller. This member is a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff536420">HDAUDIO_CODEC_COMMAND</a>. Before calling the <a href="https://msdn.microsoft.com/0ba92f5c-c4a3-48de-b8af-9c444b2e65b5">TransferCodecVerbs</a> routine, the caller writes a codec command to this member.


### -field Input

Specifies the response to the codec command. This member is a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff536422">HDAUDIO_CODEC_RESPONSE</a>. The HD Audio bus driver retrieves the response to the codec command that is contained in the <b>Output</b> member and writes the response into the <b>Input</b> member.


## -remarks



This structure is used by the <b>TransferCodecVerbs</b> routine:

<ul>
<li>
At entry, the <b>Output</b> member contains a codec command from the caller.

</li>
<li>
Upon return, the <b>Input</b> member contains the response to the codec command.

</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536420">HDAUDIO_CODEC_COMMAND</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536422">HDAUDIO_CODEC_RESPONSE</a>



<a href="https://msdn.microsoft.com/0ba92f5c-c4a3-48de-b8af-9c444b2e65b5">TransferCodecVerbs</a>
 

 

