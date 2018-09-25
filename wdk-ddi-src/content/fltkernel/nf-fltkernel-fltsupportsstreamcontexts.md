---
UID: NF:fltkernel.FltSupportsStreamContexts
title: FltSupportsStreamContexts function
author: windows-driver-content
description: FltSupportsStreamContexts determines whether stream contexts are supported on a given file object.
old-location: ifsk\fltsupportsstreamcontexts.htm
tech.root: ifsk
ms.assetid: ea1fd4d5-85c6-40ce-9feb-a2c22e9fe905
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FltApiRef_p_to_z_a2e2c9ac-1dc0-44cf-b8f0-172ca931a450.xml, FltSupportsStreamContexts, FltSupportsStreamContexts function [Installable File System Drivers], fltkernel/FltSupportsStreamContexts, ifsk.fltsupportsstreamcontexts
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
-	FltSupportsStreamContexts
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltSupportsStreamContexts function


## -description


<b>FltSupportsStreamContexts</b> determines whether stream contexts are supported on a given file object. 


## -parameters




### -param FileObject [in]

Pointer to the file object to test. 


## -returns



<b>FltSupportsStreamContexts</b> returns <b>TRUE</b> if the file system supports stream contexts for the file object; <b>FALSE</b> otherwise. 




## -remarks



Paging files do not currently support file, stream, or stream handle contexts. 

To allocate a new context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>. 

To delete a stream context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541997">FltDeleteStreamContext</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff541960">FltDeleteContext</a>. 

To get the stream context for a file object, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543144">FltGetStreamContext</a>. 

To set a stream context on a file object, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544543">FltSetStreamContext</a>. 

To release a reference on a context, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544314">FltReleaseContext</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541960">FltDeleteContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541997">FltDeleteStreamContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543144">FltGetStreamContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544314">FltReleaseContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544543">FltSetStreamContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544586">FltSupportsStreamHandleContexts</a>
 

 

