---
UID: NF:ntifs.CcCopyWriteWontFlush
title: CcCopyWriteWontFlush function (ntifs.h)
description: The CcCopyWriteWontFlush macro determines whether the amount of data to be copied in a call to CcCopyWrite is small enough not to require immediate flushing to disk if CcCopyWrite is called with Wait set to FALSE.
old-location: ifsk\cccopywritewontflush.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["CcCopyWriteWontFlush function"]
ms.keywords: CcCopyWriteWontFlush, CcCopyWriteWontFlush function [Installable File System Drivers], ccref_a8540235-ac2e-4d04-8153-95e2dae5a650.xml, ifsk.cccopywritewontflush, ntifs/CcCopyWriteWontFlush
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - CcCopyWriteWontFlush
 - ntifs/CcCopyWriteWontFlush
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - CcCopyWriteWontFlush
---

# CcCopyWriteWontFlush function


## -description

The <b>CcCopyWriteWontFlush</b> macro determines whether the amount of data to be copied in a call to <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-cccopywrite">CcCopyWrite</a> is small enough not to require immediate flushing to disk if <b>CcCopyWrite</b> is called with <i>Wait</i> set to <b>FALSE</b>.

## -parameters

### -param FileObject [in]


Pointer to a file object for the cached file to which the data is to be written.

### -param FileOffset [in]


Pointer to a variable that specifies the starting byte offset within the cached file where the data is to be written.

### -param Length [in]


Length in bytes of the data to be copied.

## -returns

<b>CcCopyWriteWontFlush</b> returns <b>TRUE</b> if the amount of data to be copied in a call to <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-cccopywrite">CcCopyWrite</a> is small enough not to require immediate flushing to disk, <b>FALSE</b> otherwise.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-cccaniwrite">CcCanIWrite</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-cccopywrite">CcCopyWrite</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccdeferwrite">CcDeferWrite</a>
