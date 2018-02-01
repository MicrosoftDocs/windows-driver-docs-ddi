---
UID: NE:hdaudio._HDAUDIO_CODEC_POWER_STATE
title: "_HDAUDIO_CODEC_POWER_STATE"
author: windows-driver-content
description: The HDAUDIO_CODEC_POWER_STATE enumeration defines constants that specify the different power states that HD Audio codecs can support. All states are from DEVICE_POWER_STATE except PowerCodecD3Cold.
old-location: audio\hdaudio_codec_power_state.htm
old-project: audio
ms.assetid: 4C002B40-AD27-4FE2-B07F-5E9715E6CF1F
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: hdaudio/PHDAUDIO_CODEC_POWER_STATE, _HDAUDIO_CODEC_POWER_STATE, hdaudio/PowerCodecD2, hdaudio/PowerCodecUnspecified, PowerCodecD3Cold, PHDAUDIO_CODEC_POWER_STATE enumeration pointer [Audio Devices], hdaudio/PowerCodecMaximum, audio.hdaudio_codec_power_state, PowerCodecD1, PowerCodecMaximum, HDAUDIO_CODEC_POWER_STATE, PHDAUDIO_CODEC_POWER_STATE, hdaudio/HDAUDIO_CODEC_POWER_STATE, hdaudio/PowerCodecD3, hdaudio/PowerCodecD3Cold, PowerCodecUnspecified, hdaudio/PowerCodecD0, hdaudio/PowerCodecD1, *PHDAUDIO_CODEC_POWER_STATE, PowerCodecD2, HDAUDIO_CODEC_POWER_STATE enumeration [Audio Devices], PowerCodecD3, PowerCodecD0
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
req.irql: PASSIVE_LEVEL.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Hdaudio.h
apiname:
-	HDAUDIO_CODEC_POWER_STATE
product: Windows
targetos: Windows
req.typenames: HDAUDIO_CODEC_POWER_STATE, *PHDAUDIO_CODEC_POWER_STATE
---

# _HDAUDIO_CODEC_POWER_STATE enumeration


## -description


The <b>HDAUDIO_CODEC_POWER_STATE</b> enumeration defines constants that specify the different power states that HD Audio codecs can support.  All states
are from <a href="..\wudfddi\ne-wudfddi-_device_power_state.md">DEVICE_POWER_STATE</a> except PowerCodecD3Cold.



## -syntax


````
typedef enum _HDAUDIO_CODEC_POWER_STATE { 
  PowerCodecUnspecified   = 0,
  PowerCodecD0,
  PowerCodecD1,
  PowerCodecD2,
  PowerCodecD3,
  PowerCodecD3Cold,
  PowerCodecMaximum
} HDAUDIO_CODEC_POWER_STATE, *PHDAUDIO_CODEC_POWER_STATE;
````


## -enum-fields




### -field PowerCodecUnspecified

An unspecified power state.


### -field PowerCodecD0

Power state D0


### -field PowerCodecD1

Power state D1


### -field PowerCodecD2

Power state D2


### -field PowerCodecD3

Power state D3


### -field PowerCodecD3Cold

Power state D3 Cold


### -field PowerCodecMaximum

Power state Maximum


## -remarks


For more information about power states, see <a href="..\wudfddi\ne-wudfddi-_device_power_state.md">DEVICE_POWER_STATE</a>.


