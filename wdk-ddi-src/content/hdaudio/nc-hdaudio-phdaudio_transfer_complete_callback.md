---
UID: NC:hdaudio.PHDAUDIO_TRANSFER_COMPLETE_CALLBACK
title: PHDAUDIO_TRANSFER_COMPLETE_CALLBACK (hdaudio.h)
description: HDAudio codec transfer complete callback function. PHDAUDIO_TRANSFER_COMPLETE_CALLBACK is used by the PTRANSFER_CODEC_VERBS callback function.
old-location: audio\phdaudio_transfer_complete_callback.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["PHDAUDIO_TRANSFER_COMPLETE_CALLBACK callback function"]
ms.keywords: HDAudioTransferCompleteCallback, HDAudioTransferCompleteCallback callback function [Audio Devices], PHDAUDIO_TRANSFER_COMPLETE_CALLBACK, PHDAUDIO_TRANSFER_COMPLETE_CALLBACK callback, audio.phdaudio_transfer_complete_callback, hdaudio/HDAudioTransferCompleteCallback
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
 - PHDAUDIO_TRANSFER_COMPLETE_CALLBACK
 - hdaudio/PHDAUDIO_TRANSFER_COMPLETE_CALLBACK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Hdaudio.h
api_name:
 - HDAudioTransferCompleteCallback
---

# PHDAUDIO_TRANSFER_COMPLETE_CALLBACK callback function


## -description

HDAudio codec transfer complete callback function. <b>PHDAUDIO_TRANSFER_COMPLETE_CALLBACK</b> is used by the <a href="/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-ptransfer_codec_verbs">PTRANSFER_CODEC_VERBS</a> callback function.

## -parameters

### -param 

### -param Arg1

#### - Context

 This is the same  context value that was specified previously in the <a href="/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-ptransfer_codec_verbs">PTRANSFER_CODEC_VERBS</a> routine's callbackContext parameter.


#### - pHDAudioCodecTransfer

A pointer to the codecTransfer array element that contains the codec command and the response that triggered the callback.

## -remarks

For more information, see <a href="/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-ptransfer_codec_verbs">PTRANSFER_CODEC_VERBS</a>.

## -see-also

[hdaudio.h](../hdaudio/index.md)
