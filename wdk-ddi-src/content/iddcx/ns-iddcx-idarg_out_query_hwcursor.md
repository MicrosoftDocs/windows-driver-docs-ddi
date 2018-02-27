---
UID: NS:iddcx.IDARG_OUT_QUERY_HWCURSOR
title: IDARG_OUT_QUERY_HWCURSOR
author: windows-driver-content
description: Gives information about the coordinates and shape of the current cursor.
old-location: display\idarg_out_query_hwcursor.htm
old-project: display
ms.assetid: 813d6aa6-0442-4f30-9fd6-b3aec2e0e11d
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IDARG_OUT_QUERY_HWCURSOR, IDARG_OUT_QUERY_HWCURSOR structure [Display Devices], display.idarg_out_query_hwcursor, iddcx/IDARG_OUT_QUERY_HWCURSOR
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
-	IDARG_OUT_QUERY_HWCURSOR
product: Windows
targetos: Windows
req.typenames: 
---

# IDARG_OUT_QUERY_HWCURSOR structure


## -description



                 Gives information about the coordinates and shape of the current cursor.


## -syntax


````
typedef struct DARG_OUT_QUERY_HWCURSOR {
  BOOL                    IsCursorVisible;
  INT                     X;
  INT                     Y;
  BOOL                    IsCursorShapeUpdated;
  IDDCX_CURSOR_SHAPE_INFO CursorShapeInfo;
} IDARG_OUT_QUERY_HWCURSOR, *IDARG_OUT_QUERY_HWCURSOR;
````


## -struct-fields




### -field IsCursorVisible


                      [out] Indicates if the cursor is visible or not.
                 


### -field X


                     [out] If the cursor is viable, this is the screen coordinate of the top-left hand pixel in the cursor image.

<div class="alert"><b>Note</b>  NOTE : This can be negative. For example, when there is a hot-spot in the center of cursor it is placed in the top-left of the screen</div>
<div> </div>

### -field Y


                     [out] If the cursor is viable, this is the screen coordinate of the top-left hand pixel in the cursor image.

<div class="alert"><b>Note</b>  NOTE : This can be negative. For example, when there is a hot-spot in the center of cursor it is placed in the top-left of the screen</div>
<div> </div>

### -field IsCursorShapeUpdated


                     [out] Indicates if the cursor shape has been updated since the last time the driver was called. If it has been updated, the OS updates the <b>CursorShapeInfo</b> structure and copies the new cursor image data into the <a href="..\iddcx\ns-iddcx-idarg_in_query_hwcursor.md">IDARG_IN_QUERY_HWCURSOR</a> buffer <b>pShapeBuffer</b>.
                 


### -field CursorShapeInfo


                     [out] If the cursor is visible, then the OS copies the current cursor info into this buffer. If the cursor is not visible, the OS zeros this structure.
                 

