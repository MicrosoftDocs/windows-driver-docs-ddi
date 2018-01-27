---
UID: NC:hdaudio.PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK
title: PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK
author: windows-driver-content
description: HDAudio codec unsolicited response callback function. PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK is used by the PREGISTER_EVENT_CALLBACK callback function.
old-location: audio\phdaudio_unsolicited_response_callback.htm
old-project: audio
ms.assetid: B98F669D-D0DE-4FF2-903C-D51E0FEEE840
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: audio.phdaudio_unsolicited_response_callback, HDAudioUnsolicitedResponseCallback callback function [Audio Devices], HDAudioUnsolicitedResponseCallback, PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK, PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK, hdaudio/HDAudioUnsolicitedResponseCallback, HDAudioUnsolicitedResponseCallback callback function [Audio Devices], HDAudioUnsolicitedResponseCallback
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	Hdaudio.h
apiname: 
-	HDAudioUnsolicitedResponseCallback
product: Windows
targetos: Windows
req.typenames: SM_SetRNIDMgmtInfo_OUT, *PSM_SetRNIDMgmtInfo_OUT
---

# PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK callback


## -description


HDAudio codec unsolicited response callback function. <b>PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK</b> is used by the <a href="..\hdaudio\nc-hdaudio-pregister_event_callback.md">PREGISTER_EVENT_CALLBACK</a> callback function. 


## -prototype


````
PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK HDAudioUnsolicitedResponseCallback;

VOID HDAudioUnsolicitedResponseCallback(
   HDAUDIO_CODEC_RESPONSE HDAudioCodecResponse,
   PVOID                  Context
)
{ ... }

typedef PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK HDAudioUnsolicitedResponseCallback;
````


## -parameters




### -param HDAUDIO_CODEC_RESPONSE



### -param PVOID






#### - Context

This is the callbackContext value that was passed previously to <a href="..\hdaudio\nc-hdaudio-pregister_event_callback.md">PREGISTER_EVENT_CALLBACK</a>.


#### - HDAudioCodecResponse

This is a structure of type <a href="..\hdaudio\ns-hdaudio-_hdaudio_codec_response.md">HDAUDIO_CODEC_RESPONSE</a> that specifies the codec's response to the command. This structure is passed by value.  


## -returns


Void



## -remarks


The HD Audio bus driver calls the callback routine at PASSIVE_LEVEL.


