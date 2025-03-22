---
UID: NC:d3dkmddi.DXGKDDI_CREATEHWQUEUE
tech.root: display
title: DXGKDDI_CREATEHWQUEUE
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGKDDI_CREATEHWQUEUE function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 1703 (WDDM 2.2)
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_CREATEHWQUEUE
f1_keywords:
 - DXGKDDI_CREATEHWQUEUE
 - d3dkmddi/DXGKDDI_CREATEHWQUEUE
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_CREATEHWQUEUE
---

# DXGKDDI_CREATEHWQUEUE function (d3dkmddi.h)

## -description

*Dxgkrnl* calls **DxgkDdiCreateHwQueue** to have the kernel-mode display driver (KMD) perform the work to create a hardware queue.

## -parameters

### -param hHwContext

[in] The hardware context handle that the hardware queue belongs to.

### -param pCreateHwQueue

[in/out] A pointer to a [**DXGKARG_CREATEHWQUEUE**](ns-d3dkmddi-dxgkarg_createhwqueue.md) structure that describes the hardware queue to create.

## -returns

**DxgkDdiCreateHwQueue** returns STATUS_SUCCESS if KMD was able to successfully create a hardware queue. Otherwise, it returns an appropriate NTSTATUS error code.

## -remarks

**DxgkDdiCreateHwQueue**'s [WDDM synchronization class is Zero level](/windows-hardware/drivers/display/threading-and-synchronization-zero-level).

## -see-also

[**DXGKARG_CREATEHWQUEUE**](ns-d3dkmddi-dxgkarg_createhwqueue.md)

[**DxgkDestroyHwQueue**](nc-d3dkmddi-dxgkddi_destroyhwqueue.md)
