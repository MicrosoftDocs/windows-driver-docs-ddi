---
UID: NA:classpnp
ms.assetid: be83a418-7913-3897-93e4-64f8740098af
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Classpnp.h header



This header is used by Windows kernel. For more information, see
- [Windows kernel](../_kernel/index.md)

Classpnp.h contain these programming interfaces:


## Macros

| Title   | Description   |
| ---- |:---- |
| [ExAllocatePool macro](nf-classpnp-exallocatepool.md) | The ExAllocatePool routine is obsolete, and is exported only for existing binaries. Use ExAllocatePoolWithTag instead.ExAllocatePool allocates pool memory of the specified type and returns a pointer to the allocated block. |
| [ExAllocatePoolWithQuota macro](nf-classpnp-exallocatepoolwithquota.md) | The ExAllocatePoolWithQuota routine is obsolete, and is exported only for existing driver binaries. Use ExAllocatePoolWithQuotaTag instead.ExAllocatePoolWithQuota allocates pool memory, charging quota against the current process. |
