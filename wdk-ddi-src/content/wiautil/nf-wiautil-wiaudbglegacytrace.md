---
UID: NF:wiautil.wiauDbgLegacyTrace
title: wiauDbgLegacyTrace function
author: windows-driver-content
description: The wiauDbgLegacyTrace function logs a trace message.
old-location: image\wiaudbglegacytrace.htm
old-project: image
ms.assetid: ccbcab46-0af9-4c21-896f-14096f1461bc
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: wiauDbgLegacyTrace function [Imaging Devices], wiauDbgLegacyTrace, wiautil/wiauDbgLegacyTrace, wiauFncs_a780f296-5780-4589-9aa6-1e61ebec013e.xml, image.wiaudbglegacytrace
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wiautil.h
req.include-header: Wiautil.h
req.target-type: Desktop
req.target-min-winverclnt: This function is available in Windows XP and later.
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
-	wiauDbgLegacyTrace
product: Windows
targetos: Windows
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---

# wiauDbgLegacyTrace function


## -description


The <b>wiauDbgLegacyTrace</b> function logs a trace message.


## -syntax


````
inline void __stdcall wiauDbgLegacyTrace(
   LPCSTR   fmt, ...
);
````


## -parameters




### -param fmt

TBD


### -param param

TBD



####### - fmt, ...

Pointer to a format string that specifies a variable argument list, which starts with an ANSI format string containing the message and any conversion specifiers. The ellipsis (...) specifies a variable number of arguments that are to be output.


## -returns


None



## -remarks


The <b>wiauDbgLegacyTrace</b> function is identical to the <a href="..\wiautil\nf-wiautil-wiaudbgtrace.md">wiauDbgTrace</a> function except that the latter has a parameter used to identify the function or method that is active when the function is called.



## -see-also

<a href="..\wiautil\nf-wiautil-wiaudbgtrace.md">wiauDbgTrace</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiauDbgLegacyTrace function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

