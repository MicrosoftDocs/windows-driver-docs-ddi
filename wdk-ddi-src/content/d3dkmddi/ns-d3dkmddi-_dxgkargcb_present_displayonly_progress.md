---
UID: NS:d3dkmddi._DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS
title: DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS (d3dkmddi.h)
description: Provides the progress of a kernel mode display-only driver's (KMDOD) present operation that was requested by the operating system.
old-location: display\dxgkargcb_present_displayonly_progress.htm
ms.date: 10/13/2021
keywords: ["DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS structure"]
ms.keywords: DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS, DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS structure [Display Devices], _DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS, d3dkmddi/DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS, display.dxgkargcb_present_displayonly_progress
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8 (WDDM 1.2)
req.target-min-winversvr: Windows Server 2012
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
tech.root: display
req.typenames: DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS
f1_keywords:
 - _DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS
 - d3dkmddi/_DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS
 - DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS
 - d3dkmddi/DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dkmddi.h
api_name:
 - _DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS
 - DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS
---

# DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS structure

## -description

The **DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS** structure provides the progress of a kernel-mode display-only driver's (KMDOD) present operation that was requested by the operating system.

## -struct-fields

### -field VidPnSourceId

An integer that identifies a video present source.

### -field ProgressId

A value of type [**DXGK_PRESENT_DISPLAY_ONLY_PROGRESS_ID**](ne-d3dkmddi-_dxgk_present_display_only_progress_id.md) that represents the status of the current present operation.

## -see-also

[**DXGK_PRESENT_DISPLAY_ONLY_PROGRESS_ID**](ne-d3dkmddi-_dxgk_present_display_only_progress_id.md)

[**DXGKARGCB_NOTIFY_INTERRUPT_DATA**](ns-d3dkmddi-_dxgkargcb_notify_interrupt_data.md)
