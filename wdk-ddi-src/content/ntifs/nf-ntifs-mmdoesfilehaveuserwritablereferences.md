---
UID: NF:ntifs.MmDoesFileHaveUserWritableReferences
title: MmDoesFileHaveUserWritableReferences function (ntifs.h)
description: The MmDoesFileHaveUserWritableReferences function returns the number of writable references for a file object.
old-location: ifsk\mmdoesfilehaveuserwritablereferences.htm
tech.root: ifsk
ms.date: 11/23/2021
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

The **MmDoesFileHaveUserWritableReferences** function returns the number of writable references for a file object.

## -parameters

### -param SectionPointer [in]

Pointer to a [**SECTION_OBJECT_POINTERS**](../wdm/ns-wdm-_section_object_pointers.md) structure that contains the file object's section object pointers.  This parameter is required and cannot be **NULL**.

## -returns

**MmDoesFileHaveUserWritableReferences** returns the number of writable references for the file object associated with the **SectionPointer** parameter.

## -remarks

**MmDoesFileHaveUserWritableReferences** returns the number of writable references for the file object that is associated with the **SectionPointer** parameter.  This return value is the sum of the following numbers:

* The number of writable file handles for the associated file object.

* The number of writable sections for the associated file object.

* The number of writable views for the associated file object.

* The number of outstanding [**MDL**](../wdm/ns-wdm-_mdl.md)s, which are mapping regions for the associated file object.

For transactional file systems, you can use this function to determine if a given transaction is referencing a file object that can change.  If so, the transaction must be rolled back because [atomicity](/windows-hardware/drivers/kernel/using-kernel-transaction-manager) cannot be guaranteed.

Prior to calling **MmDoesFileHaveUserWritableReferences**, transactional file systems must check and intercept the creation of file objects that specify write access.  Specifically, prior to starting a transaction, transactional file systems must ensure that there are no writable file objects that currently exist for the given file in the transaction.  While the transaction is ongoing, transactional file systems must fail the requests to create file objects with write access for the transacted files.

> [!NOTE]
> This function can be used to detect if there are writable views for a file object even when all file handles and section handles for the file object have been closed.

For more information about transactions, see [Kernel Transaction Manager](/windows-hardware/drivers/kernel/introduction-to-ktm).

For more information about file objects, see [**FILE_OBJECT**](../wdm/ns-wdm-_file_object.md).
