---
UID: NS:wdm._KTRIAGE_DUMP_DATA_ARRAY
title: _KTRIAGE_DUMP_DATA_ARRAY (wdm.h)
description: 
ms.assetid: 07dbd4cb-0840-4802-a595-a9e08cab4918
ms.date: 05/08/2019
ms.topic: struct
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
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- wdm.h
api_name: 
- _KTRIAGE_DUMP_DATA_ARRAY
product:
- Windows
targetos: Windows
---

# _KTRIAGE_DUMP_DATA_ARRAY structure

## -description

## -struct-fields

### -field List

A pointer to a [**LIST_ENTRY**](https://msdn.microsoft.com/library/windows/hardware/ff554296) structure that represents the entry to be added in the array.
 
### -field NumBlocksUsed

The number of block used.
 
### -field NumBlocksTotal

The total number of blocks.
 
### -field VirtMemSize

The virtual memory size.
 
### -field ComponentNameBufferLength

The ComponentName buffer length.

### -field ComponentName

The  ComponentName.

### -field Blocks

Information pending.

## -remarks

For more information about how this structure is used, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine">Writing a Bug Check Callback Routine</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine">Writing a Bug Check Callback Routine</a>.
