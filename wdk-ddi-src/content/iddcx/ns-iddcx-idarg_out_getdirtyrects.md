---
UID: NS:iddcx.IDARG_OUT_GETDIRTYRECTS
title: IDARG_OUT_GETDIRTYRECTS
author: windows-driver-content
description: Gives information about the recs that have changed on the surface since the last load.
old-location: display\idarg_out_getdirtyrects.htm
old-project: display
ms.assetid: 4116be18-e98e-4778-b0aa-753c1ca79d32
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: IDARG_OUT_GETDIRTYRECTS structure [Display Devices], iddcx/IDARG_OUT_GETDIRTYRECTS, IDARG_OUT_GETDIRTYRECTS, display.idarg_out_getdirtyrects
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	iddcx.h
apiname:
-	IDARG_OUT_GETDIRTYRECTS
product: Windows
targetos: Windows
req.typenames: 
---

# IDARG_OUT_GETDIRTYRECTS structure


## -description



                 Gives information about the recs 
             that have changed on the surface since the last load.


## -syntax


````
typedef struct IDARG_OUT_GETDIRTYRECTS {
  UINT DirtyRectOutCount;
} IDARG_OUT_GETDIRTYRECTS, *IDARG_OUT_GETDIRTYRECTS;
````


## -struct-fields




### -field DirtyRectOutCount


                     [out] Number of dirty rects the OS copied into the <b>pDirtyRects</b> array.

