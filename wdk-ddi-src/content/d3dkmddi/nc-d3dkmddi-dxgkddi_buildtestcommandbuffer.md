---
UID: NC:d3dkmddi.DXGKDDI_BUILDTESTCOMMANDBUFFER
tech.root: display
title: DXGKDDI_BUILDTESTCOMMANDBUFFER
ms.date: 06/17/2024
targetos: Windows
description: Learn about the DXGKDDI_BUILDTESTCOMMANDBUFFER function.
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
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
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
 - DXGKDDI_BUILDTESTCOMMANDBUFFER
f1_keywords:
 - DXGKDDI_BUILDTESTCOMMANDBUFFER
 - d3dkmddi/DXGKDDI_BUILDTESTCOMMANDBUFFER
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_BUILDTESTCOMMANDBUFFER
---

## -description

KMD's **DXGKDDI_BUILDTESTCOMMANDBUFFER** function builds a test command buffer for [kernel-mode testing](/windows-hardware/drivers/display/kernel-mode-testing-of-wddm-features).

## -parameters

### -param hAdapter

[in] A handle to a context block that is associated with a display adapter. The kernel-mode display miniport driver (KMD) previously provided this handle to *Dxgkrnl* in the **MiniportDeviceContext** output parameter of the [**DxgkDdiAddDevice**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md) function.

### -param pArgs

[in/out] Pointer to a [**DXGKARG_BUILDTESTCOMMANDBUFFER**](ns-d3dkmddi-dxgkarg_buildtestcommandbuffer.md) structure that describes the test command buffer to build.

## -returns

**DXGKDDI_BUILDTESTCOMMANDBUFFER** returns NTSTATUS_SUCCESS if the function succeeds. Otherwise, it returns an appropriate NTSTATUS code such as STATUS_BUFFER_OVERFLOW.

## -remarks

**DXGKDDI_BUILDTESTCOMMANDBUFFER** builds a command buffer with device-specific instructions for a set of simple commands. KMD returns a pointer to this function in **pfnBuildTestCommandBuffer** via [**DxgkDdiQueryFeatureInterface**](/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryfeatureinterface)(DXGK_FEATURE_KERNEL_MODE_TESTING).

When **pDmaBuffer** is NULL or is too small, KMD needs to set the required size for the buffer in **DmaBufferSize** and return STATUS_BUFFER_OVERFLOW.

When **pDmaBufferPrivateData** is NULL or too small and KMD needs to generate private data, KMD needs to set the required size in **DmaBufferPrivateDataSize** and return STATUS_BUFFER_OVERFLOW.

The KMD must calculate the size of both buffers in the same call.

For more information, see [Kernel-mode testing](/windows-hardware/drivers/display/kernel-mode-testing-of-wddm-features).

## -see-also

[**DXGKARG_BUILDTESTCOMMANDBUFFER**](ns-d3dkmddi-dxgkarg_buildtestcommandbuffer.md)

[**DxgkDdiQueryFeatureInterface**](/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryfeatureinterface)
