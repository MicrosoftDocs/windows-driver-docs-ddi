---
UID: NF:acxelements.ACX_AUDIOENGINE_CONFIG_INIT_ID
tech.root: audio 
title: ACX_AUDIOENGINE_CONFIG_INIT_ID
ms.date: 10/01/2021
targetos: Windows
description: As the ACX_AUDIOENGINE_CONFIG_INIT_ID provides the same functionality as ACX_AUDIOENGINE_CONFIG_INIT, the use of ACX_AUDIOENGINE_CONFIG_INIT is recommended.
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
 - ACX_AUDIOENGINE_CONFIG_INIT_ID
f1_keywords:
 - ACX_AUDIOENGINE_CONFIG_INIT_ID
 - acxelements/ACX_AUDIOENGINE_CONFIG_INIT_ID
dev_langs:
 - c++
---

## -description

At this time, the ACX_AUDIOENGINE_CONFIG_INIT_ID can only take AcxElementIdDefault as input for the element ID, which is the same as using ACX_AUDIOENGINE_CONFIG_INIT. Because of this, [ACX_AUDIOENGINE_CONFIG_INIT](nf-acxelements-acx_audioengine_config_init.md) is recommended.

## -parameters

### -param Config

An initialized config structure.

### -param Id

Set only to AcxElementIdDefault that is defined in the AcxElements header.

## -remarks

As the ACX_AUDIOENGINE_CONFIG_INIT_ID provides the same functionality as [ACX_AUDIOENGINE_CONFIG_INIT](nf-acxelements-acx_audioengine_config_init.md), the use of ACX_AUDIOENGINE_CONFIG_INIT is recommended.

## -see-also

[acxelements.h header](index.md)

