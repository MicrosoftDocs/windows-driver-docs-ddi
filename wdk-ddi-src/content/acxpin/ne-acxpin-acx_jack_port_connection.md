---
UID: NE:acxpin._ACX_JACK_PORT_CONNECTION
tech.root: audio
title: ACX_JACK_PORT_CONNECTION
ms.date: 03/25/2022
targetos: Windows
description: The ACX_JACK_PORT_CONNECTION enumeration is used by the ACX_JACK_DESCRIPTION structure and specifies the type of port represented by the jack.
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
 - _ACX_JACK_PORT_CONNECTION
 - PACX_JACK_PORT_CONNECTION
 - ACX_JACK_PORT_CONNECTION
f1_keywords:
 - _ACX_JACK_PORT_CONNECTION
 - acxpin/_ACX_JACK_PORT_CONNECTION
 - PACX_JACK_PORT_CONNECTION
 - acxpin/PACX_JACK_PORT_CONNECTION
 - ACX_JACK_PORT_CONNECTION
 - acxpin/ACX_JACK_PORT_CONNECTION
dev_langs:
 - c++
---

## -description

The **ACX_JACK_PORT_CONNECTION** enumeration is used by the [ACX_JACK_DESCRIPTION](ns-acxpin-acx_jack_description.md) structure and specifies the type of port represented by the jack.

## -enum-fields

### -field AcxPortConnJack

Indicates that the port type is a physical jack.

### -field AcxPortConnIntegratedDevice

Indicates that the port type is a slot for an integrated device.

### -field AcxPortConnBothIntegratedAndJack

Indicates that the port type is both a jack and a slot for an integrated device.

### -field AcxPortConnUnknown

Indicates that the port type is unknown.

## -remarks

## -see-also

- [acxpin.h header](index.md)


