---
UID: NF:wiautil.wiauDbgWarning
title: wiauDbgWarning function
author: windows-driver-content
description: The wiauDbgWarning function logs a warning message.
old-location: image\wiaudbgwarning.htm
old-project: image
ms.assetid: f10f1c28-0bfd-44c5-a0aa-9f9227f775d2
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: image.wiaudbgwarning, wiautil/wiauDbgWarning, wiauFncs_1248626b-0d4f-445c-855c-9ba477cf306c.xml, wiauDbgWarning function [Imaging Devices], wiauDbgWarning
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wiautil.h
apiname:
-	wiauDbgWarning
product: Windows
targetos: Windows
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---

# wiauDbgWarning function


## -description


The <b>wiauDbgWarning</b> function logs a warning message.


## -syntax


````
inline void __stdcall wiauDbgWarning(
   LPCSTR   fname,
   LPCSTR   fmt, ...
);
````


## -parameters




### -param fname

Pointer to a string containing the name of the function or method into which the call to <b>wiauDbgWarning</b> is inserted.


### -param fmt

TBD


### -param param

TBD




####### - fmt, ...

Pointer to a format string that specifies a variable argument list, which starts with an ANSI format string containing the warning message and any conversion specifiers. The ellipsis (...) specifies a variable number of arguments that are to be output.


## -returns



None




## -see-also

<a href="..\wiautil\nf-wiautil-wiaudbgerror.md">wiauDbgError</a>



<a href="..\wiautil\nf-wiautil-wiaudbgerrorhr.md">wiauDbgErrorHr</a>



<a href="..\wiautil\nf-wiautil-wiaudbgdump.md">wiauDbgDump</a>



<a href="..\wiautil\nf-wiautil-wiaudbgtrace.md">wiauDbgTrace</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiauDbgWarning function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

