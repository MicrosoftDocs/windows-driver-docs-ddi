---
UID: NS:iddcx.IDDCX_PATH
title: IDDCX_PATH (iddcx.h)
description: Call IDDCX_PATH_INIT to initialize this structure.
old-location: display\iddcx_path.htm
tech.root: display
ms.assetid: c0126718-6bb0-493c-9fdd-78ae372f8fd4
ms.date: 05/10/2018
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

                 Call <a href="/windows-hardware/drivers/ddi/index">IDDCX_PATH_INIT</a> to initialize this structure.

## -struct-fields

### -field Size

                     Total size of the structure.

### -field MonitorObject

                     The handle the driver provides to identify the monitor this path is targeted at.

### -field Flags

                     Contains flags for this path, like the path's active state and whether it changed.

### -field TargetVideoSignalInfo

The details of the target mode signal.

## -remarks

The <a href="/windows/win32/api/wingdi/ns-wingdi-displayconfig_video_signal_info">DISPLAYCONFIG_VIDEO_SIGNAL_INFO</a> value <b>vSyncFreq</b> is the Vsync rate between the Indirect Display device and the connected monitor.  <b>vSyncFreqDivider</b> is used to calculate the rate at which the OS will update the desktop image.

The desktop update rate will be calculated by the formula: <a href="/windows/win32/api/wingdi/ns-wingdi-displayconfig_video_signal_info">DISPLAYCONFIG_VIDEO_SIGNAL_INFO</a> value <b>vSyncFreq</b>  divided by the <b>DISPLAYCONFIG_VIDEO_SIGNAL_INFO</b> value <b>vSyncFreqDivider</b>. 

The <a href="/windows/win32/api/wingdi/ns-wingdi-displayconfig_video_signal_info">DISPLAYCONFIG_VIDEO_SIGNAL_INFO</a>  value <b>vSyncFreqDivider</b> cannot be zero