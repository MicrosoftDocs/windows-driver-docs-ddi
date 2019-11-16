---
UID: NF:wiautil.wiauDbgLegacyTrace
title: wiauDbgLegacyTrace function (wiautil.h)
description: The wiauDbgLegacyTrace function logs a trace message.
old-location: image\wiaudbglegacytrace.htm
tech.root: image
ms.assetid: ccbcab46-0af9-4c21-896f-14096f1461bc
ms.date: 09/07/2018
ms.keywords: image.wiaudbglegacytrace, wiauDbgLegacyTrace, wiauDbgLegacyTrace function [Imaging Devices], wiauFncs_a780f296-5780-4589-9aa6-1e61ebec013e.xml, wiautil/wiauDbgLegacyTrace
ms.topic: function
f1_keywords:
 - "wiautil/wiauDbgLegacyTrace"
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
- wiauDbgLegacyTrace
product:
- Windows
targetos: Windows
req.typenames: 
---

# wiauDbgLegacyTrace function


## -description


The <b>wiauDbgLegacyTrace</b> function logs a trace message.


## -parameters




### -param fmt




### -param param






####### - fmt, ...

Pointer to a format string that specifies a variable argument list, which starts with an ANSI format string containing the message and any conversion specifiers. The ellipsis (...) specifies a variable number of arguments that are to be output.


## -remarks



The <b>wiauDbgLegacyTrace</b> function is identical to the [wiauDbgTrace](nf-wiautil-wiaudbgtrace.md) function except that the latter has a parameter used to identify the function or method that is active when the function is called.




## -see-also

[wiauDbgTrace](nf-wiautil-wiaudbgtrace.md)
