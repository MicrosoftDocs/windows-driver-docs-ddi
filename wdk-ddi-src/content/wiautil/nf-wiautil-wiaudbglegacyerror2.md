---
UID: NF:wiautil.wiauDbgLegacyError2
title: wiauDbgLegacyError2 function (wiautil.h)
description: The wiauDbgLegacyError2 function logs an error message.
old-location: image\wiaudbglegacyerror2.htm
tech.root: image
ms.assetid: 981fef6c-65a7-4ba1-ad6a-c7c9c2795feb
ms.date: 05/03/2018
ms.keywords: image.wiaudbglegacyerror2, wiauDbgLegacyError2, wiauDbgLegacyError2 function [Imaging Devices], wiauFncs_647f5e2c-bcc7-4e9a-9746-2f0685f29fcf.xml, wiautil/wiauDbgLegacyError2
f1_keywords:
 - "wiautil/wiauDbgLegacyError2"
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
- wiauDbgLegacyError2
product:
- Windows
targetos: Windows
req.typenames: 
---

# wiauDbgLegacyError2 function


## -description


The <b>wiauDbgLegacyError2</b> function logs an error message.


## -parameters




### -param hInstance

Specifies the handle to the DLL instance.


### -param fmt




### -param param






####### - fmt, ...

Pointer to a format string that specifies a variable argument list, which starts with an ANSI format string containing the message and any conversion specifiers. 


## -remarks



The <b>wiauDbgLegacyError2</b> function is identical to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiautil/nf-wiautil-wiaudbgerror">wiauDbgError</a> function except that the former has a parameter that specifies the handle to the DLL instance and the latter has a parameter used to identify the function or method that is active when the function is called.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiautil/nf-wiautil-wiaudbgerror">wiauDbgError</a>
 

 

