---
UID: NS:iddcx.IDARG_OUT_QUERYTARGETMODES
title: IDARG_OUT_QUERYTARGETMODES (iddcx.h)
description: Learn more about the IDARG_OUT_QUERYTARGETMODES structure.
tech.root: display
ms.date: 09/22/2023
keywords: ["IDARG_OUT_QUERYTARGETMODES structure"]
ms.keywords: IDARG_OUT_QUERYTARGETMODES, IDARG_OUT_QUERYTARGETMODES structure [Display Devices], display.idarg_out_querytargetmodes, iddcx/IDARG_OUT_QUERYTARGETMODES
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
 - IDARG_OUT_QUERYTARGETMODES
 - iddcx/IDARG_OUT_QUERYTARGETMODES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDARG_OUT_QUERYTARGETMODES
---

# IDARG_OUT_QUERYTARGETMODES structure

## -description

The **IDARG_OUT_QUERYTARGETMODES** structure contains output arguments for the [**EVT_IDD_CX_MONITOR_QUERY_TARGET_MODES**](nc-iddcx-evt_idd_cx_monitor_query_target_modes.md) and [**EVT_IDD_CX_MONITOR_QUERY_TARGET_MODES2**](nc-iddcx-evt_idd_cx_monitor_query_target_modes2.md) callback functions.

## -struct-fields

### -field TargetModeBufferOutputCount

[out] If the OS provides the number of target modes, the driver sets this to that value. See [**IDARG_IN_QUERYTARGETMODES**](ns-iddcx-idarg_in_querytargetmodes.md) for more information.

## -see-also

[**IDARG_IN_QUERYTARGETMODES**](ns-iddcx-idarg_in_querytargetmodes.md)
