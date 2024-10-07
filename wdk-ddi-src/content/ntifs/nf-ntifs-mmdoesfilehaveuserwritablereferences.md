---
UID: NF:ntifs.MmDoesFileHaveUserWritableReferences
title: MmDoesFileHaveUserWritableReferences function (ntifs.h)
description: Learn more about the MmDoesFileHaveUserWritableReferences function.
tech.root: ifsk
ms.date: 10/07/2024
keywords: ["MmDoesFileHaveUserWritableReferences function"]
ms.keywords: MmDoesFileHaveUserWritableReferences, MmDoesFileHaveUserWritableReferences function [Installable File System Drivers], ifsk.mmdoesfilehaveuserwritablereferences, mmref_fb87e0fa-60db-498e-8a17-a1bd366c3df6.xml, ntifs/MmDoesFileHaveUserWritableReferences
req.header: ntifs.h
req.include-header: Fltkernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows Vista
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - MmDoesFileHaveUserWritableReferences
 - ntifs/MmDoesFileHaveUserWritableReferences
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - MmDoesFileHaveUserWritableReferences
---

# MmDoesFileHaveUserWritableReferences function

## -description

The **MmDoesFileHaveUserWritableReferences** function determines whether a file associated with a transaction has any user-mapped sections present.

## -parameters

### -param SectionPointer [in]

Pointer to a [**SECTION_OBJECT_POINTERS**](../wdm/ns-wdm-_section_object_pointers.md) structure that contains the file object's section object pointers.  This parameter is required and can't be **NULL**.

## -returns

**MmDoesFileHaveUserWritableReferences** returns one of the following values.

| Return value | Meaning |
|--------------|---------|
| 0            | The file object has no user-mapped sections. It's safe to proceed with the transaction. |
| 1            | The file object has user-mapped sections. The transaction must be rolled back. |

## -remarks

For transactional file systems, you can use this function to determine if a given transaction is referencing a file object that can change. If so, the transaction must be rolled back because [atomicity](/windows-hardware/drivers/kernel/using-kernel-transaction-manager) can't be guaranteed.

Prior to calling **MmDoesFileHaveUserWritableReferences**, transactional file systems must check and intercept the creation of file objects that specify write access.  Specifically, prior to starting a transaction, transactional file systems must ensure that there are no writable file objects that currently exist for the given file in the transaction.  While the transaction is ongoing, transactional file systems must fail the requests to create file objects with write access for the transacted files.

This function can be used to detect if there are writable views for a file object even when all file handles and section handles for the file object have been closed.

For more information about transactions, see [Kernel Transaction Manager](/windows-hardware/drivers/kernel/introduction-to-ktm).

For more information about file objects, see [**FILE_OBJECT**](../wdm/ns-wdm-_file_object.md).

## -see-also

[**FILE_OBJECT**](../wdm/ns-wdm-_file_object.md)

[**SECTION_OBJECT_POINTERS**](../wdm/ns-wdm-_section_object_pointers.md)
