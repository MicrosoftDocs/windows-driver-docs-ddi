---
UID: NF:fltkernel.FltSupportsStreamHandleContexts
title: FltSupportsStreamHandleContexts function (fltkernel.h)
description: FltSupportsStreamHandleContexts determines whether stream handle contexts are supported on a given file object.
old-location: ifsk\fltsupportsstreamhandlecontexts.htm
tech.root: ifsk
ms.assetid: 8f4cf93f-eba7-4d6f-8b07-7c095e13f95e
ms.date: 04/16/2018
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

<b>FltSupportsStreamHandleContexts</b> determines whether stream handle contexts are supported on a given file object.

## -parameters

### -param FileObject 

[in]
Pointer to the file object to test.

## -returns

<b>FltSupportsStreamHandleContexts</b> returns <b>TRUE</b> if the file system supports stream handle contexts for the file object; <b>FALSE</b> otherwise.

## -remarks

Paging files do not currently support file, stream, or stream handle contexts. 

To allocate a new context, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecontext">FltAllocateContext</a>. 

To delete a stream handle context, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdeletestreamhandlecontext">FltDeleteStreamHandleContext</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdeletecontext">FltDeleteContext</a>. 

To get the stream handle context for a file object, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetstreamhandlecontext">FltGetStreamHandleContext</a>. 

To set a stream handle context on a file object, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetstreamhandlecontext">FltSetStreamHandleContext</a>. 

To release a reference on a context, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasecontext">FltReleaseContext</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecontext">FltAllocateContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdeletecontext">FltDeleteContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdeletestreamhandlecontext">FltDeleteStreamHandleContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetstreamhandlecontext">FltGetStreamHandleContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasecontext">FltReleaseContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetstreamhandlecontext">FltSetStreamHandleContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsupportsstreamcontexts">FltSupportsStreamContexts</a>

