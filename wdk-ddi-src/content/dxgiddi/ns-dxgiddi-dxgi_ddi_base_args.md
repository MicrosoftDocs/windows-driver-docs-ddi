---
UID: NS:dxgiddi.DXGI_DDI_BASE_ARGS
title: DXGI_DDI_BASE_ARGS (dxgiddi.h)
description: The DXGI_DDI_BASE_ARGS structure contains Microsoft DirectX Graphics Infrastructure (DXGI) basic device driver interface (DDI) device creation arguments.
old-location: display\dxgi_ddi_base_args.htm
tech.root: display
ms.assetid: e835edb9-7a7e-4258-957a-49877b1ed562
ms.date: 05/10/2018
keywords: ["DXGI_DDI_BASE_ARGS structure"]
ms.keywords: DXGI_DDI_BASE_ARGS, DXGI_DDI_BASE_ARGS structure [Display Devices], UMDisplayDriver_Dx10param_Structs_3dec4197-80df-4de3-96ca-d4f90f23e85d.xml, display.dxgi_ddi_base_args, dxgiddi/DXGI_DDI_BASE_ARGS
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
req.typenames: DXGI_DDI_BASE_ARGS
f1_keywords:
 - DXGI_DDI_BASE_ARGS
 - dxgiddi/DXGI_DDI_BASE_ARGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dxgiddi.h
api_name:
 - DXGI_DDI_BASE_ARGS
---

# DXGI_DDI_BASE_ARGS structure


## -description

The <b>DXGI_DDI_BASE_ARGS</b> structure contains Microsoft DirectX Graphics Infrastructure (DXGI) basic device driver interface (DDI) device creation arguments.

## -struct-fields

### -field pDXGIBaseCallbacks

[in] A pointer to a <a href="/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_callbacks">DXGI_DDI_BASE_CALLBACKS</a> structure that contains a table of Microsoft Direct3D runtime callback functions that the driver can use to access kernel services.

### -field pDXGIDDIBaseFunctions6_1

### -field pDXGIDDIBaseFunctions6

### -field pDXGIDDIBaseFunctions5

### -field pDXGIDDIBaseFunctions4

[in/out] A pointer to a <a href="/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi1_3_ddi_base_functions">DXGI1_3_DDI_BASE_FUNCTIONS</a> structure that the user-mode display driver fills with a table of its functions. The Direct3D runtime uses these functions to communicate with the user-mode display driver.

 Supported starting with Windows 8.1.

### -field pDXGIDDIBaseFunctions3

[in/out] A pointer to a <a href="/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi1_2_ddi_base_functions">DXGI1_2_DDI_BASE_FUNCTIONS</a> structure that the user-mode display driver fills with a table of its functions. The Direct3D runtime uses these functions to communicate with the user-mode display driver.

Supported starting with Windows 8.

### -field pDXGIDDIBaseFunctions2

[in/out] A pointer to a <a href="/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi1_1_ddi_base_functions">DXGI1_1_DDI_BASE_FUNCTIONS</a> structure that the user-mode display driver fills with a table of its functions. The Direct3D runtime uses these functions to communicate with the user-mode display driver.

 Supported starting with Windows 7.

### -field pDXGIDDIBaseFunctions

[in/out] A pointer to a <a href="/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">DXGI_DDI_BASE_FUNCTIONS</a> structure that the user-mode display driver fills with a table of its functions. The Direct3D runtime uses these functions to communicate with the user-mode display driver.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createdevice">D3D10DDIARG_CREATEDEVICE</a>



<a href="/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi1_1_ddi_base_functions">DXGI1_1_DDI_BASE_FUNCTIONS</a>



<a href="/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi1_2_ddi_base_functions">DXGI1_2_DDI_BASE_FUNCTIONS</a>



<a href="/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi1_3_ddi_base_functions">DXGI1_3_DDI_BASE_FUNCTIONS</a>



<a href="/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_callbacks">DXGI_DDI_BASE_CALLBACKS</a>



<a href="/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_base_functions">DXGI_DDI_BASE_FUNCTIONS</a>