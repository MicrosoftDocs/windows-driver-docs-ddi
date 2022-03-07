---
UID: NS:ntddk.__unnamed_struct_19
tech.root: kernel
title: DEBUG_MEMORY_REQUIREMENTS (ntddk.h)
ms.date: 03/07/2022
targetos: Windows
description: This topic describes the DEBUG_MEMORY_REQUIREMENTS structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntddk.h
req.include-header: Ntddk.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: WIN11_NEXT
req.target-min-winversvr: 
req.target-type: 
req.typenames: DEBUG_MEMORY_REQUIREMENTS, *PDEBUG_MEMORY_REQUIREMENTS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - PDEBUG_MEMORY_REQUIREMENTS
 - DEBUG_MEMORY_REQUIREMENTS
f1_keywords:
 - PDEBUG_MEMORY_REQUIREMENTS
 - ntddk/PDEBUG_MEMORY_REQUIREMENTS
 - DEBUG_MEMORY_REQUIREMENTS
 - ntddk/DEBUG_MEMORY_REQUIREMENTS
dev_langs:
 - c++
helpviewer_keywords:
 - __unnamed_struct_19
---

## -description

This topic describes the **DEBUG_MEMORY_REQUIREMENTS** structure.

## -struct-fields

### -field Start

Defines the **PHYSICAL_ADDRESS** member **Start**.

### -field MaxEnd

Defines the **PHYSICAL_ADDRESS** member **MaxEnd**.

### -field VirtualAddress

Defines the **PVOID** member **VirtualAddress**.

### -field Length

Defines the **ULONG** member **Length**.

### -field Cached

Defines the **BOOLEAN** member **Cached**.

### -field Aligned

Defines the **BOOLEAN** member **Aligned**.

## -remarks

## -see-also
