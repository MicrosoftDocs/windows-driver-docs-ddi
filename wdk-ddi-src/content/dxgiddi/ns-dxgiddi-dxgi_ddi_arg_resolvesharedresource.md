---
UID: NS:dxgiddi.DXGI_DDI_ARG_RESOLVESHAREDRESOURCE
title: DXGI_DDI_ARG_RESOLVESHAREDRESOURCE
author: windows-driver-content
description: The DXGI_DDI_ARG_RESOLVESHAREDRESOURCE structure describes the parameters that the user-mode display driver's ResolveSharedResourceDXGI function uses to synchronize a shared surface or a GDI interoperable surface.
old-location: display\dxgi_ddi_arg_resolvesharedresource.htm
old-project: display
ms.assetid: adc4bd3a-fbff-4a63-b818-b778762956ac
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DXGI_DDI_ARG_RESOLVESHAREDRESOURCE, DXGI_DDI_ARG_RESOLVESHAREDRESOURCE structure [Display Devices], UMDisplayDriver_Dx10param_Structs_16bbb236-75b5-4d2c-a6ca-b61010d5e08d.xml, display.dxgi_ddi_arg_resolvesharedresource, dxgiddi/DXGI_DDI_ARG_RESOLVESHAREDRESOURCE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	dxgiddi.h
api_name:
-	DXGI_DDI_ARG_RESOLVESHAREDRESOURCE
product:
- Windows
targetos: Windows
req.typenames: DXGI_DDI_ARG_RESOLVESHAREDRESOURCE
---

# DXGI_DDI_ARG_RESOLVESHAREDRESOURCE structure


## -description


The DXGI_DDI_ARG_RESOLVESHAREDRESOURCE structure describes the parameters that the user-mode display driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff569488">ResolveSharedResourceDXGI</a> function uses to synchronize a shared surface or a GDI interoperable surface. 


## -struct-fields




### -field hDevice

[in] A handle to the display device (graphics context) that is associated with the shared surface or GDI interoperable surface. The Direct3D runtime passes this handle to the driver in the <b>hDrvDevice</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541664">D3D10DDIARG_CREATEDEVICE</a> structure when the runtime calls the driver's <a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a> function to create the display device. 


### -field hResource

[in] A handle to the surface that the driver uses as a shared surface or in GDI interoperability.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff569488">ResolveSharedResourceDXGI</a>
 

 

