---
UID: NA:smcnt
ms.assetid: f0458d39-14d8-3d3d-9c48-866fa482bc98
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Smcnt.h header



This header is used by Smart Card Reader Devices, Windows kernel. For more information, see
- [Smart Card Reader Devices](../_smartcrd/index.md)
- [Windows kernel](../_kernel/index.md)

Smcnt.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [_OS_DEP_DATA structure](ns-smcnt-_os_dep_data.md) | The OS_DEP_DATA structure defines the data that is stored in the OsData member of the SMARTCARD_EXTENSION structure, which holds smart card information that is specific to the operating system. |

## Macros

| Title   | Description   |
| ---- |:---- |
| [ExAllocatePool macro](nf-smcnt-exallocatepool.md) | The ExAllocatePool routine is obsolete, and is exported only for existing binaries. Use ExAllocatePoolWithTag instead.ExAllocatePool allocates pool memory of the specified type and returns a pointer to the allocated block. |
