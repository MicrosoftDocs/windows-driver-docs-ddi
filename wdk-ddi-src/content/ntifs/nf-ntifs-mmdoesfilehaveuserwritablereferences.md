---
UID: NF:ntifs.MmDoesFileHaveUserWritableReferences
title: MmDoesFileHaveUserWritableReferences function (ntifs.h)
description: The MmDoesFileHaveUserWritableReferences function returns the number of writable references for a file object.
old-location: ifsk\mmdoesfilehaveuserwritablereferences.htm
tech.root: ifsk
ms.assetid: b88afd6e-3a0a-471e-a874-db8fc3175d61
ms.date: 04/16/2018
keywords: ["MmDoesFileHaveUserWritableReferences function"]
ms.keywords: MmDoesFileHaveUserWritableReferences, MmDoesFileHaveUserWritableReferences function [Installable File System Drivers], ifsk.mmdoesfilehaveuserwritablereferences, mmref_fb87e0fa-60db-498e-8a17-a1bd366c3df6.xml, ntifs/MmDoesFileHaveUserWritableReferences
f1_keywords:
 - "ntifs/MmDoesFileHaveUserWritableReferences"
req.header: ntifs.h
req.include-header: Fltkernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows operating systems.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- MmDoesFileHaveUserWritableReferences
product:
- Windows
targetos: Windows
req.typenames: 
---

# MmDoesFileHaveUserWritableReferences function


## -description


The <b>MmDoesFileHaveUserWritableReferences </b>function returns the number of writable references for a file object.


## -parameters




### -param SectionPointer [in]

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_section_object_pointers">SECTION_OBJECT_POINTERS</a> structure that contains the file object's section object pointers.  This parameter is required and cannot be <b>NULL</b>.


## -returns



<b>MmDoesFileHaveUserWritableReferences </b>returns the number of writable references for the file object associated with the <i>SectionPointer </i>parameter.




## -remarks



<b>MmDoesFileHaveUserWritableReferences</b> returns the number of writable references for the file object that is associated with the <i>SectionPointer </i>parameter.  This return value is the sum of the following numbers:

<ul>
<li>
 The number of writable file handles for the associated file object.

</li>
<li>
 The number of writable sections for the associated file object.

</li>
<li>
 The number of writable views for the associated file object.

</li>
<li>
 The number of outstanding <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_mdl">MDL</a>s, which are mapping regions for the associated file object.

</li>
</ul>
For transactional file systems, you can use this function to determine if a given transaction is referencing a file object that can change.  If so, the transaction must be rolled back because <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-kernel-transaction-manager">atomicity</a> cannot be guaranteed.

Prior to calling <b>MmDoesFileHaveUserWritableReferences</b>, transactional file systems must check and intercept the creation of file objects that specify write access.  Specifically, prior to starting a transaction, transactional file systems must ensure that there are no writable file objects that currently exist for the given file in the transaction.  While the transaction is ongoing, transactional file systems must fail the requests to create file objects with write access for the transacted files.

<div class="alert"><b>Note</b>   This function can be used to detect if there are writable views for a file object even when all file handles and section handles for the file object have been closed.</div>
<div> </div>
For more information about transactions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-kernel-transaction-manager">Kernel Transaction Manager Design Guide</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Kernel Transaction Manager Routines</a>.

For more information about file objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">FILE_OBJECT</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">FILE_OBJECT</a>
 

 

