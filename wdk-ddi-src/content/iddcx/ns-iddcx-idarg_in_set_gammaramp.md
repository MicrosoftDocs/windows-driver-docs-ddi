---
UID: NS:iddcx.IDARG_IN_SET_GAMMARAMP
title: IDARG_IN_SET_GAMMARAMP (iddcx.h)
description: Learn more about the IDARG_IN_SET_GAMMARAMP structure.
tech.root: display
ms.date: 09/22/2023
keywords: ["IDARG_IN_SET_GAMMARAMP structure"]
ms.keywords: IDARG_IN_SET_GAMMARAMP, IDARG_IN_SET_GAMMARAMP structure [Display Devices], display.idarg_in_set_gammaramp, iddcx/IDARG_IN_SET_GAMMARAMP
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
 - IDARG_IN_SET_GAMMARAMP
 - iddcx/IDARG_IN_SET_GAMMARAMP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDARG_IN_SET_GAMMARAMP
---

# IDARG_IN_SET_GAMMARAMP structure

## -description

The OS passes an **IDARG_IN_SET_GAMMARAMP** structure to [**EVT_IDD_CX_MONITOR_SET_GAMMA_RAMP**](nc-iddcx-evt_idd_cx_monitor_set_gamma_ramp.md) with input information about the gamma ramp being set.

## -struct-fields

### -field Type

[in] A [**IDDCX_GAMMARAMP_TYPE**](ne-iddcx-iddcx_gammaramp_type.md) value that specifies the type of gamma ramp being set.

### -field GammaRampSizeInBytes

[in] Size in bytes of the provided gamma ramp data that **pGammaRampData** points to. Set to zero for [**IDDCX_GAMMARAMP_TYPE_DEFAULT**](ne-iddcx-iddcx_gammaramp_type.md).

### -field pGammaRampData

[in] Pointer to the gamma ramp data to set. The driver should cast this field based on the gamma ramp **Type**. **pGammaRampData** is set to NULL for [**IDDCX_GAMMARAMP_TYPE_DEFAULT**](ne-iddcx-iddcx_gammaramp_type.md).

## -see-also

[**EVT_IDD_CX_MONITOR_SET_GAMMA_RAMP**](nc-iddcx-evt_idd_cx_monitor_set_gamma_ramp.md)

[**IDDCX_GAMMARAMP_TYPE**](ne-iddcx-iddcx_gammaramp_type.md)
