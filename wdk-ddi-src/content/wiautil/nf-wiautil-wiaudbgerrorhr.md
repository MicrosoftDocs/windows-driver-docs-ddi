---
UID: NF:wiautil.wiauDbgErrorHr
title: wiauDbgErrorHr function (wiautil.h)
description: The wiauDbgErrorHr function logs a message containing an HRESULT and its error message string.
old-location: image\wiaudbgerrorhr.htm
tech.root: image
ms.assetid: 18d248d9-d447-4d3e-9eaa-f6befb4bef58
ms.date: 05/03/2018
ms.keywords: image.wiaudbgerrorhr, wiauDbgErrorHr, wiauDbgErrorHr function [Imaging Devices], wiauFncs_1400188e-53d1-481c-a470-8a2247b7f34f.xml, wiautil/wiauDbgErrorHr
ms.topic: function
req.header: wiautil.h
req.include-header: Wiautil.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wiautil.h
api_name:
- wiauDbgErrorHr
product:
- Windows
targetos: Windows
req.typenames: 
---

# wiauDbgErrorHr function


## -description


The <b>wiauDbgErrorHr</b> function logs a message containing an HRESULT and its error message string.


## -parameters




### -param hr

Specifies the HRESULT that is to be logged.


### -param fname

Pointer to a string containing the name of the function or method into which the call to <b>wiauDbgDump</b> is inserted.


### -param fmt




### -param param






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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiautil/nf-wiautil-wiaudbgdump">wiauDbgDump</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiautil/nf-wiautil-wiaudbgerror">wiauDbgError</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiautil/nf-wiautil-wiaudbgtrace">wiauDbgTrace</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiautil/nf-wiautil-wiaudbgwarning">wiauDbgWarning</a>
 

 

