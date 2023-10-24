---
UID: NS:iddcx.IDARG_IN_ADAPTERDISPLAYCONFIGUPDATE2
tech.root: display
title: IDARG_IN_ADAPTERDISPLAYCONFIGUPDATE2
ms.date: 09/22/2023
targetos: Windows
description: Learn about the IDARG_IN_ADAPTERDISPLAYCONFIGUPDATE2 structure.
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
 - IDARG_IN_ADAPTERDISPLAYCONFIGUPDATE2
f1_keywords:
 - IDARG_IN_ADAPTERDISPLAYCONFIGUPDATE2
 - iddcx/IDARG_IN_ADAPTERDISPLAYCONFIGUPDATE2
dev_langs:
 - c++
helpviewer_keywords:
 - IDARG_IN_ADAPTERDISPLAYCONFIGUPDATE2
---

## -description

**IDARG_IN_ADAPTERDISPLAYCONFIGUPDATE2** contains the arguments used in the [**IddCxAdapterDisplayConfigUpdate2**](nf-iddcx-iddcxadapterdisplayconfigupdate2.md) function.

## -struct-fields

### -field PathCount

[in] The number of paths in the pPaths array. **PathCount** can't be zero.

### -field pPaths

[in] Pointer to array of [**IDDCX_DISPLAYCONFIGPATH2**](ns-iddcx-iddcx_displayconfigpath2.md) structures containing path display configuration information.

## -remarks

An indirect display driver (IDD) calls [**IddCxAdapterDisplayConfigUpdate2**](nf-iddcx-iddcxadapterdisplayconfigupdate2.md) when it receives a new display configuration.

For more information about HDR support, see [IddCx version 1.10 updates](/windows-hardware/drivers/display/iddcx1.10-updates).

## -see-also

[**IDDCX_DISPLAYCONFIGPATH2**](ns-iddcx-iddcx_displayconfigpath2.md)

[**IddCxAdapterDisplayConfigUpdate2**](nf-iddcx-iddcxadapterdisplayconfigupdate2.md)
