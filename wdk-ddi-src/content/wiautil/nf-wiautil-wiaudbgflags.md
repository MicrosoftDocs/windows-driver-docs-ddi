---
UID: NF:wiautil.wiauDbgFlags
title: wiauDbgFlags function
author: windows-driver-content
description: The wiauDbgFlags function determines whether a particular debugging flag is set.
old-location: image\wiaudbgflags.htm
old-project: image
ms.assetid: 2185a1c0-e952-4dbd-b1a9-82339e417774
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: wiauDbgFlags function [Imaging Devices], wiauDbgFlags, image.wiaudbgflags, wiautil/wiauDbgFlags, wiauFncs_db71e773-84d8-40b9-9688-9fa33aad9182.xml
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
-	wiauDbgFlags
product: Windows
targetos: Windows
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---

# wiauDbgFlags function


## -description


The <b>wiauDbgFlags</b> function determines whether a particular debugging flag is set.


## -syntax


````
inline void __stdcall wiauDbgFlags(
   DWORD    flags,
   LPCSTR   prefix,
   LPCSTR   fname,
   LPCSTR   fmt, ...
);
````


## -parameters




### -param flags

Is a set of flags that control which information is placed in the log file or displayed in the debugger. See the <i>flags</i> parameter of <a href="..\wiautil\nf-wiautil-wiaudbgsetflags.md">wiauDbgSetFlags</a> for a list of the flag values.


### -param prefix

Pointer to a string containing a prefix (such as "ERROR " or "WARN ").


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



If message logging to log file, or debugger, or both is enabled and the particular flag in the <i>flags</i> parameter is enabled, this function logs a message containing the strings pointed to by the <i>prefix</i>, <i>fname</i>, and <i>fmt</i> parameters.




## -see-also

<a href="..\wiautil\nf-wiautil-wiaudbgsetflags.md">wiauDbgSetFlags</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiauDbgFlags function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

