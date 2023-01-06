---
UID: NS:acxpin._ACX_JACK_CONFIG
tech.root: audio
title: ACX_JACK_CONFIG
ms.date: 07/28/2022
targetos: Windows
description: The ACX_JACK_CONFIG structure is used to configure an audio jack.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: acxpin.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: ACX_JACK_CONFIG, *PACX_JACK_CONFIG
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxpin.h
api_name:
 - _ACX_JACK_CONFIG
 - PACX_JACK_CONFIG
 - ACX_JACK_CONFIG
f1_keywords:
 - _ACX_JACK_CONFIG
 - acxpin/_ACX_JACK_CONFIG
 - PACX_JACK_CONFIG
 - acxpin/PACX_JACK_CONFIG
 - ACX_JACK_CONFIG
 - acxpin/ACX_JACK_CONFIG
dev_langs:
 - c++
---

## -description

The **ACX_JACK_CONFIG** structure is used to configure an audio jack.

## -struct-fields

### -field Size

The size of all of the data in the **ACX_JACK_CONFIG** structure in bytes.

### -field Id

An identifier associated with the jack. Currently not used, set to AcxJackPropertiesIdDefault.

### -field Flags

A combination of values from the [ACX_JACK_CONFIG_FLAGS](ne-acxpin-acx_jack_config_flags.md) enum that describe the jack.

### -field Callbacks

A pointer to an [ACX_JACK_CALLBACKS](ns-acxpin-acx_jack_callbacks.md) structure that specifies the callback functions for the jack.

### -field Description

An [ACX_JACK_DESCRIPTION](ns-acxpin-acx_jack_description.md) structure that describes the jack, including the connection type, location of the jack, and so on.

## -remarks

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [ACX_JACK_CONFIG_FLAGS](ne-acxpin-acx_jack_config_flags.md)
- [ACX_JACK_CALLBACKS](ns-acxpin-acx_jack_callbacks.md)
- [ACX_JACK_DESCRIPTION](ns-acxpin-acx_jack_description.md)
- [acxpin.h header](index.md)
