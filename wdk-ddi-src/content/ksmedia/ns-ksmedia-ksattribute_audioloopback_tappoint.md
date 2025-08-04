---
UID: NS:ksmedia.tagKSATTRIBUTE_AUDIOLOOPBACK_TAPPOINT
tech.root: audio
title: KSATTRIBUTE_AUDIOLOOPBACK_TAPPOINT
ms.date: 08/04/2025
targetos: Windows
description: The KSATTRIBUTE_AUDIOLOOPBACK_TAPPOINT attribute points to the  pre and post tap audio point definitions.
prerelease: false
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
req.typenames: KSATTRIBUTE_AUDIOLOOPBACK_TAPPOINT, *PKSATTRIBUTE_AUDIOLOOPBACK_TAPPOINT
typedef_isUnnamed: false
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - tagKSATTRIBUTE_AUDIOLOOPBACK_TAPPOINT
 - PKSATTRIBUTE_AUDIOLOOPBACK_TAPPOINT
 - KSATTRIBUTE_AUDIOLOOPBACK_TAPPOINT
f1_keywords:
 - tagKSATTRIBUTE_AUDIOLOOPBACK_TAPPOINT
 - ksmedia/tagKSATTRIBUTE_AUDIOLOOPBACK_TAPPOINT
 - PKSATTRIBUTE_AUDIOLOOPBACK_TAPPOINT
 - ksmedia/PKSATTRIBUTE_AUDIOLOOPBACK_TAPPOINT
 - KSATTRIBUTE_AUDIOLOOPBACK_TAPPOINT
 - ksmedia/KSATTRIBUTE_AUDIOLOOPBACK_TAPPOINT
dev_langs:
 - c++
helpviewer_keywords:
 - tagKSATTRIBUTE_AUDIOLOOPBACK_TAPPOINT
---

# KSATTRIBUTE_AUDIOLOOPBACK_TAPPOINT structure (ksmedia.h)

## -description

The KSATTRIBUTE_AUDIOLOOPBACK_TAPPOINT attribute points to the  pre and post tap audio point definitions. It is available starting in Windows 11 24H2.

## -struct-fields

### -field AttributeHeader

The AttributeHeader member specifies the attribute header using a [KSATTRIBUTE](/windows-hardware/drivers/ddi/ks/ns-ks-ksattribute) data type.

### -field TapPoint

The TapPoint member specifies the tap point type defined in the [AUDIOLOOPBACK_TAPPOINT_TYPE](ne-ksmedia-audioloopback_tappoint_type.md) enumeration.

## -remarks

The KSATTRIBUTE_AUDIOLOOPBACK_TAPPOINT structure available in ksmedia.h can provide a wrapper for specifying the AUDIO_LOOPBACK_TAPPOINT_TYPE attribute about where to tap loopback in the stream graph.

If KSATTRIBUTEID_AUDIOLOOPBACK_TAPPOINT is provided, then loopback should be collected based on options described by [AUDIOLOOPBACK_TAPPOINT_TYPE](ne-ksmedia-audioloopback_tappoint_type.md).

The *Ksmedia.h* header file defines the **KSATTRIBUTEID_AUDIOLOOPBACK_TAPPOINT** attribute ID as follows:

```cpp
#define STATIC_KSATTRIBUTEID_AUDIOLOOPBACK_TAPPOINT 0x2795a0f7, 0x1688, 0x44fe, 0xbc, 0x14, 0xbf, 0x82, 0x73, 0x99, 0x21, 0x41
DEFINE_GUIDSTRUCT("2795A0F7-1688-44FE-BC14-BF8273992141", KSATTRIBUTEID_AUDIOLOOPBACK_TAPPOINT);
#define KSATTRIBUTEID_AUDIOLOOPBACK_TAPPOINT DEFINE_GUIDNAMED(KSATTRIBUTEID_AUDIOLOOPBACK_TAPPOINT)
```

At pin creation time, a KSATTRIBUTEID_AUDIOLOOPBACK_TAPPOINT  entry containing a KSATTRIBUTE_AUDIOLOOPBACK_TAPPOINT is added to the pin creation attributes. This entry contains the AUDIOLOOPBACK_TAPPOINT_TYPE for the loopback pin instance.

## -see-also

- [KSPROPERTY_AUDIOLOOPBACK](/windows-hardware/drivers/audio/ksproperty-audioloopback)
- [KSPROPSETID_AudioLoopback](/windows-hardware/drivers/audio/kspropsetid-audioloopback)
- [AUDIOLOOPBACK_TAPPOINT_TYPE](ne-ksmedia-audioloopback_tappoint_type.md)
