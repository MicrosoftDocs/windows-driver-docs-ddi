---
UID: NS:dxgiddi.DXGI_DDI_ARG_RESOLVESHAREDRESOURCE
title: DXGI_DDI_ARG_RESOLVESHAREDRESOURCE (dxgiddi.h)
description: The DXGI_DDI_ARG_RESOLVESHAREDRESOURCE structure describes the parameters that the user-mode display driver's ResolveSharedResourceDXGI function uses to synchronize a shared surface or a GDI interoperable surface.
old-location: display\dxgi_ddi_arg_resolvesharedresource.htm
tech.root: display
ms.assetid: adc4bd3a-fbff-4a63-b818-b778762956ac
ms.date: 05/10/2018
keywords: ["DXGI_DDI_ARG_RESOLVESHAREDRESOURCE structure"]
ms.keywords: DXGI_DDI_ARG_RESOLVESHAREDRESOURCE, DXGI_DDI_ARG_RESOLVESHAREDRESOURCE structure [Display Devices], UMDisplayDriver_Dx10param_Structs_16bbb236-75b5-4d2c-a6ca-b61010d5e08d.xml, display.dxgi_ddi_arg_resolvesharedresource, dxgiddi/DXGI_DDI_ARG_RESOLVESHAREDRESOURCE
f1_keywords:
 - "dxgiddi/DXGI_DDI_ARG_RESOLVESHAREDRESOURCE"
 - "DXGI_DDI_ARG_RESOLVESHAREDRESOURCE"
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: DXGI_DDI_ARG_RESOLVESHAREDRESOURCE is supported beginning with the Windows 7 operating system.
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
- dxgiddi.h
api_name:
- DXGI_DDI_ARG_RESOLVESHAREDRESOURCE
targetos: Windows
req.typenames: DXGI_DDI_ARG_RESOLVESHAREDRESOURCE
---

# DXGI_DDI_ARG_RESOLVESHAREDRESOURCE structure


## -description


The DXGI_DDI_ARG_RESOLVESHAREDRESOURCE structure describes the parameters that the user-mode display driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi1_1_ddi_base_functions">ResolveSharedResourceDXGI</a> function uses to synchronize a shared surface or a GDI interoperable surface. 


## -struct-fields




### -field hDevice

[in] A handle to the display device (graphics context) that is associated with the shared surface or GDI interoperable surface. The Direct3D runtime passes this handle to the driver in the <b>hDrvDevice</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createdevice">D3D10DDIARG_CREATEDEVICE</a> structure when the runtime calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a> function to create the display device. 


### -field hResource

[in] A handle to the surface that the driver uses as a shared surface or in GDI interoperability.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi1_1_ddi_base_functions">ResolveSharedResourceDXGI</a>
 

 

