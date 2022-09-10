---
UID: NS:wdm._EXTENDED_CREATE_INFORMATION_32
tech.root: kernel
title: EXTENDED_CREATE_INFORMATION_32 (wdm.h)
ms.date: 08/02/2022
targetos: Windows
description: Describes the 32-bit version of the EXTENDED_CREATE_INFORMATION structure.
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
req.target-min-winverclnt: Windows 11, version 22H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: EXTENDED_CREATE_INFORMATION_32, *PEXTENDED_CREATE_INFORMATION_32
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _EXTENDED_CREATE_INFORMATION_32
 - PEXTENDED_CREATE_INFORMATION_32
 - EXTENDED_CREATE_INFORMATION_32
f1_keywords:
 - _EXTENDED_CREATE_INFORMATION_32
 - wdm/_EXTENDED_CREATE_INFORMATION_32
 - PEXTENDED_CREATE_INFORMATION_32
 - wdm/PEXTENDED_CREATE_INFORMATION_32
 - EXTENDED_CREATE_INFORMATION_32
 - wdm/EXTENDED_CREATE_INFORMATION_32
dev_langs:
 - c++
helpviewer_keywords:
 - _EXTENDED_CREATE_INFORMATION_32
---

## -description

Describes the 32-bit version of the [**EXTENDED_CREATE_INFORMATION**](ns-wdm-extended_create_information.md) structure.

## -struct-fields

### -field ExtendedCreateFlags

Defines the **LONGLONG** member **ExtendedCreateFlags**.

### -field EaBuffer

Defines the void* **POINTER_32** member **EaBuffer**.

### -field EaLength

Defines the **ULONG** member **EaLength**.

## -remarks

## -see-also
