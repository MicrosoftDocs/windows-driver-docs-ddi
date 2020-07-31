---
UID: NC:d3dkmddi.DXGKDDI_CONTROLINTERRUPT2
title: DXGKDDI_CONTROLINTERRUPT2 (d3dkmddi.h)
description: The DxgkDdi_ControlInterrupt2 function enables or disables the given interrupt type on the graphics hardware.
old-location: display\dxgkddicontrolinterrupt2.htm
ms.assetid: 0C09CAB1-3DFC-4340-8FF2-99CAF7F13156
ms.date: 03/24/2020
ms.keywords: DXGKDDI_CONTROLINTERRUPT2, DXGKDDI_CONTROLINTERRUPT2 callback, DxgkDdi_ControlInterrupt2, DxgkDdi_ControlInterrupt2 callback function [Display Devices], d3dkmddi/DxgkDdi_ControlInterrupt2, display.dxgkddicontrolinterrupt2
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 10 and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3dkmddi/DxgkDdi_ControlInterrupt2"
 - "DxgkDdi_ControlInterrupt2"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DxgkDdi_ControlInterrupt2
product:
 - Windows
---

# DXGKDDI_CONTROLINTERRUPT2 callback function

## -description

The *DxgkDdi_ControlInterrupt2* function enables or disables the given interrupt type on the graphics hardware.

## -parameters

### -param hAdapter

[in] A handle to the adapter object for the graphics processing unit (GPU). The driver returned this handle in the *MiniportDeviceContext* parameter from a call to its [*DxgkDdiAddDevice*](https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device) function.

### -param InterruptControl

[in] A [**DXGKARG_CONTROLINTERRUPT2**](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_controlinterrupt2) structure that supplies the interrupt type, as well as the VSYNC state.

## -returns

*DxgkDdi_ControlInterrupt2* returns one of the following values:

| **Return code** | **Description** |
|:--|:--|
| **STATUS_SUCCESS** | The interrupt type was successfully enabled or disabled on the graphics hardware. |
| **STATUS_NOT_IMPLEMENTED** | *DxgkDdi_ControlInterrupt2* does not support enabling or disabling the specified interrupt type. |

## -remarks

Only one of *DxgkDdiControlInterrupt2* or [*DxgkDdi_ControlInterrupt3*](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_controlinterrupt3) will be used by the OS during the lifetime of an adapter.

WDDM 2.7 drivers that do not implement [*DxgkDdi_ControlInterrupt3*](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_controlinterrupt3) are opting out of independent VidPn VSync control, and the OS will only call *DxgkDdi_ControlInterrupt2*. The [**DXGK_DRIVERCAPS**](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps)**->IndependentVidPnVSync** capability must be 0 in drivers that do not support *DxgkDdi_ControlInterrupt3*; otherwise, the OS will fail adapter initialization. If driver does implement *DxgkDdi_ControlInterrupt3*, then the capability can be set to 0 or 1 to indicate Per-VidPn support.

## -see-also

[**DXGK_DRIVERCAPS**](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps)

[**DXGKARG_CONTROLINTERRUPT2**](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_controlinterrupt2)

[**DXGKARG_CONTROLINTERRUPT3**](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_controlinterrupt3)

[*DxgkDdi_ControlInterrupt3*](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_controlinterrupt3)

[*DxgkDdiAddDevice*](https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device)
