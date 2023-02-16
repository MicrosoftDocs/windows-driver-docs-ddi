---
UID: NS:ntifs.TUNNEL
tech.root: ifsk
title: TUNNEL
ms.date: 09/27/2021
targetos: Windows
description: Learn more about the TUNNEL structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows Server 2022
req.target-min-winversvr: 
req.target-type: 
req.typenames: TUNNEL, *PTUNNEL
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - PTUNNEL
 - TUNNEL
f1_keywords:
 - PTUNNEL
 - ntifs/PTUNNEL
 - TUNNEL
 - ntifs/TUNNEL
dev_langs:
 - c++
---

## -description

The **TUNNEL** structure is a tunnel cache structure.

## -struct-fields

### -field Mutex

A [**FAST_MUTEX**](/windows-hardware/drivers/kernel/fast-mutexes-and-guarded-mutexes) structure that contains the mutex for cache manipulation.

### -field Cache

Pointer to a [**RTL_SPLAY_LINKS**](../ntddk/ns-ntddk-_rtl_splay_links.md) structure that contains the splay tree of tunneled information keyed by DirKey ## Name.

### -field TimerQueue

A [**LIST_ENTRY**](/windows/win32/api/ntdef/ns-ntdef-list_entry) structure that contains the timer queue used to age entries out of the main cache.

### -field NumEntries

Number of entries in the cache. **NumEntries** is used to track the number of entries in the cache to prevent excessive use of memory.

