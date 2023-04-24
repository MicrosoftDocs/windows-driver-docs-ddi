---
UID: NF:miniport.FIELD_OFFSET
title: FIELD_OFFSET macro (miniport.h)
description: The FIELD_OFFSET macro (miniport.h) returns the byte offset of the specified field in the specified known structure type.
tech.root: kernel
ms.date: 08/29/2022
keywords: ["FIELD_OFFSET macro"]
ms.keywords: FIELD_OFFSET, FIELD_OFFSET function [Kernel-Mode Driver Architecture], k106_d6f0b450-e99c-4dd7-94c5-f428e4b1d642.xml, kernel.field_offset, ntdef/FIELD_OFFSET
req.header: miniport.h
req.include-header: Wdm.h, Ntddk.h, Miniport.h, Minitape.h, Scsi.h, Storport.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - FIELD_OFFSET
 - miniport/FIELD_OFFSET
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntdef.h
api_name:
 - FIELD_OFFSET
---

## -description

The **FIELD_OFFSET** macro returns the byte offset of a named field in a known structure type.

## -parameters

### -param type

Specifies the name of a known structure type containing **Field**.

### -param field

Specifies the name of a field in a structure of type **Type**.

## -remarks

Returns the byte offset of the caller supplied **Field** in the **Type** structure.

Used by device driver writers to symbolically determine the offset of a known field in a known structure type.

## -see-also

[**CONTAINING_RECORD**](/windows/win32/api/ntdef/nf-ntdef-containing_record)
