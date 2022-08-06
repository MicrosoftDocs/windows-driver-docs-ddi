---
UID: NS:iddcx.IDARG_OUT_QUERY_HWCURSOR2
tech.root: display
title: IDARG_OUT_QUERY_HWCURSOR2
ms.date: 08/05/2022
targetos: Windows
description: Learn more about the IDARG_OUT_QUERY_HWCURSOR2 structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: iddcx.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 22H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDARG_OUT_QUERY_HWCURSOR2
f1_keywords:
 - IDARG_OUT_QUERY_HWCURSOR2
 - iddcx/IDARG_OUT_QUERY_HWCURSOR2
dev_langs:
 - c++
helpviewer_keywords:
 - IDARG_OUT_QUERY_HWCURSOR2
---

## -description

An **IDARG_OUT_QUERY_HWCURSOR2** structure is the output parameter used by [**IddCxMonitorQueryHardwareCursor2**](nf-iddcx-iddcxmonitorqueryhardwarecursor2.md) to return information about the current cursor.

## -struct-fields

### -field IsCursorVisible

[out] A Boolean value that indicates whether the cursor is visible.

### -field X

[out] If the cursor is visible (**IsCursorVisible** = TRUE) then **X** is the *x* screen co-ordinate of the top-left hand pixel in the cursor image. This field is only valid if **PositionValid** is TRUE. See Remarks.

### -field Y

[out] If the cursor is visible (**IsCursorVisible** = TRUE) then **Y** is the *y* screen co-ordinate of the top-left hand pixel in the cursor image. This field is only valid if **PositionValid** is TRUE. See Remarks.

### -field IsCursorShapeUpdated

 [out] A Boolean value that indicates whether the cursor shape has been updated since the last time the driver called [**IddCxMonitorQueryHardwareCursor2**](nf-iddcx-iddcxmonitorqueryhardwarecursor2.md). If it has been updated then the OS updates the **CursorShapeInfo** structure and copies the new cursor image data into the [**IDARG_IN_QUERY_HWCURSOR**](ns-iddcx-idarg_in_query_hwcursor.md).**pShapeBuffer** buffer.

### -field CursorShapeInfo

[out] A [**IDDCX_CURSOR_SHAPE_INFO**](ns-iddcx-iddcx_cursor_shape_info.md) structure in which the OS copies the current cursor information if the cursor is visible. If the cursor is not visible then OS zeroes this structure.

### -field PositionValid

[out] A Boolean value that indicates whether the **X**, **Y**, and **PositionId** fields in this structure are valid.

### -field PositionId

[out] The ID of the last cursor position that the OS received for this monitor. The driver can compare this ID to the last cursor position that it processed to know whether it should process a new position update.

Note that there are cases where the position values might not have changed but the position ID value has changed. In this case the driver should process the position as if it was a new move. **PositionId** is not updated if **IsCursorVisible** changes and is only valid if **PositionValid** is TRUE.

## -remarks

Note that**X** and **Y** can be negative; for example, a hot spot in the center of cursor that is placed in the top-left of the screen.

## -see-also

[**IddCxMonitorQueryHardwareCursor2**](nf-iddcx-iddcxmonitorqueryhardwarecursor2.md)
