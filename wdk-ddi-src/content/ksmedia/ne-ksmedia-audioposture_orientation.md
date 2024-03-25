---
UID: NE:ksmedia.AUDIOPOSTURE_ORIENTATION
title: AUDIOPOSTURE_ORIENTATION
ms.date: 08/11/2021
ms.topic: language-reference
targetos: Windows
description: The rotation values indicates the orientation of screen in sync with the UI. The UI may be locked to a particular orientation regardless of the physical sensor.
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
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - AUDIOPOSTURE_ORIENTATION
f1_keywords:
 - ksmedia/AUDIOPOSTURE_ORIENTATION
dev_langs:
 - c++
---

## -description

The rotation values indicates the orientation of screen in sync with the UI. The UI may be locked to a particular orientation regardless of the physical sensor. This indicates the UI/shell orientation on the particular screen.

## -enum-fields

### -field AUDIOPOSTURE_ORIENTATION_NOTROTATED

The panel is not rotated. (Default)

### -field AUDIOPOSTURE_ORIENTATION_ROTATED90DEGREESCOUNTERCLOCKWISE

The panel is rotated 90 degrees counter-clockwise.

### -field AUDIOPOSTURE_ORIENTATION_ROTATED180DEGREESCOUNTERCLOCKWISE

The panel is rotated 180 degrees counter-clockwise.

### -field AUDIOPOSTURE_ORIENTATION_ROTATED270DEGREESCOUNTERCLOCKWISE

The panel is rotated 270 degrees counter-clockwise.

## -remarks

## -see-also

[Supporting Audio Posture](/windows-hardware/drivers/audio/supporting-audio-posture)

