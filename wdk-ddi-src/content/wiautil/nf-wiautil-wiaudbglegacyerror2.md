---
UID: NF:wiautil.wiauDbgLegacyError2
title: wiauDbgLegacyError2 function
author: windows-driver-content
description: The wiauDbgLegacyError2 function logs an error message.
old-location: image\wiaudbglegacyerror2.htm
old-project: image
ms.assetid: 981fef6c-65a7-4ba1-ad6a-c7c9c2795feb
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: wiauDbgLegacyError2, image.wiaudbglegacyerror2, wiauFncs_647f5e2c-bcc7-4e9a-9746-2f0685f29fcf.xml, wiautil/wiauDbgLegacyError2, wiauDbgLegacyError2 function [Imaging Devices]
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
-	wiauDbgLegacyError2
product: Windows
targetos: Windows
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---

# wiauDbgLegacyError2 function


## -description


The <b>wiauDbgLegacyError2</b> function logs an error message.


## -syntax


````
inline void __stdcall wiauDbgLegacyError2(
   HINSTANCE   hInstance,
   LPCSTR      fmt, ...
);
````


## -parameters




### -param hInstance

Specifies the handle to the DLL instance.


### -param fmt

TBD


### -param param

TBD




####### - fmt, ...

Pointer to a format string that specifies a variable argument list, which starts with an ANSI format string containing the message and any conversion specifiers. 


## -returns



None




## -remarks



The <b>wiauDbgLegacyError2</b> function is identical to the <a href="..\wiautil\nf-wiautil-wiaudbgerror.md">wiauDbgError</a> function except that the former has a parameter that specifies the handle to the DLL instance and the latter has a parameter used to identify the function or method that is active when the function is called.




## -see-also

<a href="..\wiautil\nf-wiautil-wiaudbgerror.md">wiauDbgError</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiauDbgLegacyError2 function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

