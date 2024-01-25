---
UID: NE:ksmedia.tagAUDIOLOOPBACK_TAPPOINT_TYPE
tech.root: audio
title: AUDIOLOOPBACK_TAPPOINT_TYPE
ms.date: 01/25/2024
targetos: Windows
description: The AUDIOLOOPBACK_TAPPOINT_TYPE enum contains the  pre and post tap point definitions.
prerelease: true
req.construct-type: enumeration
req.ddi-compliance: 
req.header: ksmedia.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
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

## -description

The AUDIOLOOPBACK_TAPPOINT_TYPE enum contains the  pre and post tap point definitions. It is available starting in Windows 11 23H2.

## -enum-fields

### -field AUDIOLOOPBACK_TAPPOINT_PREVOLUMEMUTE

The loopback stream tap point is returned before applying endpoint volume and mute.

### -field AUDIOLOOPBACK_TAPPOINT_POSTVOLUMEMUTE

The loopback stream tap point is after applying endpoint volume and mute.

## -remarks

The enum is used by [KSPROPERTY_AUDIOLOOPBACK](/windows-hardware/drivers/audio/ksproperty-audioloopback) in the [KSPROPSETID_AudioLoopback](/windows-hardware/drivers/audio/kspropsetid-audioloopback) property set to indicate if the loopback tap point is pre or post volume and mute.

## -see-also

[KSPROPERTY_AUDIOLOOPBACK](/windows-hardware/drivers/audio/ksproperty-audioloopback)

[KSPROPSETID_AudioLoopback](/windows-hardware/drivers/audio/kspropsetid-audioloopback)
