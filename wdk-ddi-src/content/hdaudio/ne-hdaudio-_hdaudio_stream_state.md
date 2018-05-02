---
UID: NE:hdaudio._HDAUDIO_STREAM_STATE
title: "_HDAUDIO_STREAM_STATE"
author: windows-driver-content
description: The HDAUDIO_STREAM_STATE enumeration defines constants that specify the different stream states supported by HDAudio.
old-location: audio\hdaudio_stream_state.htm
old-project: audio
ms.assetid: A1029A2D-980F-44F5-B7D6-1C37F97D0368
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: "*PHDAUDIO_STREAM_STATE, HDAUDIO_STREAM_STATE, HDAUDIO_STREAM_STATE enumeration [Audio Devices], PHDAUDIO_STREAM_STATE, PHDAUDIO_STREAM_STATE enumeration pointer [Audio Devices], PauseState, ResetState, RunState, StopState, _HDAUDIO_STREAM_STATE, audio.hdaudio_stream_state, hdaudio/HDAUDIO_STREAM_STATE, hdaudio/PHDAUDIO_STREAM_STATE, hdaudio/PauseState, hdaudio/ResetState, hdaudio/RunState, hdaudio/StopState"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Hdaudio.h
api_name:
-	HDAUDIO_STREAM_STATE
product:
- Windows
targetos: Windows
req.typenames: HDAUDIO_STREAM_STATE, *PHDAUDIO_STREAM_STATE
---

# _HDAUDIO_STREAM_STATE enumeration


## -description


The <b>HDAUDIO_STREAM_STATE</b> enumeration defines constants that specify the different stream states supported by HDAudio.


## -enum-fields




### -field ResetState

The reset state.


### -field StopState

The stop state.


### -field PauseState

The pause state.


### -field RunState

The run state.


## -remarks



This enumeration is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537889">PSET_DMA_ENGINE_STATE</a>.



