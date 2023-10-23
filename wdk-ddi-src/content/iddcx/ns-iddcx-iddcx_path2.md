---
UID: NS:iddcx.IDDCX_PATH2
tech.root: display
title: IDDCX_PATH2
ms.date: 09/22/2023
targetos: Windows
description: Learn more about the IDDCX_PATH2 structure.
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: iddcx.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 22H2 September Update (IddCx version 1.10)
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDDCX_PATH2
f1_keywords:
 - IDDCX_PATH2
 - iddcx/IDDCX_PATH2
dev_langs:
 - c++
helpviewer_keywords:
 - IDDCX_PATH2
---

## -description

The **IDDCX_PATH2** structure describes the mode to be set on a given monitor.

## -struct-fields

### -field Size

Total size of this structure, in bytes.

### -field MonitorObject

An [**IDDCX_MONITOR**](/windows-hardware/drivers/display/iddcx-objects) object with the handle the driver provides to identify the monitor that this path is targeted at.

### -field Flags

A [**IDDCX_PATH_FLAGS**](ne-iddcx-iddcx_path_flags.md) value with flags for this path, such as the path's active state and whether it has changed.

### -field TargetVideoSignalInfo

A [**DISPLAYCONFIG_VIDEO_SIGNAL_INFO**](/windows/win32/api/wingdi/ns-wingdi-displayconfig_video_signal_info) structure with details of the target mode signal. See Remarks.

### -field WireFormatInfo

An [**IDDCX_WIRE_FORMAT_INFO**](ns-iddcx-iddcx_wire_format_info.md) structure with details of the signal to send to the monitor.

## -remarks

The OS provides an **IDDCX_PATH2** to the driver for every connected monitor, even if that monitor is not active.

[**DISPLAYCONFIG_VIDEO_SIGNAL_INFO**](/windows/win32/api/wingdi/ns-wingdi-displayconfig_video_signal_info)'s **vSyncFreq** value is the Vsync rate between the Indirect Display device and the connected monitor.  **vSyncFreqDivider** is used to calculate the rate at which the OS will update the desktop image. The desktop update rate will be calculated by the formula: ```vSyncFreq / vSyncFreqDivider```. **vSyncFreqDivider** cannot be zero.

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

## -see-also

[**EVT_IDD_CX_ADAPTER_COMMIT_MODES2**](nc-iddcx-evt_idd_cx_adapter_commit_modes2.md)

[**IDARG_IN_COMMITMODES2**](ns-iddcx-idarg_in_commitmodes2.md)
