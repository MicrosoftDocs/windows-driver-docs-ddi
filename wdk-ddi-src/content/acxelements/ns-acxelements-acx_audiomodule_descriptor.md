---
UID: NS:acxelements._ACX_AUDIOMODULE_DESCRIPTOR
tech.root: audio 
title: ACX_AUDIOMODULE_DESCRIPTOR
ms.date: 04/29/2022
targetos: Windows
description: The ACX_AUDIOMODULE_DESCRIPTOR is used to define an audio module descriptor structure.
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: acxelements.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: ACX_AUDIOMODULE_DESCRIPTOR, *PACX_AUDIOMODULE_DESCRIPTOR
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxelements.h
api_name:
 - _ACX_AUDIOMODULE_DESCRIPTOR
 - PACX_AUDIOMODULE_DESCRIPTOR
 - ACX_AUDIOMODULE_DESCRIPTOR
f1_keywords:
 - _ACX_AUDIOMODULE_DESCRIPTOR
 - acxelements/_ACX_AUDIOMODULE_DESCRIPTOR
 - PACX_AUDIOMODULE_DESCRIPTOR
 - acxelements/PACX_AUDIOMODULE_DESCRIPTOR
 - ACX_AUDIOMODULE_DESCRIPTOR
 - acxelements/ACX_AUDIOMODULE_DESCRIPTOR
dev_langs:
 - c++
---

## -description

The **ACX_AUDIOMODULE_DESCRIPTOR** is used to define an audio module descriptor structure.

## -struct-fields

### -field ClassId

The GUID identifier of the module, which is defined by the audio device module owner.

### -field InstanceId

The identifier, defined by the driver developer, that disambiguates between multiple instances of the same module class in the driver topology.

### -field VersionMajor

The major version of the audio module.

### -field VersionMinor

The minor version of the audio module.

### -field Name

The friendly name of the audio device module for display in UI. The buffer size is ACX_AUDIOMODULE_MAX_NAME_CCH_SIZE including the NULL terminator.

## -remarks

### Example

Sample Pending

Example usage is shown below.

```cpp

```

## -see-also

- [acxelements.h header](index.md)
