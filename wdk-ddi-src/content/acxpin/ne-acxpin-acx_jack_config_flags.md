---
UID: NE:acxpin._ACX_JACK_CONFIG_FLAGS
tech.root: audio
title: ACX_JACK_CONFIG_FLAGS
ms.date: 03/25/2022
targetos: Windows
description: The ACX_JACK_CONFIG_FLAGS enumeration is used to describe the properties of a physical jack to an audio class extension (ACX).
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
 - _ACX_JACK_CONFIG_FLAGS
 - ACX_JACK_CONFIG_FLAGS
f1_keywords:
 - _ACX_JACK_CONFIG_FLAGS
 - acxpin/_ACX_JACK_CONFIG_FLAGS
 - ACX_JACK_CONFIG_FLAGS
 - acxpin/ACX_JACK_CONFIG_FLAGS
dev_langs:
 - c++
---

## -description

The **ACX_JACK_CONFIG_FLAGS** enumeration is used to describe the properties of a physical jack to an audio class extension (ACX).

## -enum-fields

### -field AcxJackConfigNoFlags

Indicates that there are no flags set.

### -field AcxJackConfigJackDetection

Indicates if the audio hardware can detect whether a device is plugged in.

### -field AcxJackConfigValidFlags

For internal validation, do not use.

## -remarks

### ACX requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum ACX version** | 1.0 |

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxpin.h header](index.md)


