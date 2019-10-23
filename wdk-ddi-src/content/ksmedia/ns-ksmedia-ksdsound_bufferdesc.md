---
UID: NS:ksmedia.__unnamed_struct_5
title: KSDSOUND_BUFFERDESC (ksmedia.h)
description: The KSDSOUND_BUFFERDESC structure describes a DirectSound buffer.
old-location: audio\ksdsound_bufferdesc.htm
tech.root: audio
ms.assetid: 95b2f2ff-b98f-4210-9a4f-898573679aa7
ms.date: 05/08/2018
ms.keywords: "*PKSDSOUND_BUFFERDESC, KSDSOUND_BUFFERDESC, KSDSOUND_BUFFERDESC structure [Audio Devices], PKSDSOUND_BUFFERDESC, PKSDSOUND_BUFFERDESC structure pointer [Audio Devices], aud-prop_309ec354-b919-40c7-8751-9e0a0000f7c8.xml, audio.ksdsound_bufferdesc, ksmedia/KSDSOUND_BUFFERDESC, ksmedia/PKSDSOUND_BUFFERDESC"
ms.topic: struct
f1_keywords:
 - "ksmedia/KSDSOUND_BUFFERDESC"
req.header: ksmedia.h
req.include-header: Ksmedia.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ksmedia.h
api_name:
- KSDSOUND_BUFFERDESC
product:
- Windows
targetos: Windows
req.typenames: KSDSOUND_BUFFERDESC, *PKSDSOUND_BUFFERDESC
---

# KSDSOUND_BUFFERDESC structure


## -description


The KSDSOUND_BUFFERDESC structure describes a DirectSound buffer.


## -struct-fields




### -field Flags

Specifies the buffer configuration. This member can be set to the bitwise OR of one or more of the following flag bits:





#### KSDSOUND_BUFFER_PRIMARY

Indicates that the buffer is a primary sound buffer (the buffer the user hears when a game is playing).



#### KSDSOUND_BUFFER_STATIC

Indicates that the buffer will be used for static sound data.



#### KSDSOUND_BUFFER_LOCHARDWARE

Forces the buffer to use hardware mixing.



#### KSDSOUND_BUFFER_LOCSOFTWARE

Forces the buffer to be stored in system memory and use software mixing.


### -field Control

Specifies the capabilities of the buffer. The capabilities of a buffer are represented by a set of control flags. This member can be set to the bitwise OR of one or more of the following flag bits:





#### KSDSOUND_BUFFER_CTRL_3D

Indicates that the buffer is either a primary buffer or a secondary buffer with 3D-control capability. If this bit is set, the KS pin representing the buffer implements a 3D node (<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksnodetype-3d-effects">KSNODETYPE_3D_EFFECTS</a>). If the KSDSOUND_BUFFER_CTRL_HRTF_3D bit is set, the 3D node supports the optional <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/kspropsetid-hrtf3d">KSPROPSETID_Hrtf3d</a> property set.



#### KSDSOUND_BUFFER_CTRL_FREQUENCY

Indicates that the buffer has frequency-control capability. If this bit is set, the pin representing the buffer implements a sample-rate conversion (<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksnodetype-src">KSNODETYPE_SRC</a>) node.



#### KSDSOUND_BUFFER_CTRL_HRTF_3D

Indicates that the buffer uses a head-related transfer function (HRTF) for 3D control. If this bit is set, then the KSDSOUND_BUFFER_CTRL_3D bit must also be set.



#### KSDSOUND_BUFFER_CTRL_PAN

Indicates that the buffer has pan-control capability. If this bit is set, the pin representing the buffer implements a volume node (<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksnodetype-volume">KSNODETYPE_VOLUME</a>) to control panning. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/directsound-node-ordering-requirements">DirectSound Node-Ordering Requirements</a>.



#### KSDSOUND_BUFFER_CTRL_VOLUME

Indicates that the buffer has volume-control capability. If this bit is set, the pin representing the buffer implements a volume node (<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksnodetype-volume">KSNODETYPE_VOLUME</a>) to control the stream's volume level.



#### KSDSOUND_BUFFER_CTRL_POSITIONNOTIFY

Indicates that the buffer has position-notification capability. If this bit is set, the pin representing the buffer supports the <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-audio-position">KSPROPERTY_AUDIO_POSITION</a> property.


### -field WaveFormatEx

Specifies the wave-data format of the buffer. This member is a structure of type <a href="https://docs.microsoft.com/windows/desktop/api/mmreg/ns-mmreg-twaveformatex">WAVEFORMATEX</a>.


## -remarks



The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksdataformat_dsound">KSDATAFORMAT_DSOUND</a> structure contains a <b>BufferDesc</b> member that is a KSDSOUND_BUFFERDESC structure.

Note that the <b>WaveFormatEx</b> member of the KSDSOUND_BUFFERDESC structure can be extended to include additional format information (for example, a channel configuration mask). For details, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-waveformatextensible">WAVEFORMATEXTENSIBLE</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksdataformat_dsound">KSDATAFORMAT_DSOUND</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksnodetype-3d-effects">KSNODETYPE_3D_EFFECTS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksnodetype-src">KSNODETYPE_SRC</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksnodetype-volume">KSNODETYPE_VOLUME</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-audio-position">KSPROPERTY_AUDIO_POSITION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/kspropsetid-hrtf3d">KSPROPSETID_Hrtf3d</a>



<a href="https://docs.microsoft.com/windows/desktop/api/mmreg/ns-mmreg-twaveformatex">WAVEFORMATEX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-waveformatextensible">WAVEFORMATEXTENSIBLE</a>
 

 

