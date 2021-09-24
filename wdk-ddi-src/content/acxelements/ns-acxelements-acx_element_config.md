---
UID: NS:acxelements._ACX_ELEMENT_CONFIG
tech.root: audio 
title: ACX_ELEMENT_CONFIG
ms.date: 09/03/2021
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

The ACX_ELEMENT_CONFIG structure is used to define the audio element configuration. 

## -struct-fields

### -field Size

TBD - The length, in bytes, of this structure.

### -field Id

A number that represents the ID of the TBD.

### -field Type

TBD TBD

The KSNODETYPE, for example KSNODETYPE_AUDIO_ENGINE or KSNODETYPE_AUDIO_KEYWORDDETECTOR. For more information, see [Audio Topology Nodes](/windows-hardware/drivers/audio/audio-topology-nodes).

TBD TBD


### -field Name

A pointer to a GUID that represents the name of the TBD that will be used for TBD.

### -field Flags

Audio element configuration flags defined by the [ACX_ELEMENT_CONFIG_FLAGS enum](ne-acxelements-acx_element_config_flags.md). 

TBD - No flag bits are currently defined. Set this member to zero - AcxAudioElementConfigNoFlags

### -field PropertiesCount

TBD - The number of properties. This is a TBD zero / one based count.

### -field MethodsCount

TBD - The number of methods. This is a TBD zero / one based count.

### -field Properties

TBD - An ACX_PROPERTY_ITEM structure that defines a set of TBD TBD and is used to TBD. 

TODO: DocsTeam add link to this structure in AcxRequest header when available.

### -field Methods

And ACX_METHOD_ITEM  structure that defines the methods for this audio element configuration. 

TODO: DocsTeam need to link this struct - in AcxRequest.h

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

## -see-also

[acxelements.h header](index.md)

