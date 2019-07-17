---
UID: NF:wiautil.wiauDbgLegacyError
title: wiauDbgLegacyError function (wiautil.h)
description: The wiauDbgLegacyError function logs an error message.
old-location: image\wiaudbglegacyerror.htm
tech.root: image
ms.assetid: c2a9bd35-ce3a-4640-9982-b470e98b4692
ms.date: 05/03/2018
ms.keywords: image.wiaudbglegacyerror, wiauDbgLegacyError, wiauDbgLegacyError function [Imaging Devices], wiauFncs_03e81269-0a09-42c4-8d0d-1f808e6ef69e.xml, wiautil/wiauDbgLegacyError
ms.topic: function
f1_keywords:
 - "wiautil/wiauDbgLegacyError"
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
- wiauDbgLegacyError
product:
- Windows
targetos: Windows
req.typenames: 
---

# wiauDbgLegacyError function


## -description


The <b>wiauDbgLegacyError</b> function logs an error message.


## -parameters




### -param fmt




### -param param






####### - fmt, ...

Pointer to a format string that specifies a variable argument list, which starts with an ANSI format string containing the message and any conversion specifiers. The ellipsis (...) specifies a variable number of arguments that are to be output.


## -returns



None




## -remarks



The <b>wiauDbgLegacyError</b> function is identical to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiautil/nf-wiautil-wiaudbgerror">wiauDbgError</a> function except that the latter function has an additional parameter used to identify the function or method that is active when the function is called.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiautil/nf-wiautil-wiaudbgerror">wiauDbgError</a>
 

 

