---
UID: NF:dispmprt.DlMapMemoryEx
title: DlMapMemoryEx function
author: windows-driver-content
description: Maps a range of bus-relative physical addresses of display memory into system space or into the virtual address space of a user-mode process.
tech.root: display
ms.assetid: a474b01c-75bc-49fe-8b5a-cbe281c97d16
ms.author: windowsdriverdev
ms.date: 04/04/2019
keywords: ["DlMapMemoryEx function"]
ms.keywords: DlMapMemoryEx
req.header: dispmprt.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - DlMapMemoryEx
 - dispmprt/DlMapMemoryEx
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - Displib.lib
 - Displib.dll
api_name:
 - DlMapMemoryEx
product:
 - Windows
dev_langs:
 - c++
---

# DlMapMemoryEx function


## -description

Maps a range of bus-relative physical addresses of display memory into system space or into the virtual address space of a user-mode process.

## -parameters

### -param DeviceHandle

A handle that represents a display adapter.

### -param TranslatedAddress

### -param Length

On input, specifies the number of bytes of memory to map.

### -param InIoSpace

Pointer to a variable that indicates the location of the range.

### -param ProcessHandle

### -param VirtualAddress

Pointer to a variable that, on input, is either <b>NULL</b> or a handle to a user-mode process.

### -param MapToUserMode

## -returns

This function returns NTSTATUS.

## -remarks

## -see-also

