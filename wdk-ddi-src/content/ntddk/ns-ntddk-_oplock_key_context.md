---
UID: NS:ntddk._OPLOCK_KEY_CONTEXT
title: OPLOCK_KEY_CONTEXT (ntddk.h)
description: The OPLOCK_KEY_CONTEXT structure is returned from IoGetOplockKeyContextEx. This structure contains oplock keys for a specific file object.
tech.root: ifsk
ms.date: 03/16/2023
keywords: ["OPLOCK_KEY_CONTEXT structure"]
ms.keywords: "*POPLOCK_KEY_CONTEXT, OPLOCK_KEY_CONTEXT, OPLOCK_KEY_CONTEXT structure [Installable File System Drivers], OPLOCK_KEY_FLAG_PARENT_KEY, OPLOCK_KEY_FLAG_TARGET_KEY, OPLOCK_KEY_VERSION_WIN7, OPLOCK_KEY_VERSION_WIN8, POPLOCK_KEY_CONTEXT, POPLOCK_KEY_CONTEXT structure pointer [Installable File System Drivers], _OPLOCK_KEY_CONTEXT, ifsk.oplock_key_context, ntddk/OPLOCK_KEY_CONTEXT, ntddk/POPLOCK_KEY_CONTEXT"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available starting in Windows 8.
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
req.irql: 
targetos: Windows
req.typenames: OPLOCK_KEY_CONTEXT, *POPLOCK_KEY_CONTEXT
f1_keywords:
 - _OPLOCK_KEY_CONTEXT
 - ntddk/_OPLOCK_KEY_CONTEXT
 - POPLOCK_KEY_CONTEXT
 - ntddk/POPLOCK_KEY_CONTEXT
 - OPLOCK_KEY_CONTEXT
 - ntddk/OPLOCK_KEY_CONTEXT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _OPLOCK_KEY_CONTEXT
 - POPLOCK_KEY_CONTEXT
 - OPLOCK_KEY_CONTEXT
---

## -description

The **OPLOCK_KEY_CONTEXT** structure is returned from [IoGetOplockKeyContextEx](./nf-ntddk-iogetoplockkeycontextex.md). This structure contains oplock keys for a specific file object.

## -struct-fields

### -field Version

The oplock key version. The version is set to one of the following values:

| Value | Meaning |
|---|---|
| **OPLOCK_KEY_VERSION_WIN7** | This is a Windows 7 oplock key. |
| **OPLOCK_KEY_VERSION_WIN8** | This is a Windows 8 oplock key. |

### -field Flags

A set of flags that indicate the oplock key type. **Flags** is set to one or both of the following values:

| Value | Meaning |
|---|---|
| OPLOCK_KEY_FLAG_PARENT_KEY | A valid oplock key is present in **ParentOplockKey.** |
| OPLOCK_KEY_FLAG_TARGET_KEY | A valid oplock key is present in **TargetOplockKey.** |

### -field ParentOplockKey

A **GUID**  that represents the parent oplock  key value.

### -field TargetOplockKey

A **GUID**  that represents the target oplock  key value.

### -field Reserved

## -remarks

If an oplock is requested for a file during an [IRP_MJ_CREATE](/windows-hardware/drivers/ifs/irp-mj-create) request, a file system that supports oplocks   will attach an oplock key context to the file object created. The oplock key  context is later available through a pointer to an **OPLOCK_KEY_CONTEXT** structure.  The **OPLOCK_KEY_CONTEXT** structure is returned from a call to [IoGetOplockKeyContextEx](./nf-ntddk-iogetoplockkeycontextex.md).

## -see-also

[IoGetOplockKeyContextEx](./nf-ntddk-iogetoplockkeycontextex.md)

[Oplock Semantics](/windows-hardware/drivers/ifs/oplock-semantics)
