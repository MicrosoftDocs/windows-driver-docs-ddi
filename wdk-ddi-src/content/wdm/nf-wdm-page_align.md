---
UID: NF:wdm.PAGE_ALIGN
tech.root: 
title: PAGE_ALIGN
ms.date: 07/16/2021
targetos: Windows
description: 
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
 - wdm.h
api_name:
 - PAGE_ALIGN
f1_keywords:
 - PAGE_ALIGN
 - wdm/PAGE_ALIGN
dev_langs:
 - c++
---

## -description

The **PAGE_ALIGN** macro returns a page-aligned virtual address for a given virtual address.

## -parameters

### -param Va

[in]
Pointer to the virtual address.

## -remarks

**PAGE_ALIGN** returns a pointer to the page-aligned virtual address.

Available starting with Windows 2000.
