---
UID: NS:dispmprt._DXGKARG_GETDISPLAYSTATE_INTRUSIVE
title: DXGKARG_GETDISPLAYSTATEINTRUSIVE
ms.date: 03/24/2020
ms.topic: language-reference
tech.root: display
targetos: Windows
description: The DXGKARG_GETDISPLAYSTATEINTRUSIVE structure is passed to DxgkDdiGetDisplayStateIntrusive during diagnostic data collection.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: dispmprt.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGKARG_GETDISPLAYSTATEINTRUSIVE, *PDXGKARG_GETDISPLAYSTATEINTRUSIVE
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGKARG_GETDISPLAYSTATE_INTRUSIVE
 - PDXGKARG_GETDISPLAYSTATEINTRUSIVE
 - DXGKARG_GETDISPLAYSTATEINTRUSIVE
f1_keywords:
 - _DXGKARG_GETDISPLAYSTATE_INTRUSIVE
 - dispmprt/_DXGKARG_GETDISPLAYSTATE_INTRUSIVE
 - PDXGKARG_GETDISPLAYSTATEINTRUSIVE
 - dispmprt/PDXGKARG_GETDISPLAYSTATEINTRUSIVE
 - DXGKARG_GETDISPLAYSTATEINTRUSIVE
 - dispmprt/DXGKARG_GETDISPLAYSTATEINTRUSIVE
dev_langs:
 - c++
---

# DXGKARG_GETDISPLAYSTATEINTRUSIVE structure


## -description

The **DXGKARG_GETDISPLAYSTATEINTRUSIVE** structure is passed to [**DxgkDdiGetDisplayStateIntrusive**](nc-dispmprt-dxgkddi_getdisplaystateintrusive.md) during diagnostic data collection.

## -struct-fields

### -field NumOfTargets

The number of targets on which the operating system believes there is a monitor connected with a corresponding VidPnTargetId filled in.

### -field SizeOfDisplayStateIntrusiveElement

Size of a [**DXGK_DISPLAYSTATE_INTRUSIVE**](ns-dispmprt-dxgk_displaystate_intrusive.md) structure, in bytes. Set to ```sizeof(DXGK_DISPLAYSTATE_INTRUSIVE)```.

### -field ppDisplayStateIntrusive

Pointer to an array of pointers to [**DXGK_DISPLAYSTATE_INTRUSIVE**](ns-dispmprt-dxgk_displaystate_intrusive.md) structures.

## -remarks

DXGKRNL passes **DXGKARG_GETDISPLAYSTATEINTRUSIVE** in calls to [**DxgkDdiGetDisplayStateIntrusive**](nc-dispmprt-dxgkddi_getdisplaystateintrusive.md) during diagnostic data collection.

## -see-also

[**DXGK_DISPLAYSTATE_INTRUSIVE**](ns-dispmprt-dxgk_displaystate_intrusive.md)

[**DxgkDdiGetDisplayStateIntrusive**](nc-dispmprt-dxgkddi_getdisplaystateintrusive.md)

