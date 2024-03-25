---
UID: NS:iddcx.IDARG_IN_QUERYTARGETMODES
title: IDARG_IN_QUERYTARGETMODES (iddcx.h)
description: Learn more about the IDARG_IN_QUERYTARGETMODES structure.
tech.root: display
ms.date: 09/22/2023
keywords: ["IDARG_IN_QUERYTARGETMODES structure"]
ms.keywords: IDARG_IN_QUERYTARGETMODES, IDARG_IN_QUERYTARGETMODES structure [Display Devices], display.idarg_in_querytargetmodes, iddcx/IDARG_IN_QUERYTARGETMODES
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
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
 - IDARG_IN_QUERYTARGETMODES
 - iddcx/IDARG_IN_QUERYTARGETMODES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDARG_IN_QUERYTARGETMODES
---

# IDARG_IN_QUERYTARGETMODES structure

## -description

The **IDARG_IN_QUERYTARGETMODES** structure contains input arguments for the [**EVT_IDD_CX_MONITOR_QUERY_TARGET_MODES**](nc-iddcx-evt_idd_cx_monitor_query_target_modes.md) callback function.

## -struct-fields

### -field MonitorDescription

[in] An [**IDDCX_MONITOR_DESCRIPTION**](ns-iddcx-iddcx_monitor_description.md) structure that contains the monitor description.

This might not be the monitor description the driver originally provided in the monitor arrival call, which allows for the monitor description to be updated by the OS.

### -field TargetModeBufferInputCount

[in] The number of target modes that can be held in the buffer that **pTargetModes** points to. If the value is zero, then the driver should not copy the target mode list to **pTargetModes**, but should instead set [**IDARG_OUT_QUERYTARGETMODES**](ns-iddcx-idarg_out_querytargetmodes.md)'s **TargetModeBufferOutputCount** value to indicate the size of buffer required to store the modes.

### -field pTargetModes

[out] Pointer to a buffer of [**IDDCX_TARGET_MODE**](ns-iddcx-iddcx_target_mode.md) structures that the driver should copy the target modes it supports for this monitor to if the value is non-NULL. If **pTargetModes** is NULL, then driver shouldn't copy any data and should instead just set [**IDARG_OUT_QUERYTARGETMODES**](ns-iddcx-idarg_out_querytargetmodes.md)'s **TargetModeBufferOutputCount** value to indicate the size of buffer required to store the modes.

## -see-also

[**EVT_IDD_CX_MONITOR_QUERY_TARGET_MODES**](nc-iddcx-evt_idd_cx_monitor_query_target_modes.md)

[**IDARG_OUT_QUERYTARGETMODES**](ns-iddcx-idarg_out_querytargetmodes.md)

[**IDDCX_MONITOR_DESCRIPTION**](ns-iddcx-iddcx_monitor_description.md)

[**IDDCX_TARGET_MODE**](ns-iddcx-iddcx_target_mode.md)
