---
UID: NS:dxgiddi.DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS
title: DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS (dxgiddi.h)
description: The DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS structure contains gamma capabilities.
old-location: display\dxgi_ddi_arg_get_gamma_control_caps.htm
tech.root: display
ms.assetid: 1e7930e4-ab3e-4981-9533-ed1da8c777dc
ms.date: 05/10/2018
keywords: ["DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS structure"]
ms.keywords: DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS, DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS structure [Display Devices], UMDisplayDriver_Dx10param_Structs_770eb1ba-2972-4133-b899-a096a53fc1de.xml, display.dxgi_ddi_arg_get_gamma_control_caps, dxgiddi/DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.typenames: DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS
f1_keywords:
 - DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS
 - dxgiddi/DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dxgiddi.h
api_name:
 - DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS
---

# DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS structure


## -description

The DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS structure contains gamma capabilities.

## -struct-fields

### -field hDevice

[in] A handle to the display device (graphics context) from which the driver retrieves gamma capabilities. The Direct3D runtime passes this handle to the driver in the <b>hDrvDevice</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createdevice">D3D10DDIARG_CREATEDEVICE</a> structure when the runtime calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a> function to create the display device.

### -field pGammaCapabilities

[in/out] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgitype/ns-dxgitype-dxgi_gamma_control_capabilities">DXGI_GAMMA_CONTROL_CAPABILIITES</a> structure that describes gamma capabilities.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgitype/ns-dxgitype-dxgi_gamma_control_capabilities">DXGI_GAMMA_CONTROL_CAPABILIITES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">GetGammaCapsDXGI</a>

