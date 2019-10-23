---
UID: NS:ksmedia._tagKSJACK_SINK_INFORMATION
title: _tagKSJACK_SINK_INFORMATION (ksmedia.h)
description: The KSJACK_SINK_INFORMATION structure specifies information about a display-related digital audio device, such as an HDMI device or a display port.
old-location: audio\ksjack_sink_information.htm
tech.root: audio
ms.assetid: ec832068-9b5d-40ce-bafc-31642539e2d9
ms.date: 05/08/2018
ms.keywords: "*PKSJACK_SINK_INFORMATION, KSJACK_SINK_INFORMATION, KSJACK_SINK_INFORMATION structure [Audio Devices], PKSJACK_SINK_INFORMATION, PKSJACK_SINK_INFORMATION structure pointer [Audio Devices], _tagKSJACK_SINK_INFORMATION, aud-prop_e9bbfa8a-d002-400c-a35d-3da0a8026cd6.xml, audio.ksjack_sink_information, ksmedia/KSJACK_SINK_INFORMATION, ksmedia/PKSJACK_SINK_INFORMATION"
ms.topic: struct
f1_keywords:
 - "ksmedia/KSJACK_SINK_INFORMATION"
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later Windows operating systems.
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
- KSJACK_SINK_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: KSJACK_SINK_INFORMATION, *PKSJACK_SINK_INFORMATION
---

# _tagKSJACK_SINK_INFORMATION structure


## -description


The <code>KSJACK_SINK_INFORMATION</code> structure specifies information about a display-related digital audio device, such as an HDMI device or a display port.


## -struct-fields




### -field ConnType

Specifies the connection type of the sink. This parameter is an enumeration of type <a href="https://go.microsoft.com/fwlink/p/?linkid=143848">KSJACK_SINK_CONNECTIONTYPE</a>. 


### -field ManufacturerId

Specifies the sink manufacturer ID.


### -field ProductId

Specifies the sink product ID.


### -field AudioLatency

Specifies the sink audio latency.


### -field HDCPCapable

Specifies that this jack sink provides support for High-bandwidth Digital Content Protection (HDCP).


### -field AICapable

Specifies that this jack sink provides support for the following data packet types: audio content protection (ACP), international standard recording code-1 (ISRC1), and ISRC2.


### -field SinkDescriptionLength

Specifies the length of the <b>SinkDescription</b>[] member.


### -field SinkDescription

Specifies a string that contains the sink name, which must be NULL-terminated. The maximum length is defined by the MAX_SINK_DESCRIPTION_NAME_LENGTH constant (31  characters, plus a terminating <b>NULL</b>).


### -field PortId

Reserved.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/igpupvdev/ns-igpupvdev-_luid">LUID</a>
 

 

