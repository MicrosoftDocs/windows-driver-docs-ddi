---
UID: NS:dxgiddi.DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS
title: DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS
author: windows-driver-content
description: The DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS structure contains gamma capabilities.
old-location: display\dxgi_ddi_arg_get_gamma_control_caps.htm
old-project: display
ms.assetid: 1e7930e4-ab3e-4981-9533-ed1da8c777dc
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS, dxgiddi/DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS, display.dxgi_ddi_arg_get_gamma_control_caps, UMDisplayDriver_Dx10param_Structs_770eb1ba-2972-4133-b899-a096a53fc1de.xml, DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS structure [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	dxgiddi.h
apiname:
-	DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS
product: Windows
targetos: Windows
req.typenames: DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS
---

# DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS structure


## -description


The DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS structure contains gamma capabilities. 


## -syntax


````
typedef struct DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS {
  DXGI_DDI_HDEVICE                hDevice;
  DXGI_GAMMA_CONTROL_CAPABILITIES *pGammaCapabilities;
} DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS;
````


## -struct-fields




### -field hDevice

[in] A handle to the display device (graphics context) from which the driver retrieves gamma capabilities. The Direct3D runtime passes this handle to the driver in the <b>hDrvDevice</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createdevice.md">D3D10DDIARG_CREATEDEVICE</a> structure when the runtime calls the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a> function to create the display device. 


### -field pGammaCapabilities

[in/out] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff557521">DXGI_GAMMA_CONTROL_CAPABILIITES</a> structure that describes gamma capabilities. 


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566790">GetGammaCapsDXGI</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557521">DXGI_GAMMA_CONTROL_CAPABILIITES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

