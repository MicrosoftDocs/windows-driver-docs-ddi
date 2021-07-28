---
UID: NF:wdm.ROUND_TO_PAGES
tech.root: 
title: ROUND_TO_PAGES
ms.date: 07/16/2021
targetos: Windows
description: "Learn more about: ROUND_TO_PAGES"
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
 - ROUND_TO_PAGES
f1_keywords:
 - ROUND_TO_PAGES
 - wdm/ROUND_TO_PAGES
dev_langs:
 - c++
---

## -description

The **ROUND_TO_PAGES** macro takes a size in bytes and rounds it up to the next full page.

## -parameters

### -param Size

[in]
Specifies the size in bytes to round up to a page multiple.

## -remarks

**ROUND_TO_PAGES** returns a ULONG_PTR with the input size rounded up to a multiple of the virtual memory page size for the current platform.

Callers of **ROUND_TO_PAGES** can be running at any IRQL. The caller must ensure that the supplied parameter cannot cause memory overflow.

