---
UID: NC:hdaudio.PHDAUDIO_TRANSFER_COMPLETE_CALLBACK
title: PHDAUDIO_TRANSFER_COMPLETE_CALLBACK
author: windows-driver-content
description: HDAudio codec transfer complete callback function. PHDAUDIO_TRANSFER_COMPLETE_CALLBACK is used by the PTRANSFER_CODEC_VERBS callback function.
old-location: audio\phdaudio_transfer_complete_callback.htm
old-project: audio
ms.assetid: 6B3DA3B1-33E9-4BE4-A3EE-146080C483A6
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: HDAudioTransferCompleteCallback, HDAudioTransferCompleteCallback callback function [Audio Devices], PHDAUDIO_TRANSFER_COMPLETE_CALLBACK, PHDAUDIO_TRANSFER_COMPLETE_CALLBACK callback, audio.phdaudio_transfer_complete_callback, hdaudio/HDAudioTransferCompleteCallback
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
-	HDAudioTransferCompleteCallback
product: Windows
targetos: Windows
req.typenames: 
---

# PHDAUDIO_TRANSFER_COMPLETE_CALLBACK callback function


## -description


HDAudio codec transfer complete callback function. <b>PHDAUDIO_TRANSFER_COMPLETE_CALLBACK</b> is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff538596">PTRANSFER_CODEC_VERBS</a> callback function. 


## -parameters




### -param *


### -param Arg1








#### - Context

 This is the same  context value that was specified previously in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff538596">PTRANSFER_CODEC_VERBS</a> routine's callbackContext parameter.


#### - pHDAudioCodecTransfer

A pointer to the codecTransfer array element that contains the codec command and the response that triggered the callback. 


## -returns



Void




## -remarks



For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff538596">PTRANSFER_CODEC_VERBS</a>.



