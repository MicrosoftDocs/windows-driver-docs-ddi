---
UID: NE:acxpin._ACX_PIN_CONFIG_FLAGS
tech.root: audio
title: ACX_PIN_CONFIG_FLAGS
ms.date: 09/09/2022
targetos: Windows
description: The ACX_PIN_CONFIG_FLAGS enumeration specifies pin configuration settings used in the ACX_PIN_CONFIG structure.
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
 - _ACX_PIN_CONFIG_FLAGS
 - ACX_PIN_CONFIG_FLAGS
f1_keywords:
 - _ACX_PIN_CONFIG_FLAGS
 - acxpin/_ACX_PIN_CONFIG_FLAGS
 - ACX_PIN_CONFIG_FLAGS
 - acxpin/ACX_PIN_CONFIG_FLAGS
dev_langs:
 - c++
---

## -description

The **ACX_PIN_CONFIG_FLAGS** enumeration specifies pin configuration settings used in the ACX_PIN_CONFIG structure.

## -enum-fields

### -field AcxPinConfigNoFlags

Indicates that there are no flags set.

### -field AcxPinConfigMicrophoneConfigSpecified

Indicates that an [ACX_MICROPHONE_CONFIG](./ns-acxpin-acx_microphone_config.md) structure is available for this pin.

### -field AcxPinConfigNoDefaultDataFormatLists

Indicates that there are no default data format lists for this pin.

### -field AcxPinConfigValidFlags

For internal validation, do not use.

## -remarks

### ACX requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum ACX version** | 1.0 |

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [ACX_MICROPHONE_CONFIG](./ns-acxpin-acx_microphone_config.md)
- [ACX_PIN_CONFIG](./ns-acxpin-acx_pin_config.md)
- [EVT_ACX_PIN_DATAFORMAT_CHANGE_NOTIFICATION](./nc-acxpin-evt_acx_pin_dataformat_change_notification.md)
- [acxpin.h header](./index.md)
