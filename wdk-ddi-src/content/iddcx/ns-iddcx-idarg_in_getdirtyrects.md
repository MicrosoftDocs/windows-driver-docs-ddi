---
UID: NS:iddcx.IDARG_IN_GETDIRTYRECTS
title: IDARG_IN_GETDIRTYRECTS (iddcx.h)
description: Gives information about the parts of the surface that have changed since the last present.
old-location: display\idarg_in_getdirtyrects.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["IDARG_IN_GETDIRTYRECTS structure"]
ms.keywords: IDARG_IN_GETDIRTYRECTS, IDARG_IN_GETDIRTYRECTS structure [Display Devices], display.idarg_in_getdirtyrects, iddcx/IDARG_IN_GETDIRTYRECTS
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
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
 - IDARG_IN_GETDIRTYRECTS
 - iddcx/IDARG_IN_GETDIRTYRECTS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDARG_IN_GETDIRTYRECTS
---

# IDARG_IN_GETDIRTYRECTS structure


## -description

             
         Gives information about the parts of the surface that have changed since the last present.

## -struct-fields

### -field DirtyRectInCount

                     [in] Number of dirty rects in the <b>pDirtyRects</b> array

### -field pDirtyRects

                     [out] Pointer to the buffer where the OS can copy the dirty rects that indicate which parts of the surface have been changed since the last present.

