---
UID: NS:acxpin._ACX_PIN_CONFIG
tech.root: audio
title: ACX_PIN_CONFIG
ms.date: 09/08/2022
targetos: Windows
description: The ACX_PIN_CONFIG structure is used to configure a pin.
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
req.typenames: ACX_PIN_CONFIG, *PACX_PIN_CONFIG
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxpin.h
api_name:
 - _ACX_PIN_CONFIG
 - PACX_PIN_CONFIG
 - ACX_PIN_CONFIG
f1_keywords:
 - _ACX_PIN_CONFIG
 - acxpin/_ACX_PIN_CONFIG
 - PACX_PIN_CONFIG
 - acxpin/PACX_PIN_CONFIG
 - ACX_PIN_CONFIG
 - acxpin/ACX_PIN_CONFIG
dev_langs:
 - c++
---

## -description

The **ACX_PIN_CONFIG** structure is used to configure a pin.

## -struct-fields

### -field Size

The size of all of the data in the **ACX_PIN_CONFIG** structure in bytes. This field is set by the [ACX_PIN_CONFIG_INIT](nf-acxpin-acx_pin_config_init.md) function.

### -field Flags

A combination of values from the [ACX_PIN_CONFIG_FLAGS](ne-acxpin-acx_pin_config_flags.md) enum that describe the pin.

### -field Id

An identifier associated with the pin.

### -field Type

An [ACX_PIN_TYPE](ne-acxpin-acx_pin_type.md) enum value that specifies the type of the pin.

### -field Communication

An [ACX_PIN_COMMUNICATION](ne-acxpin-acx_pin_communication.md) enum value that specifies the communication type of the pin.

### -field Qualifier

An [ACX_PIN_QUALIFIER](ne-acxpin-acx_pin_qualifier.md) enum value that specifies how the pin is connected in the multi-circuit audio topology.

### -field Category

A GUID value representing the category of the pin.

### -field Name

A GUID value representing the name of the pin.

### -field PinCallbacks

A pointer to an [ACX_PIN_CALLBACKS](nf-acxpin-acx_pin_callbacks_init.md) structure that specifies the callback functions for the pin.

### -field PropertiesCount

Specifies the size of the array pointed to by the *Properties* field.

### -field MethodsCount

Specifies the size of the array pointed to by the *Methods* field.

### -field Properties

A pointer to an array of [ACX_PROPERTY_ITEM](../acxrequest/ns-acxrequest-acx_property_item.md) structures containing pin properties.

### -field Methods

A pointer to an array of [ACX_METHOD_ITEM](../acxrequest/ns-acxrequest-acx_method_item.md) structures containing pin methods.

### -field u

A union used to specify the additional type configuration of the pin.

### -field u.MicrophoneConfig

A pointer to an [ACX_MICROPHONE_CONFIG](ns-acxpin-acx_microphone_config.md) structure associated with the pin.

### -field MaxStreams

Specifies the maximum number of streams supported by the pin.

## -remarks

Instances of the **ACX_PIN_CONFIG** structure must be initialized by calling the [ACX_PIN_CONFIG_INIT](nf-acxpin-acx_pin_config_init.md) function.

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [ACX_PIN_CONFIG_INIT](nf-acxpin-acx_pin_config_init.md)
- [ACX_PIN_CONFIG_FLAGS](ne-acxpin-acx_pin_config_flags.md)
- [ACX_PROPERTY_ITEM](../acxrequest/ns-acxrequest-acx_property_item.md)
- [ACX_METHOD_ITEM](../acxrequest/ns-acxrequest-acx_method_item.md)
- [ACX_PIN_CALLBACKS](nf-acxpin-acx_pin_callbacks_init.md)
- [acxpin.h header](index.md)
