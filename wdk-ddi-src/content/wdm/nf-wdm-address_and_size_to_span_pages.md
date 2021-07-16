---
UID: NF:wdm.ADDRESS_AND_SIZE_TO_SPAN_PAGES
tech.root: 
title: ADDRESS_AND_SIZE_TO_SPAN_PAGES
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
 - ADDRESS_AND_SIZE_TO_SPAN_PAGES
f1_keywords:
 - ADDRESS_AND_SIZE_TO_SPAN_PAGES
 - wdm/ADDRESS_AND_SIZE_TO_SPAN_PAGES
dev_langs:
 - c++
---

## -description

The **ADDRESS_AND_SIZE_TO_SPAN_PAGES** macro returns the number of pages spanned by the virtual range defined by a virtual address and the size in bytes of a transfer request.

## -parameters

### -param Va

[in]
Pointer to the virtual address that is the base of the range.

### -param Size

[in]
Specifies the size in bytes of the transfer request.

## -remarks

**ADDRESS_AND_SIZE_TO_SPAN_PAGES** returns the number of pages spanned by the virtual range starting at _Va_.

Drivers that make DMA transfers call **ADDRESS_AND_SIZE_TO_SPAN_PAGES** to determine whether a transfer request must be split into a sequence of device DMA operations.

A driver can use the system-defined constant PAGE_SIZE to determine whether the number of bytes to be transferred is less than the virtual memory page size of the current platform.

Callers of **ADDRESS_AND_SIZE_TO_SPAN_PAGES** can be running at any IRQL. The caller must ensure that the specified parameters do not cause memory overflow.

