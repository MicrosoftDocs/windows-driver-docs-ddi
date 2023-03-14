---
UID: NF:fltkernel.FltReleaseResource
tech.root: ifsk
title: FltReleaseResource
ms.date: 03/03/2023
targetos: Windows
description: Learn more about the FltReleaseResource function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: fltkernel.h
req.idl: 
req.include-header: 
req.irql: IRQL <= DISPATCH_LEVEL
req.kmdf-ver: 
req.lib: FltMgr.lib
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows XP SP2
req.target-min-winversvr: Windows Server 2003 SP1
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - 
api_location:
 - fltkernel.h
api_name:
 - FltReleaseResource
f1_keywords:
 - FltReleaseResource
 - fltkernel/FltReleaseResource
dev_langs:
 - c++
helpviewer_keywords:
 - FltReleaseResource
---

## -description

The **FltReleaseResource** routine releases a specified resource owned by the current thread.

## -parameters

### -param Resource [in/out]

Pointer to the opaque [**ERESOURCE**](/windows-hardware/drivers/kernel/eresource-structures) structure for the resource to be released.

## -returns

None.

## -remarks

FltReleaseResource releases a resource that was previously acquired by calling [**FltAcquireResourceExclusive**](nf-fltkernel-fltacquireresourceexclusive.md) or [**FltAcquireResourceShared**](nf-fltkernel-fltacquireresourceshared.md).

**FltReleaseResource** is a wrapper for [**ExReleaseResourceLite**](../wdm/nf-wdm-exreleaseresourcelite.md) that reenables normal kernel APC delivery.

Because FltReleaseResource reenables normal kernel APC delivery, it is not necessary to call [**KeEnterCriticalRegion**](../ntddk/nf-ntddk-keentercriticalregion.md) or [**FsRtlEnterFileSystem**](fsrtlenterfilesystem.md) after calling **FltReleaseResource**.

To acquire a resource for exclusive access, call [**FltAcquireResourceExclusive**](nf-fltkernel-fltacquireresourceexclusive.md).

To acquire a resource for shared access, call [**FltAcquireResourceShared**](nf-fltkernel-fltacquireresourceshared.md).

To delete a resource from the system's resource list, call [**ExDeleteResourceLite**](../wdm/nf-wdm-exdeleteresourcelite.md).

To initialize a resource for reuse, call [**ExReinitializeResourceLite**](../wdm/nf-wdm-exreinitializeresourcelite.md).

For more information about ERESOURCE structures, see [Introduction to ERESOURCE Routines](/windows-hardware/drivers/kernel/introduction-to-eresource-routines).
