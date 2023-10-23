---
UID: NS:iddcx.IDARG_IN_QUERYTARGETMODES2
tech.root: display
title: IDARG_IN_QUERYTARGETMODES2
ms.date: 09/22/2023
targetos: Windows
description: Learn more about the IDARG_IN_QUERYTARGETMODES2 structure.
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
 - IDARG_IN_QUERYTARGETMODES2
f1_keywords:
 - IDARG_IN_QUERYTARGETMODES2
 - iddcx/IDARG_IN_QUERYTARGETMODES2
dev_langs:
 - c++
helpviewer_keywords:
 - IDARG_IN_QUERYTARGETMODES2
---

## -description

The **IDARG_IN_QUERYTARGETMODES2** structure contains input arguments for the [**EVT_IDD_CX_MONITOR_QUERY_TARGET_MODES2**](nc-iddcx-evt_idd_cx_monitor_query_target_modes2.md) callback function, which allows a driver to report extra information needed for HDR10 or WCG monitor modes.

## -struct-fields

### -field MonitorDescription

[in] An [**IDDCX_MONITOR_DESCRIPTION**](ns-iddcx-iddcx_monitor_description.md) structure that contains the monitor description.

This might not be the monitor description the driver originally provided in the monitor arrival call, which allows for the monitor description to be updated by the OS.

### -field TargetModeBufferInputCount

[in] The number of target modes that can be held in the buffer that **pTargetModes** points to. If the value is zero, then the driver should not copy the target mode list to **pTargetModes**, but should instead set [**IDARG_OUT_QUERYTARGETMODES**](ns-iddcx-idarg_out_querytargetmodes.md)'s **TargetModeBufferOutputCount** value to indicate the size of buffer required to store the modes.

### -field pTargetModes

[out] Pointer to a buffer of [**IDDCX_TARGET_MODE2**](ns-iddcx-iddcx_target_mode2.md) structures that the driver should copy the target modes it supports for this monitor to if the value is non-NULL. If **pTargetModes** is NULL, then driver shouldn't copy any data and should instead just set [**IDARG_OUT_QUERYTARGETMODES**](ns-iddcx-idarg_out_querytargetmodes.md)'s **TargetModeBufferOutputCount** value to indicate the size of buffer required to store the modes.

## -remarks

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

## -see-also

[**EVT_IDD_CX_MONITOR_QUERY_TARGET_MODES2**](nc-iddcx-evt_idd_cx_monitor_query_target_modes2.md)

[**IDARG_OUT_QUERYTARGETMODES**](ns-iddcx-idarg_out_querytargetmodes.md)

[**IDDCX_MONITOR_DESCRIPTION**](ns-iddcx-iddcx_monitor_description.md)

[**IDDCX_TARGET_MODE2**](ns-iddcx-iddcx_target_mode2.md)
