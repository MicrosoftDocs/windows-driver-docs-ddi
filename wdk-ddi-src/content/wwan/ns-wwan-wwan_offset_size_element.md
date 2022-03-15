---
UID: NS:wwan._WWAN_OFFSET_SIZE_ELEMENT
tech.root: netvista
title: WWAN_OFFSET_SIZE_ELEMENT
ms.date: 01/13/2022
targetos: Windows
description: The WWAN_OFFSET_SIZE_ELEMENT structure contains the size and offset to a data buffer.
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wwan.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: WIN11_NEXT
req.target-min-winversvr: 
req.target-type: 
req.typenames: WWAN_OFFSET_SIZE_ELEMENT, *PWWAN_OFFSET_SIZE_ELEMENT
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_OFFSET_SIZE_ELEMENT
 - PWWAN_OFFSET_SIZE_ELEMENT
 - WWAN_OFFSET_SIZE_ELEMENT
f1_keywords:
 - _WWAN_OFFSET_SIZE_ELEMENT
 - wwan/_WWAN_OFFSET_SIZE_ELEMENT
 - PWWAN_OFFSET_SIZE_ELEMENT
 - wwan/PWWAN_OFFSET_SIZE_ELEMENT
 - WWAN_OFFSET_SIZE_ELEMENT
 - wwan/WWAN_OFFSET_SIZE_ELEMENT
dev_langs:
 - c++
helpviewer_keywords:
 - _WWAN_OFFSET_SIZE_ELEMENT
---

## -description

The **WWAN_OFFSET_SIZE_ELEMENT** structure contains the size and offset to a data buffer.

## -struct-fields

### -field Offset

The first 4 bytes of **WWAN_OFFSET_SIZE_ELEMENT** are the offset to the data buffer, calculated from the beginning of the structure that contains **WWAN_OFFSET_SIZE_ELEMENT**.

### -field Size

The second 4 bytes of **WWAN_OFFSET_SIZE_ELEMENT** are the size of the raw data of the data buffer, in bytes.

## -remarks

## -see-also

