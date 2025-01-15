---
UID: NC:dispmprt.DXGKDDI_DISPLAYMUX_GET_DRIVER_SUPPORT_LEVEL
tech.root: display
title: DXGKDDI_DISPLAYMUX_GET_DRIVER_SUPPORT_LEVEL
ms.date: 01/13/2025
targetos: Windows
description: Learn more about the DXGKDDI_DISPLAYMUX_GET_DRIVER_SUPPORT_LEVEL function.
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
 - DXGKDDI_DISPLAYMUX_GET_DRIVER_SUPPORT_LEVEL
f1_keywords:
 - DXGKDDI_DISPLAYMUX_GET_DRIVER_SUPPORT_LEVEL
 - dispmprt/DXGKDDI_DISPLAYMUX_GET_DRIVER_SUPPORT_LEVEL
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_DISPLAYMUX_GET_DRIVER_SUPPORT_LEVEL
---

## -description

*Dxgkrnl* calls a kernel-mode display driver's (KMD) **DxgkDdiDisplayMuxGetDriverSupportLevel** function to query the level of support the driver has for the [automatic display switch](/windows-hardware/drivers/display/automatic-display-switch) (ADS) feature.

## -parameters

### -param DriverContext

[in] Handle to a context block that is associated with a display adapter. KMD's [**DxgkDdiAddDevice**](nc-dispmprt-dxgkddi_add_device.md) function previously provided this handle to *Dxgkrnl*.

### -param pDriverSupportLevel

[out] Pointer to a [**DXGK_DISPLAYMUX_SUPPORT_LEVEL**](../d3dkmdt/ne-d3dkmdt-dxgk_displaymux_support_level.md) value in which the driver writes the level of ADS support that it provides.

## -returns

**DxgkDdiDisplayMuxGetDriverSupportLevel** returns STATUS_SUCCESS if it succeeds. Otherwise, it returns an appropriate NT_STATUS error code.

## -remarks

This DDI is called under [synchronization level 2](/windows-hardware/drivers/display/threading-and-synchronization-second-level).

**DxgkDdiDisplayMuxGetDriverSupportLevel** is called before [**DxgkDdiStartDevice**](nc-dispmprt-dxgkddi_start_device.md). It's meant to return just the level of automatic display switch support the driver generically has. The support level returned shouldn't be influenced by any other factor, including:

* The GPU the driver is loaded for.
* Any other GPU in the system.
* Any aspect of the system; for example, internal or external monitor connected, system type, or any information obtained from the system.

If the driver supports automatic display switching on any system then it return a value that isn't DXGK_DISPLAYMUX_DRIVER_SUPPORT_LEVEL_NONE.

For more information, see [Automatic Display Switch](/windows-hardware/drivers/display/automatic-display-switch).

## -see-also

[**DXGK_DISPLAYMUX_SUPPORT_LEVEL**](../d3dkmdt/ne-d3dkmdt-dxgk_displaymux_support_level.md)

[**DxgkDdiAddDevice**](nc-dispmprt-dxgkddi_add_device.md)

[**DxgkDdiStartDevice**](nc-dispmprt-dxgkddi_start_device.md)
