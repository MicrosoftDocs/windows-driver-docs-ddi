---
UID: NS:acxpin._ACX_JACK_SINK_INFORMATION
tech.root: audio
title: ACX_JACK_SINK_INFORMATION
ms.date: 07/28/2022
targetos: Windows
description: The ACX_JACK_SINK_INFORMATION structure specifies information about a display-related digital audio device, such as an HDMI device or a display port.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: acxpin.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: ACX_JACK_SINK_INFORMATION, *PACX_JACK_SINK_INFORMATION
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxpin.h
api_name:
 - _ACX_JACK_SINK_INFORMATION
 - PACX_JACK_SINK_INFORMATION
 - ACX_JACK_SINK_INFORMATION
f1_keywords:
 - _ACX_JACK_SINK_INFORMATION
 - acxpin/_ACX_JACK_SINK_INFORMATION
 - PACX_JACK_SINK_INFORMATION
 - acxpin/PACX_JACK_SINK_INFORMATION
 - ACX_JACK_SINK_INFORMATION
 - acxpin/ACX_JACK_SINK_INFORMATION
dev_langs:
 - c++
---

## -description

The **ACX_JACK_SINK_INFORMATION** structure specifies information about a display-related digital audio device, such as an HDMI device or a display port.

## -struct-fields

### -field ConnType

A value from the [ACX_JACK_SINK_INFO_CONNECTION_TYPE](ne-acxpin-acx_jack_sink_info_connection_type.md) enum indicating the video connection type, such as HDMI or DisplayPort.

### -field ManufacturerId

Specifies the sink manufacturer ID.

### -field ProductId

Specifies the sink product ID.

### -field AudioLatency

Specifies the sink audio latency.

### -field HDCPCapable

Specifies that this jack sink provides support for high-bandwidth digital content protection (HDCP).

### -field AICapable

Specifies that this jack sink provides support for the following data packet types: audio content protection (ACP), international standard recording code-1 (ISRC1), and ISRC2.

### -field SinkDescriptionLength

Specifies the length of the *SinkDescription* field.

### -field SinkDescription

Specifies a string that contains the sink name, which must be NULL-terminated. The maximum length is defined by the MAX_SINK_DESCRIPTION_NAME_LENGTH constant (31 characters, plus a terminating NULL).

### -field PortId

Reserved.

## -remarks

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [ACX_JACK_SINK_INFO_CONNECTION_TYPE](ne-acxpin-acx_jack_sink_info_connection_type.md)
- [acxpin.h header](index.md)
