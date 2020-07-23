---
UID: NS:ksmedia.__unnamed_struct_35
title: KSRTAUDIO_SETWRITEPACKET_INFO (ksmedia.h)
description: The KSRTAUDIO_SETWRITEPACKET_INFO structure describes information associated with an audio packet.
old-location: audio\ksrtaudio_setwritepacket_info.htm
tech.root: audio
ms.assetid: 641DE2B5-7903-4D25-A280-F2BCCE8B1500
ms.date: 05/08/2018
keywords: ["KSRTAUDIO_SETWRITEPACKET_INFO structure"]
ms.keywords: "*PKSRTAUDIO_SETWRITEPACKET_INFO, KSRTAUDIO_SETWRITEPACKET_INFO, KSRTAUDIO_SETWRITEPACKET_INFO structure [Audio Devices], PKSRTAUDIO_SETWRITEPACKET_INFO, PKSRTAUDIO_SETWRITEPACKET_INFO structure pointer [Audio Devices], audio.ksrtaudio_setwritepacket_info, ksmedia/KSRTAUDIO_SETWRITEPACKET_INFO, ksmedia/PKSRTAUDIO_SETWRITEPACKET_INFO"
f1_keywords:
 - "ksmedia/KSRTAUDIO_SETWRITEPACKET_INFO"
 - "KSRTAUDIO_SETWRITEPACKET_INFO"
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 10 and later Windows operating systems.
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
- KSRTAUDIO_SETWRITEPACKET_INFO
targetos: Windows
req.typenames: KSRTAUDIO_SETWRITEPACKET_INFO, *PKSRTAUDIO_SETWRITEPACKET_INFO
---

# KSRTAUDIO_SETWRITEPACKET_INFO structure


## -description


The KSRTAUDIO_SETWRITEPACKET_INFO structure describes information associated with an audio packet.


## -struct-fields




### -field PacketNumber

 The number of the packet written by the OS to the WaveRT buffer. Depending on the values returned by the driver in the KSPROPERTY_RTAUDIO_GETPACKETCOUNT property, the PacketNumber may skip values. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-rtaudio-packetcount">KSPROPERTY_RTAUDIO_PACKETCOUNT</a>. 




### -field Flags

Additional attributes related to the packet or stream. 



<i>KSSTREAM_HEADER_OPTIONSF_ENDOFSTREAM</i> - This flag indicates that this packet represents the end of the data stream. 




### -field EosPacketLength

The length of the EOS packet if <i>KSSTREAM_HEADER_OPTIONSF_ENDOFSTREAM</i> is specified in Flags. Zero is a valid value. If <i>KSSTREAM_HEADER_OPTIONSF_ENDOFSTREAM</i> is not specified in Flags, this parameter is ignored. The EosPacketLength is measured in bytes.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-rtaudio-setwritepacket">KSPROPERTY_RTAUDIO_SETWRITEPACKET</a>
 

 

