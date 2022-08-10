---
UID: NS:iddcx.IDARG_OUT_GETVERSION
title: IDARG_OUT_GETVERSION
ms.date: 08/09/2022
tech.root: display
targetos: Windows
description: The IDARG_OUT_GETVERSION structure is used to store the IddCx (Indirect Display Driver Class eXtension) version.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: iddcx.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDARG_OUT_GETVERSION
f1_keywords:
 - IDARG_OUT_GETVERSION
 - iddcx/IDARG_OUT_GETVERSION
dev_langs:
 - c++
---

## -description

The **IDARG_OUT_GETVERSION** structure identifies the IddCx (Indirect Display Driver Class eXtension) version.

## -struct-fields

### -field IddCxVersion

ULONG value that identifies the IddCx version that the driver is running on. See [IddCx versions](/windows-hardware/drivers/display/iddcx-versions) for a complete list of possible version values.

## -remarks

An ID driver calls [**IddCxGetVersion**](nf-iddcx-iddcxgetversion.md) to determine the IddCx version that the driver is running on.

## -see-also

[IddCx versions](/windows-hardware/drivers/display/iddcx-versions)

[**IddCxGetVersion**](nf-iddcx-iddcxgetversion.md)

[**PFN_IDDCXGETVERSION**](nc-iddcx-pfn_iddcxgetversion.md)
