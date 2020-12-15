---
UID: NS:ksmedia._tagKSJACK_SINK_INFORMATION
title: _tagKSJACK_SINK_INFORMATION (ksmedia.h)
description: The KSJACK_SINK_INFORMATION structure specifies information about a display-related digital audio device, such as an HDMI device or a display port.
old-location: audio\ksjack_sink_information.htm
tech.root: audio
ms.date: 08/20/2020
keywords: ["tagKSJACK_SINK_INFORMATION structure"]
ms.keywords: "*PKSJACK_SINK_INFORMATION, KSJACK_SINK_INFORMATION, KSJACK_SINK_INFORMATION structure [Audio Devices], PKSJACK_SINK_INFORMATION, PKSJACK_SINK_INFORMATION structure pointer [Audio Devices], _tagKSJACK_SINK_INFORMATION, aud-prop_e9bbfa8a-d002-400c-a35d-3da0a8026cd6.xml, audio.ksjack_sink_information, ksmedia/KSJACK_SINK_INFORMATION, ksmedia/PKSJACK_SINK_INFORMATION"
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
targetos: Windows
req.typenames: KSJACK_SINK_INFORMATION, *PKSJACK_SINK_INFORMATION
f1_keywords:
 - _tagKSJACK_SINK_INFORMATION
 - ksmedia/_tagKSJACK_SINK_INFORMATION
 - PKSJACK_SINK_INFORMATION
 - ksmedia/PKSJACK_SINK_INFORMATION
 - KSJACK_SINK_INFORMATION
 - ksmedia/KSJACK_SINK_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KSJACK_SINK_INFORMATION
---

# _tagKSJACK_SINK_INFORMATION structure


## -description

The **KSJACK_SINK_INFORMATION** structure specifies information about a display-related digital audio device, such as an HDMI device or a display port.

## -struct-fields

### -field ConnType

Specifies the connection type of the sink. This parameter is an enumeration of type [KSJACK_SINK_CONNECTIONTYPE](/windows/win32/api/devicetopology/ne-devicetopology-ksjack_sink_connectiontype).

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

Specifies the length of the **SinkDescription**[] member.

### -field SinkDescription

Specifies a string that contains the sink name, which must be NULL-terminated. The maximum length is defined by the MAX_SINK_DESCRIPTION_NAME_LENGTH constant (31  characters, plus a terminating **NULL**).

### -field PortId

Reserved.

## -see-also

[LUID](../igpupvdev/ns-igpupvdev-_luid.md)
