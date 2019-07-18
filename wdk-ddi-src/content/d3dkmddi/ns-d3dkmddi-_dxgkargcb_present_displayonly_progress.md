---
UID: NS:d3dkmddi._DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS
title: _DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS (d3dkmddi.h)
description: Provides the progress of a kernel mode display-only driver's (KMDOD) present operation that was requested by the operating system.
old-location: display\dxgkargcb_present_displayonly_progress.htm
ms.assetid: c3849df0-0794-43fe-ba29-6daa8461cd9a
ms.date: 05/10/2018
ms.keywords: DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS, DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS structure [Display Devices], _DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS, d3dkmddi/DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS, display.dxgkargcb_present_displayonly_progress
ms.topic: struct
f1_keywords:
 - "d3dkmddi/DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS"
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3dkmddi.h
api_name:
- DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS
---

# _DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS structure


## -description


Provides the progress of a kernel mode display-only driver's (KMDOD) present operation that was requested by the operating system.


## -struct-fields




### -field VidPnSourceId

An integer that identifies a video present source.


### -field ProgressId

A value of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ne-d3dkmddi-_dxgk_present_display_only_progress_id">DXGK_PRESENT_DISPLAY_ONLY_PROGRESS_ID</a> that represents the status of the current present operation.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ne-d3dkmddi-_dxgk_present_display_only_progress_id">DXGK_PRESENT_DISPLAY_ONLY_PROGRESS_ID</a>
 

 

