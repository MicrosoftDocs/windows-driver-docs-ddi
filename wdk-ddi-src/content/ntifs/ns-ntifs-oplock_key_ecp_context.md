---
UID: NS:ntifs._OPLOCK_KEY_ECP_CONTEXT
tech.root: ifsk
title: OPLOCK_KEY_ECP_CONTEXT
ms.date: 03/13/2023
targetos: Windows
description: Learn more about the OPLOCK_KEY_ECP_CONTEXT structure.
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
req.target-min-winverclnt: Windows 7; obsolete starting in Windows 8
req.target-min-winversvr: 
req.target-type: 
req.typenames: OPLOCK_KEY_ECP_CONTEXT, *POPLOCK_KEY_ECP_CONTEXT
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _OPLOCK_KEY_ECP_CONTEXT
 - POPLOCK_KEY_ECP_CONTEXT
 - OPLOCK_KEY_ECP_CONTEXT
f1_keywords:
 - _OPLOCK_KEY_ECP_CONTEXT
 - ntifs/_OPLOCK_KEY_ECP_CONTEXT
 - POPLOCK_KEY_ECP_CONTEXT
 - ntifs/POPLOCK_KEY_ECP_CONTEXT
 - OPLOCK_KEY_ECP_CONTEXT
 - ntifs/OPLOCK_KEY_ECP_CONTEXT
dev_langs:
 - c++
helpviewer_keywords:
 - _OPLOCK_KEY_ECP_CONTEXT
---

## -description

The **OPLOCK_KEY_ECP_CONTEXT** structure is used to attach an oplock key to a file. This structure is obsolete for Windows 8 and later versions; filters should instead use [DUAL_OP_LOCK_KEY_ECP_CONTEXT](./dual-oplock-key-ecp-context.md).

## -struct-fields

### -field OplockKey

A GUID for the oplock key. This GUID is shared among different handles and identifies them as belonging to the same client cache. When two handles share the same oplock key, a request performed on one handle will not break an outstanding oplock on the other handle.

### -field Reserved

Reserved. Must be set to zero.

## -remarks

For information about how to use ECPs to associate extra information with a file when the file is created, see [Using Extra Create Parameters with an IRP_MJ_CREATE Operation](/windows-hardware/drivers/ifs/using-ecps-to-process-irp-mj-create-operations-in-a-file-system-minifilter).

A minifilter should not alter the contents of the OPLOCK_KEY_ECP_CONTEXT structure when it sees the ECP coming down from above. You should use it to retrieve information about the oplock key ECP only. For more information about this issue, see [System-Defined ECPs](/windows-hardware/drivers/ifs/system-defined-ecps).

The oplock key enables an application to open multiple handles to the same stream without breaking the application's own oplock. The oplock break only occurs after the application receives a sharing violation (STATUS_SHARING_VIOLATION).

Oplocks are granted on stream handles when a stream is opened. Such a stream handle can be associated with an oplock key. A caller can explicitly provide the oplock key to the [**IoCreateFileEx**](../ntddk/nf-ntddk-iocreatefileex.md) routine to create the stream handle. If the caller does not explicitly specify an oplock key when the caller creates the handle, the operating system treats the handle as having a unique oplock key associated with the handle, so that the handle's key differs from any other key on any other handle. If a file operation is received on a handle other than the one on which the oplock was granted, and the oplock key that is associated with the oplock's handle differs from the key that is associated with the operation's handle, and that operation is incompatible with the currently granted oplock, then that oplock is broken. The oplock breaks even if it is the same process or thread performing the incompatible operation. For example, if a process opens a stream for which an exclusive oplock is granted and the same process then opens the same stream again, by using a different (or no) oplock key, the exclusive oplock is broken immediately.

Oplock keys are associated with handles when the handles are created. You can associate a handle with an oplock key even if no oplocks are granted.

For more information about oplocks and oplock keys, see [Oplock Semantics Overview](/windows-hardware/drivers/ifs/oplock-overview).

## -see-also

[DUAL_OP_LOCK_KEY_ECP_CONTEXT](dual-oplock-key-ecp-context.md)

[**IoCreateFileEx**](../ntddk/nf-ntddk-iocreatefileex.md)
