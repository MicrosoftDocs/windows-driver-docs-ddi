---
UID: NS:iddcx.IDDCX_TARGET_MODE
title: IDDCX_TARGET_MODE (iddcx.h)
description: Gives information about the target mode signal, including the bandwidth needed for the mode.
old-location: display\iddcx_target_mode.htm
tech.root: display
ms.date: 01/11/2021
keywords: ["IDDCX_TARGET_MODE structure"]
ms.keywords: IDDCX_TARGET_MODE, IDDCX_TARGET_MODE structure [Display Devices], display.iddcx_target_mode, iddcx/IDDCX_TARGET_MODE
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
 - IDDCX_TARGET_MODE
 - iddcx/IDDCX_TARGET_MODE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDDCX_TARGET_MODE
---

# IDDCX_TARGET_MODE structure

## -description

**IDDCX_TARGET_MODE** provides information about the target mode signal, including the bandwidth needed for the mode.

## -struct-fields

### -field Size

Size of the structure, in bytes.

### -field TargetVideoSignalInfo

A [**DISPLAYCONFIG_TARGET_MODE**](/windows/win32/api/wingdi/ns-wingdi-displayconfig_target_mode) structure that describes the display path target mode, including information about the video signal for the display.

### -field RequiredBandwidth

The display pipeline bandwidth required for this mode. The driver reports pipeline bandwidth in **[IDDCX_ADAPTER_CAPS](ns-iddcx-iddcx_adapter_caps.md).MaxDisplayPipelineRate**. The OS will never pick a combination of modes across all targets that exceeds this value.

## -remarks

Using the values reported in [**DISPLAYCONFIG_VIDEO_SIGNAL_INFO**](/windows/win32/api/wingdi/ns-wingdi-displayconfig_video_signal_info) (which is a member of [**DISPLAYCONFIG_TARGET_MODE**](/windows/win32/api/wingdi/ns-wingdi-displayconfig_target_mode)), the desktop update rate will be calculated by the formula ```vSyncFreq / vSyncFreqDivider```, where:

* **vSyncFreq** is the Vsync rate between the indirect display device and the connected monitor
* **vSyncFreqDivider** is used to calculate the rate at which the OS will update the desktop image. This value cannot be zero.

## -see-also

[**IDDCX_ADAPTER_CAPS**](ns-iddcx-iddcx_adapter_caps.md)
