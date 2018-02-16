---
UID: NS:dxgiddi.DXGI_DDI_ARG_RESOLVESHAREDRESOURCE
title: DXGI_DDI_ARG_RESOLVESHAREDRESOURCE
author: windows-driver-content
description: The DXGI_DDI_ARG_RESOLVESHAREDRESOURCE structure describes the parameters that the user-mode display driver's ResolveSharedResourceDXGI function uses to synchronize a shared surface or a GDI interoperable surface.
old-location: display\dxgi_ddi_arg_resolvesharedresource.htm
old-project: display
ms.assetid: adc4bd3a-fbff-4a63-b818-b778762956ac
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGI_DDI_ARG_RESOLVESHAREDRESOURCE, UMDisplayDriver_Dx10param_Structs_16bbb236-75b5-4d2c-a6ca-b61010d5e08d.xml, display.dxgi_ddi_arg_resolvesharedresource, DXGI_DDI_ARG_RESOLVESHAREDRESOURCE structure [Display Devices], dxgiddi/DXGI_DDI_ARG_RESOLVESHAREDRESOURCE
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	dxgiddi.h
apiname:
-	DXGI_DDI_ARG_RESOLVESHAREDRESOURCE
product: Windows
targetos: Windows
req.typenames: DXGI_DDI_ARG_RESOLVESHAREDRESOURCE
---

# DXGI_DDI_ARG_RESOLVESHAREDRESOURCE structure


## -description


The DXGI_DDI_ARG_RESOLVESHAREDRESOURCE structure describes the parameters that the user-mode display driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff569488">ResolveSharedResourceDXGI</a> function uses to synchronize a shared surface or a GDI interoperable surface. 


## -syntax


````
typedef struct DXGI_DDI_ARG_RESOLVESHAREDRESOURCE {
  DXGI_DDI_HDEVICE   hDevice;
  DXGI_DDI_HRESOURCE hResource;
} DXGI_DDI_ARG_RESOLVESHAREDRESOURCE;
````


## -struct-fields




### -field hDevice

[in] A handle to the display device (graphics context) that is associated with the shared surface or GDI interoperable surface. The Direct3D runtime passes this handle to the driver in the <b>hDrvDevice</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createdevice.md">D3D10DDIARG_CREATEDEVICE</a> structure when the runtime calls the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a> function to create the display device. 


### -field hResource

[in] A handle to the surface that the driver uses as a shared surface or in GDI interoperability.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569488">ResolveSharedResourceDXGI</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGI_DDI_ARG_RESOLVESHAREDRESOURCE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

