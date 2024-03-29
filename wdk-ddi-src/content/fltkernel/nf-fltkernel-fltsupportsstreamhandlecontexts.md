---
UID: NF:fltkernel.FltSupportsStreamHandleContexts
title: FltSupportsStreamHandleContexts function (fltkernel.h)
description: FltSupportsStreamHandleContexts determines whether stream handle contexts are supported on a given file object.
old-location: ifsk\fltsupportsstreamhandlecontexts.htm
tech.root: ifsk
ms.date: 01/22/2021
keywords: ["FltSupportsStreamHandleContexts function"]
ms.keywords: FltApiRef_p_to_z_07134b31-8768-43bc-904e-9abd945a166b.xml, FltSupportsStreamHandleContexts, FltSupportsStreamHandleContexts function [Installable File System Drivers], fltkernel/FltSupportsStreamHandleContexts, ifsk.fltsupportsstreamhandlecontexts
req.header: fltkernel.h
req.include-header: Fltkernel.h
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltSupportsStreamHandleContexts
 - fltkernel/FltSupportsStreamHandleContexts
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltSupportsStreamHandleContexts
---

# FltSupportsStreamHandleContexts function

## -description

**FltSupportsStreamHandleContexts** determines whether stream handle contexts are supported on a given file object.

## -parameters

### -param FileObject [in]

Pointer to the file object to test.

## -returns

**FltSupportsStreamHandleContexts** returns **TRUE** if the file system supports stream handle contexts for the file object; **FALSE** otherwise.

## -remarks

Paging files do not currently support file, stream, or stream handle contexts.

## -see-also

[**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md)

[**FltDeleteContext**](nf-fltkernel-fltdeletecontext.md)

[**FltDeleteStreamHandleContext**](nf-fltkernel-fltdeletestreamhandlecontext.md)

[**FltGetStreamHandleContext**](nf-fltkernel-fltgetstreamhandlecontext.md)

[**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md)

[**FltSetStreamHandleContext**](nf-fltkernel-fltsetstreamhandlecontext.md)

[**FltSupportsStreamContexts**](nf-fltkernel-fltsupportsstreamcontexts.md)
