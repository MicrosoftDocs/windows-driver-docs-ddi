---
UID: NE:acxmanager._ACX_COMPOSITE_TEMPLATE_CONFIG_FLAGS
tech.root: audio
title: ACX_COMPOSITE_TEMPLATE_CONFIG_FLAGS
ms.date: 04/27/2022
targetos: Windows
description: The ACX_COMPOSITE_TEMPLATE_CONFIG_FLAGS enumeration is used to configure the properties of a composite template used by the audio class extension (ACX) manager.
prerelease: true
req.construct-type: enumeration
req.ddi-compliance: 
req.header: acxmanager.h
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
 - acxmanager.h
api_name:
 - _ACX_COMPOSITE_TEMPLATE_CONFIG_FLAGS
 - ACX_COMPOSITE_TEMPLATE_CONFIG_FLAGS
f1_keywords:
 - _ACX_COMPOSITE_TEMPLATE_CONFIG_FLAGS
 - acxmanager/_ACX_COMPOSITE_TEMPLATE_CONFIG_FLAGS
 - ACX_COMPOSITE_TEMPLATE_CONFIG_FLAGS
 - acxmanager/ACX_COMPOSITE_TEMPLATE_CONFIG_FLAGS
dev_langs:
 - c++
---

## -description

The **ACX_COMPOSITE_TEMPLATE_CONFIG_FLAGS** enumeration is used to configure the properties of a composite template used by the audio class extension (ACX) manager.

## -enum-fields

### -field AcxCompositeTemplateConfigNoFlags

Indicates that there are no flags set.

### -field AcxCompositeTemplateConfigPrivate

For internal use only, do not use.

### -field AcxCompositeTemplateConfigSingleton

Indicates that the composite template represents a composite singleton, so it does not repeat in the system.

### -field AcxCompositeTemplateConfigValidFlags

For internal validation, do not use.

## -remarks

### ACX requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum ACX version** | 1.0 |

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxmanager.h header](index.md)

