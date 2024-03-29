---
UID: NS:ks.KSTIME
title: KSTIME (ks.h)
description: The KSTIME structure specifies a time stamp that can be used to indicate stream position.
old-location: stream\kstime.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KSTIME structure"]
ms.keywords: "*PKSTIME, KSTIME, KSTIME structure [Streaming Media Devices], PKSTIME, PKSTIME structure pointer [Streaming Media Devices], ks-struct_9db70ddb-ae2c-464b-a481-6927adef449c.xml, ks/KSTIME, ks/PKSTIME, stream.kstime"
req.header: ks.h
req.include-header: Ks.h
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
req.typenames: KSTIME, *PKSTIME
f1_keywords:
 - PKSTIME
 - ks/PKSTIME
 - KSTIME
 - ks/KSTIME
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - PKSTIME
 - KSTIME
---

# KSTIME structure


## -description

The KSTIME structure specifies a time stamp that can be used to indicate stream position.

## -struct-fields

### -field Time

Specifies a time value. When using unscaled time, <b>Time</b> is in units of 100-nanoseconds. When using scaled time, <b>Time</b> is in units governed by the scale factor expressed in the <b>Numerator</b> and <b>Denominator</b> members. For more information about scaled and unscaled time, see <b>Remarks</b>.

### -field Numerator

Specifies the numerator of the scaling factor for a scaled time value. For a nonscaled value, this should be one. <b>Numerator</b> must not be zero.

### -field Denominator

Specifies the denominator of the scaling factor for a scaled time value. For a nonscaled value, this should be one. <b>Denominator</b> must not be zero.

## -remarks

Unscaled time stamps are in 100-nanosecond units. A data stream can use different units by specifying the numerator and denominator of a scale factor.

