---
UID: NE:acxpin._ACX_JACK_GEN_LOCATION
tech.root: audio
title: ACX_JACK_GEN_LOCATION
ms.date: 03/25/2022
targetos: Windows
description: The ACX_JACK_GEN_LOCATION enumeration is used by the ACX_JACK_DESCRIPTION structure to help describe the general location of an audio jack within a system.
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
 - _ACX_JACK_GEN_LOCATION
 - PACX_JACK_GEN_LOCATION
 - ACX_JACK_GEN_LOCATION
f1_keywords:
 - _ACX_JACK_GEN_LOCATION
 - acxpin/_ACX_JACK_GEN_LOCATION
 - PACX_JACK_GEN_LOCATION
 - acxpin/PACX_JACK_GEN_LOCATION
 - ACX_JACK_GEN_LOCATION
 - acxpin/ACX_JACK_GEN_LOCATION
dev_langs:
 - c++
---

## -description

The **ACX_JACK_GEN_LOCATION** enumeration is used by the [ACX_JACK_DESCRIPTION](ns-acxpin-acx_jack_description.md) structure to help describe the general location of an audio jack within a system.

## -enum-fields

### -field AcxGenLocPrimaryBox

Indicates that the jack is located on the primary chassis of the system.

### -field AcxGenLocInternal

Indicates that the jack is located inside the primary chassis in the system.

### -field AcxGenLocSeparate

Indicates that the jack is located on a separate chassis from the primary box.

### -field AcxGenLocOther

Indicates that the jack is located somewhere other than the locations defined by this enum.

### -field AcxJackGenLocationMaximum

For internal validation, do not use.

## -remarks

## -see-also

- [ACX_JACK_GEO_LOCATION](ne-acxpin-acx_jack_geo_location.md)
- [acxpin.h header](index.md)
 

