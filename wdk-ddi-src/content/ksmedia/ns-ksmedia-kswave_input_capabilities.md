---
UID: NS:ksmedia.KSWAVE_INPUT_CAPABILITIES
title: KSWAVE_INPUT_CAPABILITIES (ksmedia.h)
description: The KSWAVE_INPUT_CAPABILITIES structure is used to describe the input capabilities of a device.
old-location: stream\kswave_input_capabilities.htm
tech.root: stream
ms.date: 04/30/2019
keywords: ["KSWAVE_INPUT_CAPABILITIES structure"]
ms.keywords: "*PKSWAVE_INPUT_CAPABILITIES, KSWAVE_INPUT_CAPABILITIES, KSWAVE_INPUT_CAPABILITIES structure [Streaming Media Devices], PKSWAVE_INPUT_CAPABILITIES, PKSWAVE_INPUT_CAPABILITIES structure pointer [Streaming Media Devices], dvdref_cc35df03-82e2-4b12-a08f-26aa0fde1279.xml, ksmedia/KSWAVE_INPUT_CAPABILITIES, ksmedia/PKSWAVE_INPUT_CAPABILITIES, stream.kswave_input_capabilities"
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
targetos: Windows
req.typenames: KSWAVE_INPUT_CAPABILITIES, *PKSWAVE_INPUT_CAPABILITIES
f1_keywords:
 - PKSWAVE_INPUT_CAPABILITIES
 - ksmedia/PKSWAVE_INPUT_CAPABILITIES
 - KSWAVE_INPUT_CAPABILITIES
 - ksmedia/KSWAVE_INPUT_CAPABILITIES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - PKSWAVE_INPUT_CAPABILITIES
 - KSWAVE_INPUT_CAPABILITIES
---

# KSWAVE_INPUT_CAPABILITIES structure


## -description

The KSWAVE_INPUT_CAPABILITIES structure is used to describe the input capabilities of a device.

## -struct-fields

### -field MaximumChannelsPerConnection

Specifies the maximum channels per connection.

### -field MinimumBitsPerSample

Specifies the minimum bits per sample.

### -field MaximumBitsPerSample

Specifies the maximum bits per sample.

### -field MinimumSampleFrequency

Specifies the minimum sampling frequency.

### -field MaximumSampleFrequency

Specifies the maximum sampling frequency.

### -field TotalConnections

Indicates the total number of connections.

### -field ActiveConnections

Indicates the number of active connections.

## -remarks

This structure is used by the <a href="/windows-hardware/drivers/stream/ksproperty-wave-input-capabilities">KSPROPERTY_WAVE_INPUT_CAPABILITIES</a> property.

## -see-also

<a href="/windows-hardware/drivers/stream/ksproperty-wave-input-capabilities">KSPROPERTY_WAVE_INPUT_CAPABILITIES</a>

