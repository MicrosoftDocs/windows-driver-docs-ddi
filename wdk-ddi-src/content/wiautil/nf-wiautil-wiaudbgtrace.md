---
UID: NF:wiautil.wiauDbgTrace
title: wiauDbgTrace function
author: windows-driver-content
description: The wiauDbgTrace function logs a trace message.
old-location: image\wiaudbgtrace.htm
old-project: image
ms.assetid: c3cdb5c9-b43d-443b-8d04-d30eb74f39da
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: image.wiaudbgtrace, wiauDbgTrace, wiauDbgTrace function [Imaging Devices], wiauFncs_5c66ac77-5db3-489c-b7fc-84393e9105dd.xml, wiautil/wiauDbgTrace
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wiautil.h
req.include-header: Wiautil.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later.
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wiautil.h
api_name:
-	wiauDbgTrace
product: Windows
targetos: Windows
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---

# wiauDbgTrace function


## -description


The <b>wiauDbgTrace</b> function logs a trace message.


## -syntax


````
inline void __stdcall wiauDbgTrace(
   LPCSTR   fname,
   LPCSTR   fmt, ...
);
````


## -parameters




### -param fname

Pointer to a string containing the name of the function or method into which the call to <b>wiauDbgTrace</b> is inserted.


### -param fmt

TBD


### -param param

TBD




####### - fmt, ...

Pointer to a format string that specifies a variable argument list, which starts with an ANSI format string containing the trace message and any conversion specifiers. The ellipsis (...) specifies a variable number of arguments that are to be output.


## -returns



None




## -see-also

<a href="..\wiautil\nf-wiautil-wiaudbgdump.md">wiauDbgDump</a>



<a href="..\wiautil\nf-wiautil-wiaudbgwarning.md">wiauDbgWarning</a>



<a href="..\wiautil\nf-wiautil-wiaudbgerror.md">wiauDbgError</a>



<a href="..\wiautil\nf-wiautil-wiaudbgerrorhr.md">wiauDbgErrorHr</a>



 

 


