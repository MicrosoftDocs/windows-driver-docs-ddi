---
UID: NF:wiautil.wiauDbgLegacyHresult2
title: wiauDbgLegacyHresult2 function
author: windows-driver-content
description: The wiauDbgLegacyHresult2 function logs a default message containing an HRESULT.
old-location: image\wiaudbglegacyhresult2.htm
old-project: image
ms.assetid: 1b73c94b-07a8-4b65-8ed7-d5f1a073c3b2
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: wiauDbgLegacyHresult2 function [Imaging Devices], wiauDbgLegacyHresult2, image.wiaudbglegacyhresult2, wiautil/wiauDbgLegacyHresult2, wiauFncs_b980cd55-047b-4870-9bad-928253d0ce77.xml
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
-	wiautil.h
apiname:
-	wiauDbgLegacyHresult2
product: Windows
targetos: Windows
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---

# wiauDbgLegacyHresult2 function


## -description


The <b>wiauDbgLegacyHresult2</b> function logs a default message containing an HRESULT.


## -syntax


````
inline void __stdcall wiauDbgLegacyHresult2(
  _In_ HINSTANCE hInstance,
       HRESULT   hr
);
````


## -parameters




### -param hInstance [in]

Specifies the handle to the DLL instance.


### -param hr

Specifies the HRESULT to be logged.


## -returns



None




## -remarks



A call to the <b>wiauDbgLegacyHresult2</b> function is equivalent to the following call to the <a href="..\wiautil\nf-wiautil-wiaudbgerrorhr.md">wiauDbgErrorHr</a> function:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>wiauDbgErrorHr(hr, "", "");</pre>
</td>
</tr>
</table></span></div>
That is, only one line is output to the log file and/or debugger. The line has the following form:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>ERROR HRESULT = HRESULT value, Error text for HRESULT </pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wiautil\nf-wiautil-wiaudbgerrorhr.md">wiauDbgErrorHr</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiauDbgLegacyHresult2 function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

