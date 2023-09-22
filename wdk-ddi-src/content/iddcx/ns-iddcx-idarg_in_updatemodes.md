---
UID: NS:iddcx.IDARG_IN_UPDATEMODES
title: IDARG_IN_UPDATEMODES (iddcx.h)
description: Learn more about the IDARG_IN_UPDATEMODES structure.
tech.root: display
ms.date: 09/22/2023
keywords: ["IDARG_IN_UPDATEMODES structure"]
ms.keywords: IDARG_IN_UPDATEMODES, IDARG_IN_UPDATEMODES structure [Display Devices], display.idarg_in_updatemodes, iddcx/IDARG_IN_UPDATEMODES
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
 - IDARG_IN_UPDATEMODES
 - iddcx/IDARG_IN_UPDATEMODES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDARG_IN_UPDATEMODES
---

# IDARG_IN_UPDATEMODES structure

## -description

The **IDARG_IN_UPDATEMODES** structure contains input parameters for the [**IddCxMonitorUpdateModes**](nf-iddcx-iddcxmonitorupdatemodes.md) function.

## -struct-fields

### -field Reason

[in] An [**IDDCX_UPDATE_REASON**](ne-iddcx-iddcx_update_reason.md) value that indicates the reason why the driver is updating the modes.

### -field TargetModeCount

[in] Number of target modes in the buffer that **pTargetModes** points to. **TargetModeCount** can't be zero.

### -field pTargetModes

[in] Pointer to a [**IDDCX_TARGET_MODE**](ns-iddcx-idarg_in_updatemodes.md) structure that contains the target modes the driver supports for this monitor.

## -see-also

[**IDDCX_TARGET_MODE**](ns-iddcx-idarg_in_updatemodes.md)

[**IDDCX_UPDATE_REASON**](ne-iddcx-iddcx_update_reason.md)

[**IddCxMonitorUpdateModes**](nf-iddcx-iddcxmonitorupdatemodes.md)
