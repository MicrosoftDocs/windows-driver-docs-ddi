---
UID: NS:wdm._KTRIAGE_DUMP_DATA_ARRAY
title: _KTRIAGE_DUMP_DATA_ARRAY (wdm.h)
description: 
ms.date: 10/19/2018
tech.root: devtest
keywords: ["KTRIAGE_DUMP_DATA_ARRAY structure"]
ms.keywords: _KTRIAGE_DUMP_DATA_ARRAY, PKTRIAGE_DUMP_DATA_ARRAY, KTRIAGE_DUMP_DATA_ARRAY,
req.header: wdm.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: PKTRIAGE_DUMP_DATA_ARRAY, KTRIAGE_DUMP_DATA_ARRAY
targetos: Windows
f1_keywords:
 - _KTRIAGE_DUMP_DATA_ARRAY
 - wdm/_KTRIAGE_DUMP_DATA_ARRAY
 - PKTRIAGE_DUMP_DATA_ARRAY
 - wdm/PKTRIAGE_DUMP_DATA_ARRAY
 - KTRIAGE_DUMP_DATA_ARRAY
 - wdm/KTRIAGE_DUMP_DATA_ARRAY
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _KTRIAGE_DUMP_DATA_ARRAY
 - PKTRIAGE_DUMP_DATA_ARRAY
 - KTRIAGE_DUMP_DATA_ARRAY
---

# _KTRIAGE_DUMP_DATA_ARRAY structure


## -description

Specifies an array of memory locations and lengths (ranges) to be preserved in crash dump files.

## -struct-fields

### -field List

A pointer to a [**LIST_ENTRY**](/windows/win32/api/ntdef/ns-ntdef-list_entry) structure that represents the entry to be added in the array.

### -field NumBlocksUsed

### -field NumBlocksTotal

### -field VirtMemSize

### -field ComponentNameBufferLength

### -field ComponentName

### -field Blocks

## -remarks

A driver provides a pointer to a structure of this type when it calls the [**KeAddTriageDumpDataBlock**](./nf-wdm-keaddtriagedumpdatablock.md) function.

## -see-also

[*KBUGCHECK_REASON_CALLBACK_ROUTINE*](./nc-wdm-kbugcheck_reason_callback_routine.md)

