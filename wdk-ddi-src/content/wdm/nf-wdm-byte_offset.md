---
UID: NF:wdm.BYTE_OFFSET
tech.root: 
title: BYTE_OFFSET
ms.date: 07/16/2021
targetos: Windows
description: "Learn more about: BYTE_OFFSET"
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: Any level
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 2000
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
 - wdm.h
api_name:
 - BYTE_OFFSET
f1_keywords:
 - BYTE_OFFSET
 - wdm/BYTE_OFFSET
dev_langs:
 - c++
---

## -description

The **BYTE_OFFSET** macro takes a virtual address and returns the byte offset of that address within the page.

## -parameters

### -param Va

[in]
Pointer to the virtual address.

## -remarks

**BYTE_OFFSET** returns the offset portion of the virtual address.

