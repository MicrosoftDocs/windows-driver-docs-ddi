---
UID: NS:ksmedia.UMPDATAFORMAT
tech.root: audio
title: UMPDATAFORMAT (ksmedia.h)
ms.date: 09/22/2025
targetos: Windows
description: The UMPDATAFORMAT structure describes the format of a Universal MIDI Packet (UMP) for MIDI 2.0 data streaming.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: Windows
req.typenames: UMPDATAFORMAT, *PUMPDATAFORMAT
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
ms.keywords: "*PUMPDATAFORMAT, UMPDATAFORMAT, UMPDATAFORMAT structure [Audio Devices], PUMPDATAFORMAT, PUMPDATAFORMAT structure pointer [Audio Devices], audio.umpdataformat, ksmedia/UMPDATAFORMAT, ksmedia/PUMPDATAFORMAT"
ai-usage: ai-generated
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - UMPDATAFORMAT
 - PUMPDATAFORMAT
f1_keywords:
 - UMPDATAFORMAT
 - ksmedia/UMPDATAFORMAT
 - PUMPDATAFORMAT
 - ksmedia/PUMPDATAFORMAT
dev_langs:
 - c++
helpviewer_keywords:
 - UMPDATAFORMAT
---

# UMPDATAFORMAT structure

## -description

The **UMPDATAFORMAT** structure describes the format of a Universal MIDI Packet (UMP) for MIDI 2.0 data streaming operations.

## -struct-fields

### -field Position

Specifies the timestamp or position information for the UMP data. This field contains timing information that can be used for precise MIDI event scheduling and synchronization in MIDI 2.0 applications.

### -field ByteCount

Specifies the size of the UMP data in bytes. This field indicates the length of the Universal MIDI Packet data, which can vary depending on the UMP message type (32-bit, 64-bit, 96-bit, or 128-bit UMPs).

## -remarks

This structure is used in MIDI 2.0 implementations to package UMP data with associated timing information. Universal MIDI Packets provide enhanced capabilities over traditional MIDI, including higher resolution for parameters, extended addressing, and support for profiles and property exchange.

The **Position** field enables precise timing control for MIDI events, which is essential for professional music applications requiring sample-accurate timing. The **ByteCount** field specifies the size of the UMP data, allowing drivers and applications to properly handle variable-length UMP messages.

UMP format is defined in the MIDI 2.0 specification and represents the next generation of MIDI data transport, providing backward compatibility with MIDI 1.0 while enabling advanced features for modern music production and performance applications. The actual UMP data follows this structure in memory.

## -see-also

- [KSPROPERTY_MIDILOOPEDSTREAMING](ne-ksmedia-ksproperty_midiloopedstreaming.md)
