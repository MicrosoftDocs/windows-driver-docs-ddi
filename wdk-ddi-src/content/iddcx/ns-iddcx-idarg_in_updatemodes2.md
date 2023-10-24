---
UID: NS:iddcx.IDARG_IN_UPDATEMODES2
tech.root: display
title: IDARG_IN_UPDATEMODES2
ms.date: 09/22/2023
targetos: Windows
description: Learn more about the IDARG_IN_UPDATEMODES2 structure.
prerelease: false
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
 - IDARG_IN_UPDATEMODES2
f1_keywords:
 - IDARG_IN_UPDATEMODES2
 - iddcx/IDARG_IN_UPDATEMODES2
dev_langs:
 - c++
helpviewer_keywords:
 - IDARG_IN_UPDATEMODES2
---

## -description

The **IDARG_IN_UPDATEMODES2** structure contains input parameters for the [**IddCxMonitorUpdateModes2**](nf-iddcx-iddcxmonitorupdatemodes2.md) function.

## -struct-fields

### -field Reason

[in] An [**IDDCX_UPDATE_REASON**](ne-iddcx-iddcx_update_reason.md) value that indicates the reason why the driver is updating the modes.

### -field TargetModeCount

[in] Number of target modes in the buffer that **pTargetModes** points to. **TargetModeCount** can't be zero.

### -field pTargetModes

[in] Pointer to a [**IDDCX_TARGET_MODE2**](ns-iddcx-idarg_in_updatemodes2.md) structure that contains the target modes the driver supports for this monitor.

## -remarks

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

## -see-also

[**IDDCX_TARGET_MODE2**](ns-iddcx-idarg_in_updatemodes2.md)

[**IDDCX_UPDATE_REASON**](ne-iddcx-iddcx_update_reason.md)

[**IddCxMonitorUpdateModes2**](nf-iddcx-iddcxmonitorupdatemodes2.md)
