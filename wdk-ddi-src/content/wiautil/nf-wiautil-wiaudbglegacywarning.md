---
UID: NF:wiautil.wiauDbgLegacyWarning
title: wiauDbgLegacyWarning function (wiautil.h)
description: The wiauDbgLegacyWarning function logs a warning message.
old-location: image\wiaudbglegacywarning.htm
tech.root: image
ms.assetid: 5da7c762-ad5c-45bd-aebe-dc3526005569
ms.date: 05/03/2018
ms.keywords: image.wiaudbglegacywarning, wiauDbgLegacyWarning, wiauDbgLegacyWarning function [Imaging Devices], wiauFncs_03dcc80b-0d36-4130-a05d-bb407cd813cb.xml, wiautil/wiauDbgLegacyWarning
f1_keywords:
 - "wiautil/wiauDbgLegacyWarning"
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
- wiauDbgLegacyWarning
product:
- Windows
targetos: Windows
req.typenames: 
---

# wiauDbgLegacyWarning function


## -description


The <b>wiauDbgLegacyWarning</b> function logs a warning message.


## -parameters




### -param fmt




### -param param






####### - fmt, ...

Pointer to a format string that specifies a variable argument list, which starts with an ANSI format string containing the message and any conversion specifiers. The ellipsis (...) specifies a variable number of arguments that are to be output.


## -remarks



The <b>wiauDbgLegacyWarning</b> function is identical to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiautil/nf-wiautil-wiaudbgwarning">wiauDbgWarning</a> function except that the latter has a parameter used to identify the function or method that is active when the function is called.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiautil/nf-wiautil-wiaudbgwarning">wiauDbgWarning</a>
 

 

