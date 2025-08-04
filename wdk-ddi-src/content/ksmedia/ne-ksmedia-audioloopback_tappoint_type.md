---
UID: NE:ksmedia.tagAUDIOLOOPBACK_TAPPOINT_TYPE
tech.root: audio
title: AUDIOLOOPBACK_TAPPOINT_TYPE
ms.date: 08/04/2025
targetos: Windows
description: The AUDIOLOOPBACK_TAPPOINT_TYPE enum contains the  pre and post tap point definitions.
prerelease: false
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 11 24H2
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
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - tagAUDIOLOOPBACK_TAPPOINT_TYPE
 - AUDIOLOOPBACK_TAPPOINT_TYPE
f1_keywords:
 - tagAUDIOLOOPBACK_TAPPOINT_TYPE
 - ksmedia/tagAUDIOLOOPBACK_TAPPOINT_TYPE
 - AUDIOLOOPBACK_TAPPOINT_TYPE
 - ksmedia/AUDIOLOOPBACK_TAPPOINT_TYPE
dev_langs:
 - c++
helpviewer_keywords:
 - tagAUDIOLOOPBACK_TAPPOINT_TYPE
---

# AUDIOLOOPBACK_TAPPOINT_TYPE enumeration (ksmedia.h)

## -description

The **AUDIOLOOPBACK_TAPPOINT_TYPE** enum contains the pre and post tap point definitions.

## -enum-fields

### -field AUDIOLOOPBACK_TAPPOINT_PREVOLUMEMUTE

The loopback stream tap point is returned before applying endpoint volume and mute.

### -field AUDIOLOOPBACK_TAPPOINT_POSTVOLUMEMUTE

The loopback stream tap point is after applying endpoint volume and mute.

## -remarks

The **AUDIOLOOPBACK_TAPPOINT_TYPE** enumeration is available starting in Windows 11 24H2.

The enum is used by [KSPROPERTY_AUDIOLOOPBACK](/windows-hardware/drivers/audio/ksproperty-audioloopback) in the [KSPROPSETID_AudioLoopback](/windows-hardware/drivers/audio/kspropsetid-audioloopback) property set to indicate if the loopback tap point is pre or post volume and mute.

## -see-also

- [KSPROPERTY_AUDIOLOOPBACK](/windows-hardware/drivers/audio/ksproperty-audioloopback)
- [KSPROPSETID_AudioLoopback](/windows-hardware/drivers/audio/kspropsetid-audioloopback)
- [KSATTRIBUTE_AUDIOLOOPBACK_TAPPOINT](ns-ksmedia-ksattribute_audioloopback_tappoint.md)
