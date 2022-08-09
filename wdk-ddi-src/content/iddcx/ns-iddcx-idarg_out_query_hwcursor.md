---
UID: NS:iddcx.IDARG_OUT_QUERY_HWCURSOR
title: IDARG_OUT_QUERY_HWCURSOR (iddcx.h)
description: Gives information about the coordinates and shape of the current cursor.
old-location: display\idarg_out_query_hwcursor.htm
tech.root: display
ms.date: 08/05/2022
keywords: ["IDARG_OUT_QUERY_HWCURSOR structure"]
ms.keywords: IDARG_OUT_QUERY_HWCURSOR, IDARG_OUT_QUERY_HWCURSOR structure [Display Devices], display.idarg_out_query_hwcursor, iddcx/IDARG_OUT_QUERY_HWCURSOR
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
 - IDARG_OUT_QUERY_HWCURSOR
 - iddcx/IDARG_OUT_QUERY_HWCURSOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDARG_OUT_QUERY_HWCURSOR
---

# IDARG_OUT_QUERY_HWCURSOR structure

## -description

The **IDARG_OUT_QUERY_HWCURSOR** structure is the output parameter used by [**IddCxMonitorQueryHardwareCursor**] (nf-iddcx-iddcxmonitorqueryhardwarecursor.md) to return information about the coordinates and shape of the current cursor.

## -struct-fields

### -field IsCursorVisible

[out] A Boolean value that indicates whether the cursor is visible.

### -field X

[out] If the cursor is visible (**IsCursorVisible** = TRUE) then **X** is the *x* screen co-ordinate of the top-left hand pixel in the cursor image. See Remarks.

### -field Y

[out] If the cursor is visible (**IsCursorVisible** = TRUE) then **Y** is the *y* screen co-ordinate of the top-left hand pixel in the cursor image. See Remarks.

### -field IsCursorShapeUpdated

 [out] A Boolean value that indicates whether the cursor shape has been updated since the last time the driver called [**IddCxMonitorQueryHardwareCursor**](nf-iddcx-iddcxmonitorqueryhardwarecursor.md). If it has been updated then the OS updates the **CursorShapeInfo** structure and copies the new cursor image data into the [**IDARG_IN_QUERY_HWCURSOR**](ns-iddcx-idarg_in_query_hwcursor.md).**pShapeBuffer** buffer.

### -field CursorShapeInfo

[out] A [**IDDCX_CURSOR_SHAPE_INFO**](ns-iddcx-iddcx_cursor_shape_info.md) structure in which the OS copies the current cursor information if the cursor is visible. If the cursor is not visible then OS zeroes this structure.

## -remarks

Note that**X** and **Y** can be negative; for example, a hot spot in the center of cursor that is placed in the top-left of the screen.

## -see-also

[**IddCxMonitorQueryHardwareCursor**](nf-iddcx-iddcxmonitorqueryhardwarecursor.md)

[**IddCxMonitorQueryHardwareCursor2**](nf-iddcx-iddcxmonitorqueryhardwarecursor2.md)
