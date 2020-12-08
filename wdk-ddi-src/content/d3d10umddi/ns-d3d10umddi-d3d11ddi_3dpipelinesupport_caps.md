---
UID: NS:d3d10umddi.D3D11DDI_3DPIPELINESUPPORT_CAPS
title: D3D11DDI_3DPIPELINESUPPORT_CAPS (d3d10umddi.h)
description: The D3D11DDI_3DPIPELINESUPPORT_CAPS structure contains display device pipeline capabilities.
old-location: display\d3d11ddi_3dpipelinesupport_caps.htm
ms.date: 05/10/2018
keywords: ["D3D11DDI_3DPIPELINESUPPORT_CAPS structure"]
ms.keywords: D3D11DDI_3DPIPELINESUPPORT_CAPS, D3D11DDI_3DPIPELINESUPPORT_CAPS structure [Display Devices], UMDisplayDriver_Dx11param_Structs_dc9a2de4-8fcf-4cd4-9c59-cc57941cab00.xml, d3d10umddi/D3D11DDI_3DPIPELINESUPPORT_CAPS, display.d3d11ddi_3dpipelinesupport_caps
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D11DDI_3DPIPELINESUPPORT_CAPS is supported beginning with the Windows 7 operating system.
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
tech.root: display
req.typenames: D3D11DDI_3DPIPELINESUPPORT_CAPS
f1_keywords:
 - D3D11DDI_3DPIPELINESUPPORT_CAPS
 - d3d10umddi/D3D11DDI_3DPIPELINESUPPORT_CAPS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3D11DDI_3DPIPELINESUPPORT_CAPS
---

# D3D11DDI_3DPIPELINESUPPORT_CAPS structure


## -description

The D3D11DDI_3DPIPELINESUPPORT_CAPS structure contains display device pipeline capabilities.

## -struct-fields

### -field Caps

[in] A value that identifies the pipeline capabilities of the driver.

## -remarks

The driver uses the one of the values from the <a href="/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11ddi_3dpipelinelevel">D3D11DDI_3DPIPELINELEVEL</a> enumeration and the following macro to encode the 3-D pipeline level:

```cpp
#define D3D11DDI_ENCODE_3DPIPELINESUPPORT_CAP( Level ) (0x1 << Level)
```

The driver then uses the macro's result in the <b>Caps</b> member of the D3D11DDI_3DPIPELINESUPPORT_CAPS structure to provide information to the Direct3D runtime when the runtime calls the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10_2ddi_getcaps">GetCaps(D3D10_2)</a> function with the <b>Type</b> member of <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10_2ddiarg_getcaps">D3D10_2DDIARG_GETCAPS</a> set to D3D11DDICAPS_3DPIPELINESUPPORT.

The driver uses the following constant and macros to extract one of the values from the <a href="/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11ddi_3dpipelinelevel">D3D11DDI_3DPIPELINELEVEL</a> enumeration that represents the 3-D pipeline level to set for a display device. The driver extracts the value from the <b>Caps</b> member of the D3D11DDI_3DPIPELINESUPPORT_CAPS structure. The driver uses the 3-D pipeline level to create the appropriate display device when the driver receives a call to its <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a> function.

```cpp
#define D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_SHIFT (0x1)
#define D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_MASK (0x7 << D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_SHIFT)
#define D3D11DDI_EXTRACT_3DPIPELINELEVEL_FROM_FLAGS( Flags ) \
    ((D3D11DDI_3DPIPELINELEVEL)(((Flags) & D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_MASK) >> \
    D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_SHIFT))
```

For more information about the Direct3D version 10 pipeline, see <a href="/windows-hardware/drivers/display/rendering-pipeline">Rendering Pipeline</a>. 

For more information about the Direct3D version 11 pipelines, see <a href="/windows-hardware/drivers/display/pipelines-for-direct3d-version-11">Pipelines for Direct3D Version 11</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d10_2ddicaps_type">D3D10_2DDICAPS_TYPE</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11ddi_3dpipelinelevel">D3D11DDI_3DPIPELINELEVEL</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10_2ddi_getcaps">GetCaps(D3D10_2)</a>
