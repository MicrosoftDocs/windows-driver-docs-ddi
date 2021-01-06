---
UID: NF:dispmprt.DlUnmapMemory
title: DlUnmapMemory function
description: Releases a mapping between a logical address range for the adapter and a virtual address range in the user-mode address space of a particular thread.
tech.root: display
ms.date: 04/04/2019
keywords: ["DlUnmapMemory function"]
ms.keywords: DlUnmapMemory
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
 - DlUnmapMemory
 - dispmprt/DlUnmapMemory
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - Displib.lib
 - Displib.dll
api_name:
 - DlUnmapMemory
product:
 - Windows
dev_langs:
 - c++
---

# DlUnmapMemory function


## -description

Releases a mapping between a logical address range for the adapter and a virtual address range in the user-mode address space of a particular thread.

## -parameters

### -param DeviceHandle

A handle that represents a display adapter.

### -param VirtualAddress

The virtual address.

### -param ProcessHandle

The process handle.

## -returns

This function returns NTSTATUS.

## -remarks

## -see-also

