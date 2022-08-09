---
UID: NE:iddcx.IDDCX_FRAME_STATISTICS_STEP_TYPE
title: IDDCX_FRAME_STATISTICS_STEP_TYPE (iddcx.h)
description: Defines the type of frame processing step.
old-location: display\iddcx_frame_statistics_step_type.htm
tech.root: display
ms.date: 08/08/2022
keywords: ["IDDCX_FRAME_STATISTICS_STEP_TYPE enumeration"]
ms.keywords: IDDCX_FRAME_STATISTICS_STEP_TYPE, IDDCX_FRAME_STATISTICS_STEP_TYPE enumeration [Display Devices], IDDCX_FRAME_STATISTICS_STEP_TYPE_COLOR_CONVERT_END, IDDCX_FRAME_STATISTICS_STEP_TYPE_COLOR_CONVERT_START, IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_1, IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_10, IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_2, IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_3, IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_4, IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_5, IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_6, IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_7, IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_8, IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_9, IDDCX_FRAME_STATISTICS_STEP_TYPE_ENCODE_END, IDDCX_FRAME_STATISTICS_STEP_TYPE_ENCODE_START, IDDCX_FRAME_STATISTICS_STEP_TYPE_ENCRYPT_END, IDDCX_FRAME_STATISTICS_STEP_TYPE_ENCRYPT_START, IDDCX_FRAME_STATISTICS_STEP_TYPE_MUX_END, IDDCX_FRAME_STATISTICS_STEP_TYPE_MUX_START, IDDCX_FRAME_STATISTICS_STEP_TYPE_UNINITIALIZED, display.iddcx_frame_statistics_step_type, iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE, iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE_COLOR_CONVERT_END, iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE_COLOR_CONVERT_START, iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_1, iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_10, iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_2, iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_3, iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_4, iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_5, iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_6, iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_7, iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_8, iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_9, iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE_ENCODE_END, iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE_ENCODE_START, iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE_ENCRYPT_END, iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE_ENCRYPT_START, iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE_MUX_END, iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE_MUX_START, iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE_UNINITIALIZED
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
 - IDDCX_FRAME_STATISTICS_STEP_TYPE
 - iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDDCX_FRAME_STATISTICS_STEP_TYPE
---

# IDDCX_FRAME_STATISTICS_STEP_TYPE enumeration

## -description

A **IDDCX_FRAME_STATISTICS_STEP_TYPE** value defines the type of frame processing step.

## -enum-fields

### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_UNINITIALIZED

Indicates that an **IDDCX_FRAME_STATISTICS_STEP_TYPE** variable has not yet been assigned a meaningful value.

### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_COLOR_CONVERT_START

Marks the start of a color convert operation.

### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_COLOR_CONVERT_END

Marks the end of a color convert operation.

### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_ENCODE_START

Marks the start of a encode operation.

### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_ENCODE_END

Marks the end of a encode operation.

### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_ENCRYPT_START

Marks the start of an encrypt operation.

### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_ENCRYPT_END

Marks the end of an encrypt operation.

### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_MUX_START

Marks the start of a mux'ing operation.

### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_MUX_END

Marks the end of a mux'ing operation.

### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_1:0x100

Driver-defined processing step point. See Remarks.

### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_2:0x101

Driver-defined processing step point. See Remarks.

### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_3:0x102

Driver-defined processing step point. See Remarks.

### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_4:0x103

Driver-defined processing step point. See Remarks.

### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_5:0x104

Driver-defined processing step point. See Remarks.

### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_6:0x105

Driver-defined processing step point. See Remarks.

### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_7:0x106

Driver-defined processing step point. See Remarks.

### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_8:0x107

Driver-defined processing step point. See Remarks.

### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_9:0x108

Driver-defined processing step point. See Remarks.

### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_10:0x109

Driver-defined processing step point. See Remarks.

### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_256:0x1FF

Driver-defined processing step point. See Remarks.

### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_START_INTERVAL_1:0x200

Driver-defined processing step start interval. See Remarks.

### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_END_INTERVAL_1:0x300

Driver-defined processing step end interval. See Remarks.

### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_START_INTERVAL_2:0x201

Driver-defined processing step start interval. See Remarks.

### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_END_INTERVAL_2:0x301

Driver-defined processing step end interval. See Remarks.

### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_START_INTERVAL_3:0x202

Driver-defined processing step start interval. See Remarks.

### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_END_INTERVAL_3:0x302

Driver-defined processing step end interval. See Remarks.

### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_START_INTERVAL_256:0x2FF

Driver-defined processing step start interval. See Remarks.

### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_END_INTERVAL_256:0x3FF

Driver-defined processing step end interval. See Remarks.

## -remarks

For driver-defined processing step points, there are 256 single point events that a driver can use, where each event records a single QPC time. Valid driver values are 0x100-0x1FF.

For driver-defined processing step intervals, there are 256 different intervals, each with a defined start and end point. It is invalid to report either start or end without the other or for the start step to have a QPC time after the QPC time in the end step. Valid start step values are 0x200 - 0x2FFF. Valid end step values are 0x300 - 0x3FFF.

## -see-also

[**IDDCX_FRAME_STATISTICS_STEP**](ns-iddcx-iddcx_frame_statistics_step.md)
