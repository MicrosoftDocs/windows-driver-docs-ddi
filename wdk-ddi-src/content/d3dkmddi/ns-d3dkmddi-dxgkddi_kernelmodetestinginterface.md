---
UID: NS:d3dkmddi._DXGKDDI_KERNELMODETESTINGINTERFACE
tech.root: display
title: DXGKDDI_KERNELMODETESTINGINTERFACE
ms.date: 06/17/2024
targetos: Windows
description: Learn about the DXGKDDI_KERNELMODETESTINGINTERFACE structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGKDDI_KERNELMODETESTINGINTERFACE
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKDDI_KERNELMODETESTINGINTERFACE
 - DXGKDDI_KERNELMODETESTINGINTERFACE
f1_keywords:
 - _DXGKDDI_KERNELMODETESTINGINTERFACE
 - d3dkmddi/_DXGKDDI_KERNELMODETESTINGINTERFACE
 - DXGKDDI_KERNELMODETESTINGINTERFACE
 - d3dkmddi/DXGKDDI_KERNELMODETESTINGINTERFACE
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKDDI_KERNELMODETESTINGINTERFACE
---

## -description

The **DXGKDDI_KERNELMODETESTINGINTERFACE** structure contains pointers to functions that are used for the kernel-mode testing interface.

## -struct-fields

### -field pfnBuildTestCommandBuffer

Pointer to the [**DXGKDDI_BUILDTESTCOMMANDBUFFER**](nc-d3dkmddi-dxgkddi_buildtestcommandbuffer.md) function.

## -remarks

For more information, see [Kernel-mode testing](/windows-hardware/drivers/display/kernel-mode-testing-of-wddm-features).

## -see-also

[**DXGKDDI_BUILDTESTCOMMANDBUFFER**](nc-d3dkmddi-dxgkddi_buildtestcommandbuffer.md)
