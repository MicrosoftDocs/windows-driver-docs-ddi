---
UID: NF:wiautil.wiauDbgLegacyTrace2
title: wiauDbgLegacyTrace2 function (wiautil.h)
description: The wiauDbgLegacyTrace2 function logs a trace message.
old-location: image\wiaudbglegacytrace2.htm
tech.root: image
ms.assetid: 911a7089-d4ac-4da0-8be6-a3a36567635c
ms.date: 05/03/2018
keywords: ["wiauDbgLegacyTrace2 function"]
ms.keywords: image.wiaudbglegacytrace2, wiauDbgLegacyTrace2, wiauDbgLegacyTrace2 function [Imaging Devices], wiauFncs_8fbdcd6b-cb2b-461b-81f0-880675d0124b.xml, wiautil/wiauDbgLegacyTrace2
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
targetos: Windows
req.typenames: 
f1_keywords:
 - wiauDbgLegacyTrace2
 - wiautil/wiauDbgLegacyTrace2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wiautil.h
api_name:
 - wiauDbgLegacyTrace2
---

# wiauDbgLegacyTrace2 function


## -description

The <b>wiauDbgLegacyTrace2</b> function logs a trace message.

## -parameters

### -param hInstance

Specifies the handle to the DLL instance.

### -param fmt

### -param param

####### - fmt, ...

Pointer to a format string that specifies a variable argument list, which starts with an ANSI format string containing the message and any conversion specifiers. The ellipsis (...) specifies a variable number of arguments that are to be output.

## -remarks

The <b>wiauDbgLegacyTrace2</b> function is identical to the <a href="/windows-hardware/drivers/ddi/wiautil/nf-wiautil-wiaudbgtrace">wiauDbgTrace</a> function except that the former has a parameter that specifies the handle to the DLL instance and the latter has a parameter used to identify the function or method that is active when the function is called.

## -see-also

<a href="/windows-hardware/drivers/ddi/wiautil/nf-wiautil-wiaudbgtrace">wiauDbgTrace</a>