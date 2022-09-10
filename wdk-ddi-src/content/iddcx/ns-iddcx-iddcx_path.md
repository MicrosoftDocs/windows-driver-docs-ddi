---
UID: NS:iddcx.IDDCX_PATH
title: IDDCX_PATH (iddcx.h)
description: Call IDDCX_PATH_INIT to initialize this structure.
old-location: display\iddcx_path.htm
tech.root: display
ms.date: 08/09/2022
keywords: ["IDDCX_PATH structure"]
ms.keywords: IDDCX_PATH, IDDCX_PATH structure, IDDCX_PATH structure [Display Devices], IDDCX_PATH structure pointer [Display Devices], IDDCX_PATH structure structure [Display Devices], display.iddcx_path, iddcx/IDDCX_PATH
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
 - IDDCX_PATH
 - iddcx/IDDCX_PATH
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDDCX_PATH
---

# IDDCX_PATH structure

## -description

The operating system provides an **IDDCX_PATH** to the driver for every connected monitor, even if that monitor is not active.

## -struct-fields

### -field Size

Total size of this structure, in bytes.

### -field MonitorObject

An [**IDDCX_MONITOR**](/windows-hardware/drivers/display/iddcx-objects) object with the handle the driver provides to identify the monitor that this path is targeted at.

### -field Flags

A [**IDDCX_PATH_FLAGS**](ne-iddcx-iddcx_path_flags.md) value with flags for this path, like the path's active state and whether it has changed.

### -field TargetVideoSignalInfo

A [**DISPLAYCONFIG_VIDEO_SIGNAL_INFO**](/windows/win32/api/wingdi/ns-wingdi-displayconfig_video_signal_info) structure with details of the target mode signal.

## -remarks

[**DISPLAYCONFIG_VIDEO_SIGNAL_INFO**](/windows/win32/api/wingdi/ns-wingdi-displayconfig_video_signal_info)'s **vSyncFreq** value is the Vsync rate between the Indirect Display device and the connected monitor.  **vSyncFreqDivider** is used to calculate the rate at which the OS will update the desktop image. The desktop update rate will be calculated by the formula: ```vSyncFreq / vSyncFreqDivider```. **vSyncFreqDivider** cannot be zero.
