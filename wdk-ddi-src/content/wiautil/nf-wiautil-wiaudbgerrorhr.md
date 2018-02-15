---
UID: NF:wiautil.wiauDbgErrorHr
title: wiauDbgErrorHr function
author: windows-driver-content
description: The wiauDbgErrorHr function logs a message containing an HRESULT and its error message string.
old-location: image\wiaudbgerrorhr.htm
old-project: image
ms.assetid: 18d248d9-d447-4d3e-9eaa-f6befb4bef58
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: wiauDbgErrorHr, wiauFncs_1400188e-53d1-481c-a470-8a2247b7f34f.xml, image.wiaudbgerrorhr, wiautil/wiauDbgErrorHr, wiauDbgErrorHr function [Imaging Devices]
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
-	wiauDbgErrorHr
product: Windows
targetos: Windows
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---

# wiauDbgErrorHr function


## -description


The <b>wiauDbgErrorHr</b> function logs a message containing an HRESULT and its error message string.


## -syntax


````
inline void __stdcall wiauDbgErrorHr(
   HRESULT  hr,
   LPCSTR   fname,
   LPCSTR   fmt, ...
);
````


## -parameters




### -param hr

Specifies the HRESULT that is to be logged.


### -param fname

Pointer to a string containing the name of the function or method into which the call to <b>wiauDbgDump</b> is inserted.


### -param fmt

TBD


### -param param

TBD




####### - fmt, ...

Pointer to a format string that specifies a variable argument list, which starts with an ANSI format string containing the message and any conversion specifiers. The ellipsis (...) specifies a variable number of arguments that are to be output. 


## -returns



None




## -remarks



The <b>wiauDbgErrorHr</b> function typically logs two lines to the log file, or debugger, or both. The first line contains the text of the <i>fmt</i> parameter, including data, if provided. The second line contains the HRESULT and the message string associated with that HRESULT. The following example shows how this function might be called:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>wiauDbgErrorHr(hr, "AllocateBuffer", "Buffer size is %d bytes", size);</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wiautil\nf-wiautil-wiaudbgtrace.md">wiauDbgTrace</a>



<a href="..\wiautil\nf-wiautil-wiaudbgwarning.md">wiauDbgWarning</a>



<a href="..\wiautil\nf-wiautil-wiaudbgerror.md">wiauDbgError</a>



<a href="..\wiautil\nf-wiautil-wiaudbgdump.md">wiauDbgDump</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiauDbgErrorHr function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

