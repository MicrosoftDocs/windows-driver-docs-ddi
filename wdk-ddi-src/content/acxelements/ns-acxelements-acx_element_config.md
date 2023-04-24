---
UID: NS:acxelements._ACX_ELEMENT_CONFIG
tech.root: audio 
title: ACX_ELEMENT_CONFIG
ms.date: 08/01/2022
targetos: Windows
description: The ACX_ELEMENT_CONFIG structure is used to define the audio element configuration.
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
req.typenames: ACX_ELEMENT_CONFIG, *PACX_ELEMENT_CONFIG
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxelements.h
api_name:
 - _ACX_ELEMENT_CONFIG
 - PACX_ELEMENT_CONFIG
 - ACX_ELEMENT_CONFIG
f1_keywords:
 - _ACX_ELEMENT_CONFIG
 - acxelements/_ACX_ELEMENT_CONFIG
 - PACX_ELEMENT_CONFIG
 - acxelements/PACX_ELEMENT_CONFIG
 - ACX_ELEMENT_CONFIG
 - acxelements/ACX_ELEMENT_CONFIG
dev_langs:
 - c++
---

## -description

The **ACX_ELEMENT_CONFIG** structure is used to define the acx element configuration.

## -struct-fields

### -field Size

The length, in bytes, of this structure.

### -field Id

A number that represents the element ID.

### -field Type

The KSNODETYPE, for example KSNODETYPE_AUDIO_ENGINE or KSNODETYPE_AUDIO_KEYWORDDETECTOR. For more information, see [Audio Topology Nodes](/windows-hardware/drivers/audio/audio-topology-nodes).

### -field Name

A pointer to a GUID that represents the name of the element. Can be used for debugging and will default to GUID_NULL if not provided.

### -field Flags

Acx element configuration flags defined by the [ACX_ELEMENT_CONFIG_FLAGS enum](ne-acxelements-acx_element_config_flags.md).

No flag bits are currently defined. Set this member to zero - AcxAudioElementConfigNoFlags

### -field PropertiesCount

The number of properties. This is a one based count.

### -field MethodsCount

The number of methods. This is a one based count.

### -field Properties

An [ACX_PROPERTY_ITEM structure](/windows-hardware/drivers/ddi/acxrequest/ns-acxrequest-acx_property_item) that defines the properties for this acx element configuration.

### -field Methods

An [ACX_METHOD_ITEM](/windows-hardware/drivers/ddi/acxrequest/ns-acxrequest-acx_method_item) structure that defines the methods for this acx element configuration.

## -remarks

### Example

Example usage is shown below.

```cpp
    WDF_OBJECT_ATTRIBUTES           attributes;
    ACX_ELEMENT_CONFIG              elementCfg;
    CODEC_ELEMENT_CONTEXT *         elementCtx;

    ACX_ELEMENT_CONFIG_INIT(&elementCfg);
    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&attributes, CODEC_ELEMENT_CONTEXT);
    attributes.ParentObject = Circuit;
    
    status = AcxElementCreate(Circuit, &attributes, &elementCfg, Element);
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxelements.h header\]\(index.md\)
