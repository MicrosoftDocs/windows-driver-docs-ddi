---
UID: NS:wdm.__unnamed_struct_0
tech.root: kernel
title: SET_POWER_SETTING_VALUE (wdm.h)
ms.date: 03/11/2022
targetos: Windows
description: This topic describes the SET_POWER_SETTING_VALUE structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.include-header: Wdm.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: WIN11_NEXT
req.target-min-winversvr: 
req.target-type: 
req.typenames: SET_POWER_SETTING_VALUE, *PSET_POWER_SETTING_VALUE
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - PSET_POWER_SETTING_VALUE
 - SET_POWER_SETTING_VALUE
f1_keywords:
 - PSET_POWER_SETTING_VALUE
 - wdm/PSET_POWER_SETTING_VALUE
 - SET_POWER_SETTING_VALUE
 - wdm/SET_POWER_SETTING_VALUE
dev_langs:
 - c++
helpviewer_keywords:
 - __unnamed_struct_0
---

## -description

This topic describes the **SET_POWER_SETTING_VALUE** structure.

## -struct-fields

### -field Version

Version of this structure.  Currently should be set to **POWER_SETTING_VALUE_VERSION**.

### -field Guid

GUID representing the power setting being applied.

### -field PowerCondition

The power state this setting should be applied to, for example, AC, DC, thermal, and so on.

### -field DataLength

Length in bytes of the **Data** member.

### -field Data

Contains the setting value.

## -remarks

## -see-also
