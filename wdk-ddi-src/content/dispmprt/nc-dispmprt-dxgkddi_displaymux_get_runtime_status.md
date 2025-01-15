---
UID: NC:dispmprt.DXGKDDI_DISPLAYMUX_GET_RUNTIME_STATUS
tech.root: display
title: DXGKDDI_DISPLAYMUX_GET_RUNTIME_STATUS
ms.date: 01/13/2025
targetos: Windows
description: Learn more about the DXGKDDI_DISPLAYMUX_GET_RUNTIME_STATUS function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: dispmprt.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2, update 2025.01
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
 - dispmprt.h
api_name:
 - DXGKDDI_DISPLAYMUX_GET_RUNTIME_STATUS
f1_keywords:
 - DXGKDDI_DISPLAYMUX_GET_RUNTIME_STATUS
 - dispmprt/DXGKDDI_DISPLAYMUX_GET_RUNTIME_STATUS
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_DISPLAYMUX_GET_RUNTIME_STATUS
---

## -description

*Dxgkrnl* calls the kernel-mode display driver's (KMD) **DxgkDdiDisplayMuxGetRuntimeStatus** function to query the runtime level of automatic display switch (ADS) support that the driver provides.

## -parameters

### -param DriverContext

[in] Handle to a context block that is associated with a display adapter. KMD's [**DxgkDdiAddDevice**](nc-dispmprt-dxgkddi_add_device.md) function previously provided this handle to *Dxgkrnl*.

### -param pRuntimeStatus

[out] Pointer to a [**DXGK_DISPLAYMUX_RUNTIME_STATUS**](../d3dkmdt/ne-d3dkmdt-dxgk_displaymux_runtime_status.md) value in which the driver writes the runtime status of ADS support that it provides.

## -returns

**DxgkDdiDisplayMuxGetRuntimeStatus** returns STATUS_SUCCESS if it succeeds. Otherwise, it returns an appropriate NT_STATUS error code.

## -remarks

This DDI is called under [synchronization level 2](/windows-hardware/drivers/display/threading-and-synchronization-second-level).

**DxgkDdiDisplayMuxGetRuntimeStatus** is called after [**DxgkDdiStartDevice**](nc-dispmprt-dxgkddi_start_device.md). It allows KMD to indicate that it can't support ADS on this system for some reason. The driver shouldn't attempt to query information about other GPUs in the system or communicate with the ACPI mux device.

If the driver sets **pRuntimeStatus** to point to DXGK_DISPLAYMUX_RUNTIME_STATUS_NON_CRITICAL_SYSTEM_INFO_MISSING, the system will enable ADS for developmental purposes only; that is, ADS will not be enabled for customer use.

For more information, see [Automatic Display Switch](/windows-hardware/drivers/display/automatic-display-switch).

## -see-also

[**DXGK_DISPLAYMUX_RUNTIME_STATUS**](../d3dkmdt/ne-d3dkmdt-dxgk_displaymux_runtime_status.md)

[**DxgkDdiAddDevice**](nc-dispmprt-dxgkddi_add_device.md)

[**DxgkDdiStartDevice**](nc-dispmprt-dxgkddi_start_device.md)
