---
UID: NS:bdamedia.RATING_SYSTEM
tech.root: stream
title: RATING_SYSTEM
ms.date: 08/16/2023
targetos: Windows
description: This topic describes the RATING_SYSTEM structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: bdamedia.h
req.include-header: Bdamedia.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: RATING_SYSTEM, *LPRATING_SYSTEM
typedef_isUnnamed: true
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - bdamedia.h
api_name:
 - RATING_SYSTEM
 - LPRATING_SYSTEM
f1_keywords:
 - RATING_SYSTEM
 - bdamedia/RATING_SYSTEM
 - LPRATING_SYSTEM
 - bdamedia/LPRATING_SYSTEM
dev_langs:
 - c++
helpviewer_keywords:
 - RATING_SYSTEM
---

## -description

This topic describes the **RATING_SYSTEM** structure.

## -struct-fields

### -field rating_system_id

Defines the **GUID** member **rating_system_id**.

### -field rating_system_is_age_type

Defines the **BYTE** member **rating_system_is_age_type**.

### -field reserved

Reserved for future use.

### -field country_code[MAX_COUNTRY_CODE_STRING]

Defines the **BYTE** member **country_code**.

### -field rating_attribute_count

Defines the **DWORD** member **rating_attribute_count**.

### -field lpratingattrib

Defines the **RATING_ATTRIBUTE** member **lpratingattrib**.

## -remarks

## -see-also
