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

The ClassId that is used to identify the class.

TBD - assuming this usage is likePcNewPort.

Specifies the class GUID, which is passed by reference. This parameter is used only if the function creates objects of multiple classes. Otherwise, it is set to NULL.

### -field InstanceId

The Instance Id for this audio module.

### -field VersionMajor

The major version.

### -field VersionMinor

The minor version.

### -field Name

A pointer to a GUID that represents the name of the element. Can be used for debugging and will default to GUID_NULL if not provided.

## -remarks

### Example

Sample Pending

Example usage is shown below.

```cpp

```

## -see-also

- [acxelements.h header](index.md)

TBD - Please review this topic