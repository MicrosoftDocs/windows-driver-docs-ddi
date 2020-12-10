---
UID: NC:hdaudio.PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK
title: PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK (hdaudio.h)
description: HDAudio codec unsolicited response callback function. PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK is used by the PREGISTER_EVENT_CALLBACK callback function.
old-location: audio\phdaudio_unsolicited_response_callback.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK callback function"]
ms.keywords: HDAudioUnsolicitedResponseCallback, HDAudioUnsolicitedResponseCallback callback function [Audio Devices], PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK, PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK callback, audio.phdaudio_unsolicited_response_callback, hdaudio/HDAudioUnsolicitedResponseCallback
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK
 - hdaudio/PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Hdaudio.h
api_name:
 - HDAudioUnsolicitedResponseCallback
---

# PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK callback function


## -description

HDAudio codec unsolicited response callback function. <b>PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK</b> is used by the <a href="/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pregister_event_callback">PREGISTER_EVENT_CALLBACK</a> callback function.

## -parameters

### -param Arg1

### -param Arg2

#### - Context

This is the callbackContext value that was passed previously to <a href="/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pregister_event_callback">PREGISTER_EVENT_CALLBACK</a>.


#### - HDAudioCodecResponse

This is a structure of type <a href="/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_codec_response">HDAUDIO_CODEC_RESPONSE</a> that specifies the codec's response to the command. This structure is passed by value.

## -remarks

The HD Audio bus driver calls the callback routine at PASSIVE_LEVEL.

## -see-also

[hdaudio.h](../hdaudio/index.md)
