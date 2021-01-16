---
UID: NS:dispmprt._DXGKARG_GETDISPLAYSTATE_NONINTRUSIVE
title: DXGKARG_GETDISPLAYSTATENONINTRUSIVE
ms.date: 03/24/2020
ms.topic: language-reference
tech.root: display
targetos: Windows
description: The DXGKARG_GETDISPLAYSTATENONINTRUSIVE structure is passed to DxgkDdiGetDisplayStateNonIntrusive during diagnostic data collection.
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
req.typenames: DXGKARG_GETDISPLAYSTATENONINTRUSIVE, *PDXGKARG_GETDISPLAYSTATENONINTRUSIVE
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGKARG_GETDISPLAYSTATE_NONINTRUSIVE
 - PDXGKARG_GETDISPLAYSTATENONINTRUSIVE
 - DXGKARG_GETDISPLAYSTATENONINTRUSIVE
f1_keywords:
 - _DXGKARG_GETDISPLAYSTATE_NONINTRUSIVE
 - dispmprt/_DXGKARG_GETDISPLAYSTATE_NONINTRUSIVE
 - PDXGKARG_GETDISPLAYSTATENONINTRUSIVE
 - dispmprt/PDXGKARG_GETDISPLAYSTATENONINTRUSIVE
 - DXGKARG_GETDISPLAYSTATENONINTRUSIVE
 - dispmprt/DXGKARG_GETDISPLAYSTATENONINTRUSIVE
dev_langs:
 - c++
---

# DXGKARG_GETDISPLAYSTATENONINTRUSIVE structure


## -description

The **DXGKARG_GETDISPLAYSTATENONINTRUSIVE** structure is passed to [**DxgkDdiGetDisplayStateNonIntrusive**](nc-dispmprt-dxgkddi_getdisplaystatenonintrusive.md) during diagnostic data collection.

## -struct-fields

### -field NumOfTargets

The number of targets on which the operating system believes there is a monitor connected with a corresponding VidPnTargetId filled in.

### -field SizeOfDisplayStateNonIntrusiveElement

Size of a [**DXGK_DISPLAYSTATE_NONINTRUSIVE**](ns-dispmprt-dxgk_displaystate_nonintrusive.md) structure, in bytes. Set to ```sizeof(DXGK_DISPLAYSTATE_NONINTRUSIVE)```.

### -field ppDisplayStateNonIntrusive

Pointer to an array of pointers to [**DXGK_DISPLAYSTATE_NONINTRUSIVE**](ns-dispmprt-dxgk_displaystate_nonintrusive.md) structures.

## -remarks

DXGKRNL passes **DXGKARG_GETDISPLAYSTATENONINTRUSIVE** in calls to [**DxgkDdiGetDisplayStateNonIntrusive**](nc-dispmprt-dxgkddi_getdisplaystatenonintrusive.md) during diagnostic data collection.

## -see-also

[**DXGK_DISPLAYSTATE_NONINTRUSIVE**](ns-dispmprt-dxgk_displaystate_nonintrusive.md)

[**DxgkDdiGetDisplayStateNonIntrusive**](nc-dispmprt-dxgkddi_getdisplaystatenonintrusive.md)

