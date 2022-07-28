---
UID: NS:acxpin._ACX_JACK_CALLBACKS
tech.root: audio
title: ACX_JACK_CALLBACKS
ms.date: 02/24/2022
targetos: Windows
description: The ACX_JACK_CALLBACKS structure specifies audio jack event callback functions.
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
req.typenames: ACX_JACK_CALLBACKS, *PACX_JACK_CALLBACKS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxpin.h
api_name:
 - _ACX_JACK_CALLBACKS
 - PACX_JACK_CALLBACKS
 - ACX_JACK_CALLBACKS
f1_keywords:
 - _ACX_JACK_CALLBACKS
 - acxpin/_ACX_JACK_CALLBACKS
 - PACX_JACK_CALLBACKS
 - acxpin/PACX_JACK_CALLBACKS
 - ACX_JACK_CALLBACKS
 - acxpin/ACX_JACK_CALLBACKS
dev_langs:
 - c++
---

## -description

The **ACX_JACK_CALLBACKS** structure specifies audio jack event callback functions.

## -struct-fields

### -field Size

The size of all of the data in the **ACX_JACK_CALLBACKS** structure in bytes.

### -field EvtAcxJackRetrievePresenceState

A pointer to the callback function that determines if the jack is present on the system.

## -remarks

## -see-also

- [acxpin.h header](index.md)

READY2GO
