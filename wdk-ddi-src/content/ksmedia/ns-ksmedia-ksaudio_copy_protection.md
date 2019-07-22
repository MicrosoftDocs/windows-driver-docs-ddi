---
UID: NS:ksmedia.__unnamed_struct_39
title: KSAUDIO_COPY_PROTECTION (ksmedia.h)
description: The KSAUDIO_COPY_PROTECTION structure specifies the copy-protection status of an audio stream.
old-location: audio\ksaudio_copy_protection.htm
tech.root: audio
ms.assetid: 7dab0240-67c3-4412-a7a5-bb98d84c6bdd
ms.date: 05/08/2018
ms.keywords: "*PKSAUDIO_COPY_PROTECTION, KSAUDIO_COPY_PROTECTION, KSAUDIO_COPY_PROTECTION structure [Audio Devices], PKSAUDIO_COPY_PROTECTION, PKSAUDIO_COPY_PROTECTION structure pointer [Audio Devices], aud-prop_94eac763-0c97-406d-b255-686ac82f908c.xml, audio.ksaudio_copy_protection, ksmedia/KSAUDIO_COPY_PROTECTION, ksmedia/PKSAUDIO_COPY_PROTECTION"
ms.topic: struct
f1_keywords:
 - "ksmedia/KSAUDIO_COPY_PROTECTION"
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
- KSAUDIO_COPY_PROTECTION
product:
- Windows
targetos: Windows
req.typenames: KSAUDIO_COPY_PROTECTION, *PKSAUDIO_COPY_PROTECTION
---

# KSAUDIO_COPY_PROTECTION structure

## -description

The **KSAUDIO_COPY_PROTECTION** structure specifies the copy-protection status of an audio stream.

## -struct-fields

### -field fCopyrighted

Indicates whether the stream is copyrighted. If **TRUE**, the stream is copyrighted. If **FALSE**, the stream is not copyrighted and is not subject to copy protection.

### -field fOriginal

Indicates whether the stream is an original, first-generation copy of a stream or a second-generation copy of the original. If **TRUE**, the stream is original. If **FALSE**, it is a second-generation copy.

## -remarks

The [KSPROPERTY_AUDIO_COPY_PROTECTION](https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-audio-copy-protection) property uses this structure to report whether a stream is copyrighted, and also whether the stream is an original stream or a copy of the original stream.

An audio device that supports copy protection can use copyright and copy-generation information about a stream to prevent unlimited copying of proprietary audio content. For example, the Serial Copy Management System (SCMS) defines one level of copy protection that allows copying of an original, first-generation copy of a stream, but prevents copying of second-generation copies of the stream.

The KSPROPERTY_AUDIO_COPY_PROTECTION property is separate from and unrelated to the implementation of [Digital Rights Management (DRM)](https://docs.microsoft.com/windows-hardware/drivers/audio/digital-rights-management) and the [Secure Audio Path (SAP) for Windows Media](https://docs.microsoft.com/windows/win32/wmformat/the-secure-audio-path-model--deprecated).

## -see-also

[KSPROPERTY_AUDIO_COPY_PROTECTION](https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-audio-copy-protection)
