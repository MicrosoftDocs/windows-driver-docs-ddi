---
UID: NF:acxelements.ACX_VOLUME_CONFIG_INIT_ID
tech.root: audio 
title: ACX_VOLUME_CONFIG_INIT_ID
ms.date: 09/20/2021
targetos: Windows
description: TBD - The ACX_VOLUME_CONFIG_INIT_ID function initializes an ACX_VOLUME_CONFIG structure.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxelements.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxelements.h
api_name:
 - ACX_VOLUME_CONFIG_INIT_ID
f1_keywords:
 - ACX_VOLUME_CONFIG_INIT_ID
 - acxelements/ACX_VOLUME_CONFIG_INIT_ID
dev_langs:
 - c++
---

## -description

In the current ACX implementation, The ACX_VOLUME_CONFIG_INIT_ID provides the same functionality as [ACX_VOLUME_CONFIG_INIT](nf-acxelements-acx_volume_config_init.md). The ACX_VOLUME_CONFIG_INIT function initializes an [ACX_VOLUME_CONFIG](ns-acxelements-acx_volume_config.md) structure.

## -parameters

### -param Config

An [ACX_VOLUME_CONFIG](ns-acxelements-acx_volume_config.md) structure.

### -param Id

Set only to AcxElementIdDefault that is defined in the AcxElements header.

## -remarks

As the The ACX_VOLUME_CONFIG_INIT_ID provides the same functionality as [ACX_VOLUME_CONFIG_INIT](nf-acxelements-acx_volume_config_init.md), the use of ACX_VOLUME_CONFIG_INIT is recommended.

## -see-also

[acxelements.h header](index.md)

