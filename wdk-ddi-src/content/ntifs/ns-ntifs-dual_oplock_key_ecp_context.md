---
UID: NS:ntifs._DUAL_OPLOCK_KEY_ECP_CONTEXT
tech.root: ifsk
title: DUAL_OPLOCK_KEY_ECP_CONTEXT
ms.date: 03/23/2023
targetos: Windows
description: Learn more about the DUAL_OPLOCK_KEY_ECP_CONTEXT structure.
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
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.target-type: 
req.typenames: DUAL_OPLOCK_KEY_ECP_CONTEXT, *PDUAL_OPLOCK_KEY_ECP_CONTEXT
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _DUAL_OPLOCK_KEY_ECP_CONTEXT
 - PDUAL_OPLOCK_KEY_ECP_CONTEXT
 - DUAL_OPLOCK_KEY_ECP_CONTEXT
f1_keywords:
 - _DUAL_OPLOCK_KEY_ECP_CONTEXT
 - ntifs/_DUAL_OPLOCK_KEY_ECP_CONTEXT
 - PDUAL_OPLOCK_KEY_ECP_CONTEXT
 - ntifs/PDUAL_OPLOCK_KEY_ECP_CONTEXT
 - DUAL_OPLOCK_KEY_ECP_CONTEXT
 - ntifs/DUAL_OPLOCK_KEY_ECP_CONTEXT
dev_langs:
 - c++
helpviewer_keywords:
 - _DUAL_OPLOCK_KEY_ECP_CONTEXT
---

## -description

The **DUAL_OPLOCK_KEY_ECP_CONTEXT** structure contains the extra create parameter context for a dual oplock key. Oplocks keys for both a target and a parent file object can be set in this structure.

## -struct-fields

### -field ParentOplockKey

A **GUID** representing the parent oplock key value.

### -field TargetOplockKey

A **GUID** representing the target oplock key value.

### -field ParentOplockKeySet

Set to TRUE if **ParentOplockKey** contains a valid GUID for the parent's oplock key.

### -field TargetOplockKeySet

Set to TRUE if **TargetOplockKey** contains a valid GUID for the target's oplock key.

## -remarks

The **DUAL_OPLOCK_KEY_ECP_CONTEXT** structure provides dual oplock keys to allow oplock requests on files and directories. Like the [**OPLOCK_KEY_ECP_CONTEXT**](ns-ntifs-oplock_key_ecp_context.md) structure, **DUAL_OPLOCK_KEY_ECP_CONTEXT** is set in an extra create parameter list ([**ECP_LIST**](/previous-versions/windows/hardware/drivers/ff540148(v=vs.85))) and later associated with a file object during processing of [**IRP_MJ_CREATE**](/windows-hardware/drivers/ifs/irp-mj-create) by a file system or file system filter driver.

The value **GUID_ECP_DUAL_OPLOCK_KEY** is used when calling support routines such as [**FsRtlAllocateExtraCreateParameter**](nf-ntifs-fsrtlallocateextracreateparameter.md), [**FsRtlInitializeExtraCreateParameter**](nf-ntifs-fsrtlinitializeextracreateparameter.md), or [**FltRemoveExtraCreateParameter**](../fltkernel/nf-fltkernel-fltremoveextracreateparameter.md).

## -see-also

[**ECP_LIST**](/previous-versions/windows/hardware/drivers/ff540148(v=vs.85))

[**IO_DRIVER_CREATE_CONTEXT**](../ntddk/ns-ntddk-_io_driver_create_context.md)

[**IoCreateFileEx**](../ntddk/nf-ntddk-iocreatefileex.md)

[**IRP_MJ_CREATE**](/windows-hardware/drivers/ifs/irp-mj-create)

[**OPLOCK_KEY_ECP_CONTEXT**](ns-ntifs-oplock_key_ecp_context.md)
