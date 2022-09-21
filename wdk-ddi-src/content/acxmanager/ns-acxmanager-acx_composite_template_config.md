---
UID: NS:acxmanager._ACX_COMPOSITE_TEMPLATE_CONFIG
tech.root: audio
title: ACX_COMPOSITE_TEMPLATE_CONFIG
ms.date: 04/27/2022
targetos: Windows
description: The ACX_COMPOSITE_TEMPLATE_CONFIG structure is used to configure a new ACX composite template object.
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: acxmanager.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: ACX_COMPOSITE_TEMPLATE_CONFIG, *PACX_COMPOSITE_TEMPLATE_CONFIG
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxmanager.h
api_name:
 - _ACX_COMPOSITE_TEMPLATE_CONFIG
 - PACX_COMPOSITE_TEMPLATE_CONFIG
 - ACX_COMPOSITE_TEMPLATE_CONFIG
f1_keywords:
 - _ACX_COMPOSITE_TEMPLATE_CONFIG
 - acxmanager/_ACX_COMPOSITE_TEMPLATE_CONFIG
 - PACX_COMPOSITE_TEMPLATE_CONFIG
 - acxmanager/PACX_COMPOSITE_TEMPLATE_CONFIG
 - ACX_COMPOSITE_TEMPLATE_CONFIG
 - acxmanager/ACX_COMPOSITE_TEMPLATE_CONFIG
dev_langs:
 - c++
---

## -description

The **ACX_COMPOSITE_TEMPLATE_CONFIG** structure is used to configure a new ACX composite template object.

## -struct-fields

### -field Size

The size of all of the data in the **ACX_COMPOSITE_TEMPLATE_CONFIG** structure in bytes. This field is set by the [ACX_COMPOSITE_TEMPLATE_CONFIG_INIT](nf-acxmanager-acx_composite_template_config_init.md) function.

### -field Flags

A combination of values from the [ACX_COMPOSITE_TEMPLATE_CONFIG_FLAGS](ne-acxmanager-acx_composite_template_config_flags.md) enum that describe the composite template.

### -field Properties

An optional **ACXOBJECTBAG** of composite template properties. Only for singleton composites.

## -remarks

### ACX requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum ACX version** | 1.0 |

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [ACX_COMPOSITE_TEMPLATE_CONFIG_INIT](nf-acxmanager-acx_composite_template_config_init.md)
- [ACX_COMPOSITE_TEMPLATE_CONFIG_FLAGS](ne-acxmanager-acx_composite_template_config_flags.md)
- [acxmanager.h header](index.md)

