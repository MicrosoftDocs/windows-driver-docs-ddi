---
UID: NC:d3dkmddi.DXGKDDI_CONTROLINTERRUPT2
title: DXGKDDI_CONTROLINTERRUPT2 (d3dkmddi.h)
description: The DxgkDdi_ControlInterrupt2 function enables or disables the given interrupt type on the graphics hardware.
old-location: display\dxgkddicontrolinterrupt2.htm
ms.assetid: 0C09CAB1-3DFC-4340-8FF2-99CAF7F13156
ms.date: 05/10/2018
ms.keywords: DXGKDDI_CONTROLINTERRUPT2, DXGKDDI_CONTROLINTERRUPT2 callback, DxgkDdi_ControlInterrupt2, DxgkDdi_ControlInterrupt2 callback function [Display Devices], d3dkmddi/DxgkDdi_ControlInterrupt2, display.dxgkddicontrolinterrupt2
ms.topic: callback
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
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_CONTROLINTERRUPT2 callback function


## -description


The <i>DxgkDdi_ControlInterrupt2</i> function enables or disables the given interrupt type on the graphics hardware.


## -parameters




### -param hAdapter [in]

[in] A handle to the adapter object for the graphics processing unit (GPU). The driver returned this handle in the <i>MiniportDeviceContext</i> parameter from a call to its <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function.


### -param InterruptControl [in]

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/mt654042">DXGKARG_CONTROLINTERRUPT2</a>-type value that supplies the interrupt type, as well as the VSYNC state.


## -returns



<i>DxgkDdi_ControlInterrupt2</i> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **STATUS_SUCCESS** | The interrupt type was successfully enabled or disabled on the graphics hardware. | 
| **STATUS_NOT_IMPLEMENTED** | [DxgkDdi_ControlInterrupt2](https://msdn.microsoft.com/library/windows/hardware/mt667971)  does not support enabling or disabling the specified interrupt type. | 
