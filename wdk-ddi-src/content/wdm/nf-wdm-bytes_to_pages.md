---
UID: NF:wdm.BYTES_TO_PAGES
tech.root: 
title: BYTES_TO_PAGES
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
 - BYTES_TO_PAGES
f1_keywords:
 - BYTES_TO_PAGES
 - wdm/BYTES_TO_PAGES
dev_langs:
 - c++
---

## -description

The **BYTES_TO_PAGES** macro takes the size in bytes of the transfer request and calculates the number of pages required to contain the bytes.

## -parameters

### -param Size

[in]
Specifies the size in bytes of the transfer request.

## -remarks

**BYTES_TO_PAGES** returns the number of pages required to contain the specified number of bytes.

The system-defined constant PAGE_SIZE can be used to determine whether a given length in bytes for a transfer is less than the virtual memory page size of the current platform.


