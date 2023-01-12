---
UID: NE:acxpin._ACX_JACK_GEO_LOCATION
tech.root: audio
title: ACX_JACK_GEO_LOCATION
ms.date: 03/25/2022
targetos: Windows
description: The ACX_JACK_GEO_LOCATION enumeration is used by the ACX_JACK_DESCRIPTION structure to help describe the geometric location of an audio jack.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: acxpin.h
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
 - acxpin.h
api_name:
 - _ACX_JACK_GEO_LOCATION
 - PACX_JACK_GEO_LOCATION
 - ACX_JACK_GEO_LOCATION
f1_keywords:
 - _ACX_JACK_GEO_LOCATION
 - acxpin/_ACX_JACK_GEO_LOCATION
 - PACX_JACK_GEO_LOCATION
 - acxpin/PACX_JACK_GEO_LOCATION
 - ACX_JACK_GEO_LOCATION
 - acxpin/ACX_JACK_GEO_LOCATION
dev_langs:
 - c++
---

## -description

The **ACX_JACK_GEO_LOCATION** enumeration is used by the [ACX_JACK_DESCRIPTION](ns-acxpin-acx_jack_description.md) structure to help describe the geometric location of an audio jack.

## -enum-fields

### -field AcxGeoLocRear

Indicates that the jack is located on the rear of the system.

### -field AcxGeoLocFront

Indicates that the jack is located on the front of the system.

### -field AcxGeoLocLeft

Indicates that the jack is located on the left side of the system.

### -field AcxGeoLocRight

Indicates that the jack is located on the right side of the system.

### -field AcxGeoLocTop

Indicates that the jack is located on the top of the system.

### -field AcxGeoLocBottom

Indicates that the jack is located on the bottom of the system.

### -field AcxGeoLocRearPanel

Indicates that the jack is located on the rear panel of the system.

### -field AcxGeoLocRiser

Indicates that the jack is located on a riser card.

### -field AcxGeoLocInsideMobileLid

Indicates that the jack is located on the inside lid of a mobile computer.

### -field AcxGeoLocDrivebay

Indicates that the jack is located in a drive bay.

### -field AcxGeoLocHDMI

Indicates that the jack is an HDMI connector.

### -field AcxGeoLocOutsideMobileLid

Indicates that the jack is located on the outside lid of a mobile computer.

### -field AcxGeoLocATAPI

Indicates that the jack is located internally, on an ATAPI connector.

### -field AcxGeoLocNotApplicable

Indicates that the jack location is not applicable.

### -field AcxGeoLocReserved6

This value is reserved.

### -field AcxJackGeoLocationMaximum

For internal validation, do not use.

## -remarks

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [ACX_JACK_GEN_LOCATION](ne-acxpin-acx_jack_gen_location.md)
- [acxpin.h header\]\(index.md\)
