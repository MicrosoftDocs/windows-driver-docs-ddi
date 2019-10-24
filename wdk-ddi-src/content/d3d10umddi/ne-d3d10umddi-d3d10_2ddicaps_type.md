---
UID: NE:d3d10umddi.D3D10_2DDICAPS_TYPE
title: D3D10_2DDICAPS_TYPE (d3d10umddi.h)
description: The D3D10_2DDICAPS_TYPE enumeration type contains values that identify the type of capability information that is retrieved from a call to the driver's GetCaps(D3D10_2) function.
old-location: display\d3d10_2ddicaps_type.htm
ms.assetid: 2ca906d4-6d09-4624-a985-a47794acc959
ms.date: 05/10/2018
ms.keywords: D3D10_2DDICAPS_TYPE, D3D10_2DDICAPS_TYPE enumeration [Display Devices], D3D11DDICAPS_3DPIPELINESUPPORT, D3D11DDICAPS_SHADER, D3D11DDICAPS_THREADING, D3D11_1DDICAPS_ARCHITECTURE_INFO, D3D11_1DDICAPS_D3D11_OPTIONS, D3D11_1DDICAPS_SHADER_MIN_PRECISION_SUPPORT, D3DWDDM1_3DDICAPS_D3D11_OPTIONS1, D3DWDDM1_3DDICAPS_MARKER, UMDisplayDriver_Dx11param_Structs_cde2c336-2e65-43c4-970c-83b83765df38.xml, d3d10umddi/D3D10_2DDICAPS_TYPE, d3d10umddi/D3D11DDICAPS_3DPIPELINESUPPORT, d3d10umddi/D3D11DDICAPS_SHADER, d3d10umddi/D3D11DDICAPS_THREADING, d3d10umddi/D3D11_1DDICAPS_ARCHITECTURE_INFO, d3d10umddi/D3D11_1DDICAPS_D3D11_OPTIONS, d3d10umddi/D3D11_1DDICAPS_SHADER_MIN_PRECISION_SUPPORT, d3d10umddi/D3DWDDM1_3DDICAPS_D3D11_OPTIONS1, d3d10umddi/D3DWDDM1_3DDICAPS_MARKER, display.d3d10_2ddicaps_type
ms.topic: enum
f1_keywords:
 - "d3d10umddi/D3D10_2DDICAPS_TYPE"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D10_2DDICAPS_TYPE is supported beginning with the Windows 7 operating system.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3d10umddi.h
api_name:
- D3D10_2DDICAPS_TYPE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D10_2DDICAPS_TYPE
ms.custom: 19H1
---

# D3D10_2DDICAPS_TYPE enumeration


## -description


The D3D10_2DDICAPS_TYPE enumeration type contains values that identify the type of capability information that is retrieved from a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10_2ddi_getcaps">GetCaps(D3D10_2)</a> function. 


## -enum-fields




### -field D3D11DDICAPS_THREADING

The driver retrieves a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_threading_caps">D3D11DDI_THREADING_CAPS</a> structure that describes the threading capabilities that the driver supports. 


### -field D3D11DDICAPS_SHADER

The driver retrieves a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_shader_caps">D3D11DDI_SHADER_CAPS</a> structure that describes the shader capabilities that the driver supports. 


### -field D3D11DDICAPS_3DPIPELINESUPPORT

The driver retrieves a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_3dpipelinesupport_caps">D3D11DDI_3DPIPELINESUPPORT_CAPS</a> structure that describes the pipeline capabilities that the driver supports. 


### -field D3D11_1DDICAPS_D3D11_OPTIONS

The driver retrieves a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_d3d11_options_data">D3D11_1DDI_D3D11_OPTIONS_DATA</a>  structure that specifies options to provide data to the user-mode driver.

Supported starting with Windows 8.


### -field D3D11_1DDICAPS_ARCHITECTURE_INFO

The driver retrieves a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-d3dddicaps_architecture_info">D3DDDICAPS_ARCHITECTURE_INFO</a> structure that describes information about Direct3D 11.1 adapter architecture.

Supported starting with Windows 8.


### -field D3D11_1DDICAPS_SHADER_MIN_PRECISION_SUPPORT

The driver retrieves a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-d3dddicaps_shader_min_precision_support">D3DDDICAPS_SHADER_MIN_PRECISION_SUPPORT</a> structure that describes the precision support options for shaders in the user-mode display driver.

Supported starting with Windows 8.


### -field D3DWDDM1_3DDICAPS_D3D11_OPTIONS1

The driver retrieves a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3dwddm1_3ddi_d3d11_options_data1">D3DWDDM1_3DDI_D3D11_OPTIONS_DATA1</a> structure that describes the tiled resource support options in the user-mode display driver.

Supported starting with Windows 8. Used by WDDM 1.3 and later drivers.


### -field D3DWDDM1_3DDICAPS_MARKER

Supported starting with Windows 8. Used by WDDM 1.3 and later drivers.


### -field D3DWDDM2_0DDICAPS_D3D11_OPTIONS2


### -field D3DWDDM2_0DDICAPS_MEMORY_ARCHITECTURE


### -field D3DWDDM2_0DDICAPS_TEXTURE_LAYOUT_SETS


### -field D3DWDDM2_0DDICAPS_TEXTURE_LAYOUT


### -field D3DWDDM2_0DDICAPS_SWIZZLE_PATTERN


### -field D3DWDDM2_0DDICAPS_D3D11_OPTIONS3


### -field D3DWDDM2_0DDICAPS_GPUVA_CAPS


### -field D3DWDDM2_0DDICAPS_TEXTURE_LAYOUT1


### -field D3DWDDM2_2DDICAPS_SHADERCACHE


### -field D3DWDDM2_2DDICAPS_TEXTURE_LAYOUT


### -field D3DWDDM2_2DDICAPS_SWIZZLE_PATTERN

### -field D3D12_DOWNLEVEL_DDICAPS_UMDFILENAME

Supported starting from Windows 10, version 1901. Used by WDDM 2.6 and later drivers.

## -remarks



To allow a driver to unify capability concepts, the values in the D3D10_2DDICAPS_TYPE enumeration are set up so they do not overlap with the values in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ne-d3dumddi-_d3dddicaps_type">D3DDDICAPS_TYPE</a> enumeration. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_3dpipelinesupport_caps">D3D11DDI_3DPIPELINESUPPORT_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_shader_caps">D3D11DDI_SHADER_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_threading_caps">D3D11DDI_THREADING_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_d3d11_options_data">D3D11_1DDI_D3D11_OPTIONS_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-d3dddicaps_shader_min_precision_support">D3DDDICAPS_SHADER_MIN_PRECISION_SUPPORT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ne-d3dumddi-_d3dddicaps_type">D3DDDICAPS_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3dwddm1_3ddi_d3d11_options_data1">D3DWDDM1_3DDI_D3D11_OPTIONS_DATA1</a>
 

 

