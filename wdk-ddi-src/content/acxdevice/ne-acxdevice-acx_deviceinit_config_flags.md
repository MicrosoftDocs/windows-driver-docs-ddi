---
UID: NE:acxdevice._ACX_DEVICEINIT_CONFIG_FLAGS
tech.root: audio
title: ACX_DEVICEINIT_CONFIG_FLAGS
ms.date: 01/31/2022
targetos: Windows
description: The ACX_DEVICEINIT_CONFIG_FLAGS enum defines values used to initialize the audio class extension.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: acxdevice.h
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
 - acxdevice.h
api_name:
 - _ACX_DEVICEINIT_CONFIG_FLAGS
 - ACX_DEVICEINIT_CONFIG_FLAGS
f1_keywords:
 - _ACX_DEVICEINIT_CONFIG_FLAGS
 - acxdevice/_ACX_DEVICEINIT_CONFIG_FLAGS
 - ACX_DEVICEINIT_CONFIG_FLAGS
 - acxdevice/ACX_DEVICEINIT_CONFIG_FLAGS
dev_langs:
 - c++
---

## -description

The **ACX_DEVICEINIT_CONFIG_FLAGS** enum defines values used to initialize the audio class extension.

## -enum-fields

### -field AcxDeviceInitConfigNoFlags

Indicates that no flags are set.

### -field AcxDeviceInitConfigRawDevice

Indicates to Plug and Play that the device is a raw audio device.

### -field AcxDeviceInitConfigValidFlags

For internal validation, do not use.

## -remarks

### ACX requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum ACX version** | 1.0 |

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

* [acxdevice.h header](index.md)

