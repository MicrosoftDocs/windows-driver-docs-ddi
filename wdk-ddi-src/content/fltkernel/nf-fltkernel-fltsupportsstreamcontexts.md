---
UID: NF:fltkernel.FltSupportsStreamContexts
title: FltSupportsStreamContexts function (fltkernel.h)
description: FltSupportsStreamContexts determines whether stream contexts are supported on a given file object.
old-location: ifsk\fltsupportsstreamcontexts.htm
tech.root: ifsk
ms.date: 1/22/2021
keywords: ["FltSupportsStreamContexts function"]
ms.keywords: FltApiRef_p_to_z_a2e2c9ac-1dc0-44cf-b8f0-172ca931a450.xml, FltSupportsStreamContexts, FltSupportsStreamContexts function [Installable File System Drivers], fltkernel/FltSupportsStreamContexts, ifsk.fltsupportsstreamcontexts
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
 - FltSupportsStreamContexts
 - fltkernel/FltSupportsStreamContexts
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltSupportsStreamContexts
---

# FltSupportsStreamContexts function

## -description

**FltSupportsStreamContexts** determines whether stream contexts are supported on a given file object.

## -parameters

### -param FileObject [in]

Pointer to the file object to test.

## -returns

**FltSupportsStreamContexts** returns **TRUE** if the file system supports stream contexts for the file object; **FALSE** otherwise.

## -remarks

Paging files do not currently support file, stream, or stream handle contexts.

## -see-also

[**FltAllocateContext**](nf-fltkernel-fltallocatecontext.md)

[**FltDeleteContext**](nf-fltkernel-fltdeletecontext.md)

[**FltDeleteStreamContext**](nf-fltkernel-fltdeletestreamcontext.md)

[**FltGetStreamContext**](nf-fltkernel-fltgetstreamcontext.md)

[**FltReleaseContext**](nf-fltkernel-fltreleasecontext.md)

[**FltSetStreamContext**](nf-fltkernel-fltsetstreamcontext.md)

[**FltSupportsStreamHandleContexts**](nf-fltkernel-fltsupportsstreamhandlecontexts.md)
