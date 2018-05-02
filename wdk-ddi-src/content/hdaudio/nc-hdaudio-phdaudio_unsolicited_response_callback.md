---
UID: NC:hdaudio.PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK
title: PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK
author: windows-driver-content
description: HDAudio codec unsolicited response callback function. PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK is used by the PREGISTER_EVENT_CALLBACK callback function.
old-location: audio\phdaudio_unsolicited_response_callback.htm
old-project: audio
ms.assetid: B98F669D-D0DE-4FF2-903C-D51E0FEEE840
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: HDAudioUnsolicitedResponseCallback, HDAudioUnsolicitedResponseCallback callback function [Audio Devices], PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK, PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK callback, audio.phdaudio_unsolicited_response_callback, hdaudio/HDAudioUnsolicitedResponseCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: hdaudio.h
req.include-header: 
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Hdaudio.h
api_name:
-	HDAudioUnsolicitedResponseCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK callback function


## -description


HDAudio codec unsolicited response callback function. <b>PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK</b> is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537803">PREGISTER_EVENT_CALLBACK</a> callback function. 


## -parameters




### -param Arg1


### -param Arg2








#### - Context

This is the callbackContext value that was passed previously to <a href="https://msdn.microsoft.com/library/windows/hardware/ff537803">PREGISTER_EVENT_CALLBACK</a>.


#### - HDAudioCodecResponse

This is a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff536422">HDAUDIO_CODEC_RESPONSE</a> that specifies the codec's response to the command. This structure is passed by value.  


## -returns



Void




## -remarks



The HD Audio bus driver calls the callback routine at PASSIVE_LEVEL.



