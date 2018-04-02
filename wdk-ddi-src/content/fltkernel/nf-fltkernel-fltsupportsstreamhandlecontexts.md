---
UID: NF:fltkernel.FltSupportsStreamHandleContexts
title: FltSupportsStreamHandleContexts function
author: windows-driver-content
description: FltSupportsStreamHandleContexts determines whether stream handle contexts are supported on a given file object.
old-location: ifsk\fltsupportsstreamhandlecontexts.htm
old-project: ifsk
ms.assetid: 8f4cf93f-eba7-4d6f-8b07-7c095e13f95e
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FltApiRef_p_to_z_07134b31-8768-43bc-904e-9abd945a166b.xml, FltSupportsStreamHandleContexts, FltSupportsStreamHandleContexts function [Installable File System Drivers], fltkernel/FltSupportsStreamHandleContexts, ifsk.fltsupportsstreamhandlecontexts
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltSupportsStreamHandleContexts
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltSupportsStreamHandleContexts function


## -description


<b>FltSupportsStreamHandleContexts</b> determines whether stream handle contexts are supported on a given file object. 


## -parameters




### -param FileObject [in]

Pointer to the file object to test. 


## -returns



<b>FltSupportsStreamHandleContexts</b> returns <b>TRUE</b> if the file system supports stream handle contexts for the file object; <b>FALSE</b> otherwise. 




## -remarks



Paging files do not currently support file, stream, or stream handle contexts. 

To allocate a new context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>. 

To delete a stream handle context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff542016">FltDeleteStreamHandleContext</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff541960">FltDeleteContext</a>. 

To get the stream handle context for a file object, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543155">FltGetStreamHandleContext</a>. 

To set a stream handle context on a file object, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544552">FltSetStreamHandleContext</a>. 

To release a reference on a context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544314">FltReleaseContext</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541960">FltDeleteContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542016">FltDeleteStreamHandleContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543155">FltGetStreamHandleContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544314">FltReleaseContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544552">FltSetStreamHandleContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544581">FltSupportsStreamContexts</a>
 

 

