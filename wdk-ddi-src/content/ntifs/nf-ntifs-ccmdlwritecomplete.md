---
UID: NF:ntifs.CcMdlWriteComplete
title: CcMdlWriteComplete function (ntifs.h)
description: The CcMdlWriteComplete routine frees the memory descriptor lists (MDL) created by CcPrepareMdlWrite for a cached file.
old-location: ifsk\ccmdlwritecomplete.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["CcMdlWriteComplete function"]
ms.keywords: CcMdlWriteComplete, CcMdlWriteComplete routine [Installable File System Drivers], ccref_fe5a4900-c0bc-4100-b3e9-e2b7d780a9d2.xml, ifsk.ccmdlwritecomplete, ntifs/CcMdlWriteComplete
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - CcMdlWriteComplete
 - ntifs/CcMdlWriteComplete
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - CcMdlWriteComplete
---

# CcMdlWriteComplete function


## -description

The <b>CcMdlWriteComplete</b> routine frees the memory descriptor lists (MDL) created by <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccpreparemdlwrite">CcPrepareMdlWrite</a> for a cached file.

## -parameters

### -param FileObject [in]


File object pointer that was passed to <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccpreparemdlwrite">CcPrepareMdlWrite</a>.

### -param FileOffset [in]


Value of <i>FileOffset</i> that was passed to <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccpreparemdlwrite">CcPrepareMdlWrite</a>.

### -param MdlChain [in]


Address of the MDL chain returned by <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccpreparemdlwrite">CcPrepareMdlWrite</a>.

## -remarks

File systems call <b>CcMdlWriteComplete</b> to free the memory descriptor lists (MDL) created by <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccpreparemdlwrite">CcPrepareMdlWrite</a> for a cached file and to mark the specified byte range for write. All physical pages that were locked down are unlocked. Any pages that were mapped are unmapped.

If the FO_WRITE_THROUGH flag is set on the file object pointed to by the <i>FileObject</i> parameter, the file data is immediately flushed to disk. This flush operation re-enters the file system and can cause <b>CcMdlWriteComplete</b> to raise an exception if the flush operation fails. In this case, the MDL has not been freed and the caller may re-try the operation.

After <b>CcMdlWriteComplete</b> is called successfully for an IRP_MN_COMPLETE operation, the caller must set the IRP's <b>MdlAddress</b> field to <b>NULL</b>. 

Before using <b>CcMdlWriteComplete</b>, file system developers are strongly encouraged to study the way this routine is used in the FASTFAT sample. 

Each call to <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccpreparemdlwrite">CcPrepareMdlWrite</a> must be followed by a call to <b>CcMdlWriteComplete</b> or <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccmdlwriteabort">CcMdlWriteAbort</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccmdlwriteabort">CcMdlWriteAbort</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccpreparemdlwrite">CcPrepareMdlWrite</a>
