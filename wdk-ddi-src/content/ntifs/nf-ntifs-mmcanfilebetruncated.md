---
UID: NF:ntifs.MmCanFileBeTruncated
title: MmCanFileBeTruncated function (ntifs.h)
description: Learn more about the MmCanFileBeTruncated function.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["MmCanFileBeTruncated function"]
ms.keywords: MmCanFileBeTruncated, MmCanFileBeTruncated routine [Installable File System Drivers], ifsk.mmcanfilebetruncated, mmref_7d6c86f9-4a26-4d2c-bf55-9352044e9339.xml, ntifs/MmCanFileBeTruncated
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
req.irql: < DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - MmCanFileBeTruncated
 - ntifs/MmCanFileBeTruncated
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - MmCanFileBeTruncated
---

# MmCanFileBeTruncated function

## -description

The **MmCanFileBeTruncated** routine checks whether a file can be truncated.

## -parameters

### -param SectionPointer [in]

Pointer to a structure that contains the file object's section object pointers.

### -param NewFileSize [in, optional]

Pointer to a variable that specifies the size to which the file is to be truncated.  If this parameter is NULL, then a length of zero is assumed.

## -returns

**MmCanFileBeTruncated** returns TRUE if the file can be truncated; FALSE otherwise.

## -remarks

**MmCanFileBeTruncated** must always be called before a file is truncated.

A file cannot be truncated (and **MmCanFileBeTruncated** will return FALSE) if any of the following are true:

* An image section exists for the file.

* There are one or more outstanding write probes on the file's data section.

* There is a mapped view of file's data section within the truncation range determined by **NewFileSize**.

* One or more users hold references to the data section for the file, and **NewFileSize** <= the current file size.

## -see-also

[**CcPurgeCacheSection**](nf-ntifs-ccpurgecachesection.md)

[**MmFlushImageSection**](nf-ntifs-mmflushimagesection.md)
