---
UID: NE:acxelements._ACX_VOLUME_CURVE_TYPE
tech.root: audio 
title: ACX_VOLUME_CURVE_TYPE
ms.date: 04/29/2022
targetos: Windows
description: The ACX_VOLUME_CURVE_TYPE enumeration defines constants that specify a curve algorithm to be applied to set a volume level.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: acxelements.h
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
 - acxelements.h
api_name:
 - _ACX_VOLUME_CURVE_TYPE
 - PACX_VOLUME_CURVE_TYPE
 - ACX_VOLUME_CURVE_TYPE
f1_keywords:
 - _ACX_VOLUME_CURVE_TYPE
 - acxelements/_ACX_VOLUME_CURVE_TYPE
 - PACX_VOLUME_CURVE_TYPE
 - acxelements/PACX_VOLUME_CURVE_TYPE
 - ACX_VOLUME_CURVE_TYPE
 - acxelements/ACX_VOLUME_CURVE_TYPE
dev_langs:
 - c++
---

## -description

The **ACX_VOLUME_CURVE_TYPE** enumeration defines constants that specify a curve algorithm to be applied to set a volume level.

## -enum-fields

### -field AcxVolumeCurveTypeNone

Indicates that no curve algorithm will be applied. When this curve is specified, the duration of the curve specified must be equal to 0.

### -field AcxVolumeCurveTypeFade

Indicates that the algorithm that is applied to the volume setting must follow the curve shown in the diagram in [AUDIO_CURVE_TYPE enumeration](/windows-hardware/drivers/ddi/ksmedia/ne-ksmedia-audio_curve_type).

## -remarks


### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxelements.h header](index.md)
